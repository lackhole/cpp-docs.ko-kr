---
title: '방법: 네이티브 형식으로 핸들 선언'
ms.custom: get-started-article
ms.date: 11/04/2016
f1_keywords:
- gcroot
helpviewer_keywords:
- handles, declaring
- gcroot keyword [C++]
- types [C++], declaring handles in
ms.assetid: b8c0eead-17e5-4003-b21f-b673f997d79f
ms.openlocfilehash: f5d6d31be9f3c10e1a56639ccf20663ce59d7941
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387411"
---
# <a name="how-to-declare-handles-in-native-types"></a>방법: 네이티브 형식으로 핸들 선언

네이티브 형식에서 핸들 형식을 선언할 수 없습니다. vcclr.h 형식이 안전한 래퍼 템플릿을 제공 `gcroot` CLR 개체에서 참조 하는 C++ 힙. 이 서식 파일을 사용 하면 네이티브 형식에 가상 핸들을 포함 하 고 기본 형식인 것 처럼 처리를 수행할 수 있습니다. 대부분의 경우에서 사용할 수는 `gcroot` 개체로 캐스팅 없이 포함된 된 형식입니다. 그러나 [각각에](../dotnet/for-each-in.md)를 사용 해야 `static_cast` 기본 관리 되는 참조를 검색 하려면.

`gcroot` 템플릿 가비지 수집 힙에 System::Runtime::InteropServices::GCHandle "handles"를 제공 하는 값 클래스의 기능을 사용 하 여 구현 됩니다. 핸들 자체 가비지 수집 되지 않습니다 하 고 사용 하 여 더 이상에서 소멸자에 의해 해제 됩니다는 `gcroot` 클래스 (이 소멸자 수동으로 호출할 수 없습니다). 인스턴스화하는 경우는 `gcroot` 네이티브 힙에 개체를 호출 해야 해당 리소스를 삭제 합니다.

런타임 핸들에서 참조 하는 CLR 개체 사이의 연결을 유지 합니다. CLR 개체를 가비지 수집 힙을 사용 하 여 이동 핸들 개체의 새 주소를 반환 합니다. 변수를 할당 하기 전에 고정 될 필요가 없습니다를 `gcroot` 템플릿.

## <a name="example"></a>예제

이 샘플에는 만드는 방법을 보여 줍니다는 `gcroot` 네이티브 스택의 개체입니다.

```
// mcpp_gcroot.cpp
// compile with: /clr
#include <vcclr.h>
using namespace System;

class CppClass {
public:
   gcroot<String^> str;   // can use str as if it were String^
   CppClass() {}
};

int main() {
   CppClass c;
   c.str = gcnew String("hello");
   Console::WriteLine( c.str );   // no cast required
}
```

```Output
hello
```

## <a name="example"></a>예제

이 샘플에는 만드는 방법을 보여 줍니다는 `gcroot` 네이티브 힙에 개체입니다.

```
// mcpp_gcroot_2.cpp
// compile with: /clr
// compile with: /clr
#include <vcclr.h>
using namespace System;

struct CppClass {
   gcroot<String ^> * str;
   CppClass() : str(new gcroot<String ^>) {}

   ~CppClass() { delete str; }

};

int main() {
   CppClass c;
   *c.str = gcnew String("hello");
   Console::WriteLine( *c.str );
}
```

```Output
hello
```

## <a name="example"></a>예제

이 샘플에 사용 하는 방법을 보여 줍니다 `gcroot` 를 사용 하 여 참조 형식이 아닌 값 형식에 대 한 참조를 네이티브 형식에 저장할 `gcroot` boxed 형식에서입니다.

```
// mcpp_gcroot_3.cpp
// compile with: /clr
#include < vcclr.h >
using namespace System;

public value struct V {
   String^ str;
};

class Native {
public:
   gcroot< V^ > v_handle;
};

int main() {
   Native native;
   V v;
   native.v_handle = v;
   native.v_handle->str = "Hello";
   Console::WriteLine("String in V: {0}", native.v_handle->str);
}
```

```Output
String in V: Hello
```

## <a name="see-also"></a>참고자료

[C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
