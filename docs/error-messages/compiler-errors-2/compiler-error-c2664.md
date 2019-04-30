---
title: 컴파일러 오류 C2664
ms.date: 11/04/2016
f1_keywords:
- C2664
helpviewer_keywords:
- C2664
ms.assetid: 3595d66e-cf87-4fda-a896-c0cd81f95db4
ms.openlocfilehash: cffd178e1736358333ee27d4572d3531de23f527
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360322"
---
# <a name="compiler-error-c2664"></a>컴파일러 오류 C2664

'function' : 인수 n을(를) 'type1'에서 'type2'(으)로 변환할 수 없습니다.

이 매개 변수 변환 문제는 클래스의 인스턴스가 생성되고 `explicit` 키워드로 표시된 생성자에 대해 암시적 변환을 시도할 경우에 발생할 수 있습니다. 명시적 변환에 대 한 자세한 내용은 참조 하세요. [사용자 정의 형식 변환](../../cpp/user-defined-type-conversions-cpp.md)합니다.

개체에 대한 참조를 매개 변수로 사용하는 함수에 임시 개체를 전달하는 경우 해당 참조는 `const` 참조여야 합니다.

함수가 정해진 형식이 아닌 매개 변수를 통해 전달되면 적절한 생성자를 사용하여 임시 개체가 생성됩니다. 그런 다음 이 임시 개체가 함수에 전달됩니다. 이러한 경우 임시 개체는 참조를 초기화하는 데 사용됩니다. 이전 버전의 언어에서 모든 참조는 임시 개체에 의해 초기화될 수 있었습니다.

C2664를 해결하려면

- 제공된 함수의 프로토타입을 재확인하고 오류 메시지에 표시된 인수를 수정합니다.

- 필요한 경우 명시적 변환을 제공합니다.

C2664는 클래스에서 기본 클래스 중 하나의 멤버를 숨기는 경우에도 발생할 수 있습니다.

자세한 내용은 [방법: System:: string을 wchar_t * 또는 char 변환할\*](../../dotnet/how-to-convert-system-string-to-wchar-t-star-or-char-star.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C2664를 생성하고 해결 방법을 보여 줍니다.

```
// C2664.cpp
// C2664
struct A {
   void f(int i) {};
};

struct B : public A {
   // To fix, uncomment the following line.
   // using A::f;
   void f(A a) {};
};

int main() {
   B b;
   int i = 1;
   b.f(i);   // B::F hides A::f Uncomment the using declaration in B.
}
```

## <a name="example"></a>예제

다음 샘플에서도 C2664를 생성하고 해결 방법을 보여 줍니다.

```
// C2664b.cpp
// C2664 expected
struct A {
   // To fix, uncomment the following line.
   // A(int i){}
};

void func( int, A ) {}

int main() {
   func( 1, 1 );   // No conversion from int to A.
}
```

## <a name="example"></a>예제

다음 샘플에서는 문자열 리터럴로 `Test`를 호출하여 C2664를 보여 주고 해결 방법을 보여 줍니다. 매개 변수가 `szString` 참조이므로 적절한 생성자를 사용하여 개체를 생성해야 합니다. 결과 개체는 임시 개체이므로 참조를 초기화하는 데 사용할 수 없습니다.

```
// C2664c.cpp
// compile with: /EHsc
// C2664 expected
#include <iostream>
#include <string.h>
using namespace std;

class szString {
   int slen;
   char *str;

public:
   szString(const char *);
   int len() const {
      return slen;
   }
};

// Simple reference cannot bind to temp var.
void Test(szString &a) {}

// To fix, uncomment the following line.
// void Test(const szString &a) {}

szString::szString(const char * newstr) : slen(0), str(NULL) {
   slen=strlen(newstr);
   str = new char[slen + 1];
   if (str)
      strcpy_s(str, (slen + 1), newstr);
}

int main() {
   Test("hello");
}
```

## <a name="example"></a>예제

컴파일러는 C++ 표준 요구 사항에 따라 `const`를 적용합니다. 이 샘플은 C2664를 생성합니다.

```
// C2664d.cpp
// C2664 expected
#include <windows.h>

void func1(LPCSTR &s)
{

}

void func2(LPSTR &s)
{
   func1(s);
}

int main()
{
   return 0;
}
```

## <a name="example"></a>예제

다음은 C2664가 생성되는 더 복잡한 상황이며, 해결 방법에 대한 지침을 포함합니다.

```
// C2664e.cpp
// compile with: /EHsc
// C2664 expected
#define _INTL
#include <locale>
#include <iostream>

using namespace std;
#define LEN 90

int main( ) {
   char* pszExt = "This is the string to be converted!";
   wchar_t pwszInt [LEN+1];
   memset(&pwszInt[0], 0, (sizeof(wchar_t))*(LEN+1));

   // To fix, delete the following line.
   char* pszNext;

   // To fix, uncomment the following line.
   // const char* pszNext;

   wchar_t* pwszNext;
   mbstate_t state;
   locale loc("C");
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >
      ( loc ).in( state,
      pszExt, &pszExt[strlen(pszExt)], pszNext,
      pwszInt, &pwszInt[strlen(pszExt)], pwszNext );
   // See earlier comment.
      pwszInt[strlen(pszExt)] = 0;
   wcout << ( (res!=codecvt_base::error) ?
                       L"It worked! " : L"It didn't work! " )
   << L"The converted string is:\n ["
   << &pwszInt[0]
   << L"]" << endl;

   exit(-1);
}
```

## <a name="example"></a>예제

열거형 변수는 함수 호출을 충족하기 위한 해당 내부 형식으로 변환되지 않습니다. 자세한 내용은 [enum 클래스](../../extensions/enum-class-cpp-component-extensions.md)합니다. 다음 샘플에서는 C2664를 생성하고 해결 방법을 보여 줍니다.

```
// C2664f.cpp
// compile with: /clr
using namespace System;
public enum class A : Char {
   None = 0,
   NonSilent = 1,
};

void Test(Char c) {}

int main() {
   A aa = A::None;
   Test(aa);   // C2664
   Test(Char(aa));   // OK - fix by using a conversion cast
}
```

## <a name="example"></a>예제

midl 컴파일러에 있는 버그로 인해 wchar_t 형식이 형식 라이브러리에서 부호 없는 short로 생성됩니다. 이 오류를 해결하려면 C++ 소스 코드에서 형식을 캐스팅하거나 idl 파일에서 형식을 문자열로 정의해야 합니다.

```
// C2664g.idl
import "prsht.idl";

[ object, uuid(8402B8F1-BF7F-4B49-92D4-C2B9DF4543E9) ]

interface IMyObj1 : IUnknown {
   HRESULT  teststr([in, string] wchar_t *wstr);
   HRESULT  testarr([in, size_is(len)] wchar_t wstr[], [in] int len);
   HRESULT  testbstr([in] BSTR bstr);
};

[  uuid(44463307-CBFC-47A6-8B4F-13CD0A83B436) ]
library myproj1 {
   [  version(1.0), uuid(D8622C12-5448-42B8-8F0E-E3AD6B8470C1) ]
   coclass CMyObj1 { interface IMyObj1; };
}
```

C2664는 Visual C++ 6.0에서 이후 버전으로 코드를 이식할 때 `wchar_t`를 사용해도 발생합니다. Visual C++ 6.0 및 이전 버전에서는 `wchar_t`가 `typedef`용 `unsigned short`였기 때문에 해당 형식으로 암시적으로 변환할 수 있었습니다. Visual C++ 6.0 이후 버전에서는 C++ 표준에 지정된 것과 같이 `wchar_t`가 고유 기본 제공 형식이고 더 이상 `unsigned short`로 암시적으로 변환할 수 없습니다. 참조 [/zc: wchar_t (wchar_t는 네이티브 형식임)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C2664를 생성하고 해결 방법을 보여 줍니다.

```
// C2664h.cpp
#import "C2664g.tlb"
using namespace myproj1;

int main() {
   IMyObj1Ptr ptr;

   wchar_t * mybuff = 0;
   BSTR bstr = 0;
   int len;
   ptr->teststr(mybuff);
   ptr->testbstr(bstr);
   ptr->testarr(mybuff, len);   // C2664
   ptr->testarr((unsigned short *)mybuff, len);   // OK - Fix by using a cast
}
```

## <a name="example"></a>예제

C2664는 컴파일러가 템플릿 인수를 추론할 수 없는 경우에도 발생합니다.

```
// C2664i.cpp
#include <stdio.h>
template <class T, int iType=0>
class CTypedImg {
public:
   CTypedImg() {}
   void run() {}

   operator CTypedImg<T>& () {
      return *((CTypedImg<T>*)this);
    }
};

template <class t1>
void test(CTypedImg<t1>& myarg) {
   myarg.run();
}

int main() {
   CTypedImg<float,2> img;

   test((CTypedImg<float>&)img);   // OK
   test<float>(img);   // OK
   test(img);   // C2664 - qualify as above to fix
}
```