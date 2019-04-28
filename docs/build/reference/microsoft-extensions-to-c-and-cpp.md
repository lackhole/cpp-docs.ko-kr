---
title: C에 대 한 Microsoft 확장 하 고C++
ms.date: 06/14/2018
helpviewer_keywords:
- or_eq operator
- ~ operator, extensions to C/C++
- '& operator, extensions to C/C++'
- '&= operator'
- iso646.h header
- Xor operator, Microsoft extensions to C/C++
- '!= operator'
- '! operator, extension to C++'
- Or operator, Microsoft extensions to C/C++
- ^ operator, extensions to C/C++
- ^= operator, C++ extensions
- xor_eq operator
- and_eq operator
- Microsoft extensions to C/C++
- '|= operator'
- '|| operator'
- And operator, extensions to C/C++
- NOT operator
- '&& operator'
- extensions, C language
- Visual C++, extensions to C/C++
- '| operator, extensions'
- not_eq operator
- Visual C, Microsoft extensions
- extensions
- compl method
ms.assetid: e811a74a-45ba-4c00-b206-2f2321b8689a
ms.openlocfilehash: dab8ac23be8b66ca84c57514c6c04e94dddebaae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62321191"
---
# <a name="microsoft-extensions-to-c-and-c"></a>C에 대 한 Microsoft 확장 하 고C++

Visual C++는 다음과 같이 ANSI C 및 ANSI C++ 표준을 확장합니다.

## <a name="keywords"></a>키워드

여러 키워드가 추가되었습니다. 목록의 [키워드](../../cpp/keywords-cpp.md), 선행 밑줄이 두 개 있는 키워드에 시각적 개체는 C++ 확장 합니다.

## <a name="out-of-class-definition-of-static-const-integral-or-enum-members"></a>정적 const 정수 (또는 열거형) 멤버의 클래스 정의

표준에서 (**/Za**), 여기에 나와 있는 것 처럼 데이터 멤버에 대 한 클래스의 확장 정의 확인 해야 합니다.

```cpp
class CMyClass  {
   static const int max = 5;
   int m_array[max];
}
// . . .
const int CMyClass::max;   // out of class definition
```

아래 **/Ze**, 클래스의 확장 정의 static, const integral 및 const enum 데이터 멤버에 대 한 선택 사항입니다. static 및 const인 열거형 및 정수만 클래스에서 이니셜라이저를 포함할 수 있습니다. 초기화 식은 const 식이어야 합니다.

오류를 한 클래스 정의 헤더 파일 및 헤더 파일 포함 되어 여러 소스 파일에 제공 된 경우를 방지 하려면 사용 하 여 [selectany](../../cpp/selectany.md)합니다. 예를 들어:

```cpp
__declspec(selectany) const int CMyClass::max = 5;
```

## <a name="casts"></a>캐스트

C++ 컴파일러 및 C 컴파일러는 모두 이러한 종류의 비ANSI 캐스트를 지원합니다.

- l-value를 생성하기 위한 비ANSI 캐스트. 예를 들어:

   ```C
   char *p;
   (( int * ) p )++;
   ```

   > [!NOTE]
   > 이 확장은 C 언어에서만 사용할 수 있습니다. C++ 코드에서 다음 ANSI C 표준 형식을 사용해서 다른 형식에 대한 포인터인 것처럼 포인터를 수정할 수 있습니다.

   앞의 예제는 ANSI C 표준을 따르도록 다음과 같이 다시 작성할 수 있습니다.

   ```C
   p = ( char * )(( int * )p + 1 );
   ```

- 데이터 포인터에 대한 함수 포인터의 비ANSI 캐스트. 예를 들어:

   ```C
   int ( * pfunc ) ();
   int *pdata;
   pdata = ( int * ) pfunc;
   ```

   동일한 캐스트를 수행하고 ANSI 호환성을 유지 관리하려면 데이터 포인터로 캐스팅하기 전에 함수 포인터를 `uintptr_t`로 캐스팅할 수 있습니다.

   ```C
   pdata = ( int * ) (uintptr_t) pfunc;
   ```

## <a name="variable-length-argument-lists"></a>가변 길이 인수 목록

C++ 컴파일러와 C 컴파일러는 모두 대신 형식을 제공하는 함수 정의 다음에 인수의 변수 수를 지정하는 함수 선언자를 지정합니다.

```cpp
void myfunc( int x, ... );
void myfunc( int x, char * c )
{ }
```

## <a name="single-line-comments"></a>단일 줄 주석

C 컴파일러는 2개의 슬래시(//) 문자를 사용해서 시작되는 한 줄로 된 주석을 지원합니다.

```C
// This is a single-line comment.
```

## <a name="scope"></a>범위

C 컴파일러는 다음과 같은 범위 관련 기능을 지원합니다.

- Extern 항목 static으로 재정의 합니다.

   ```C
   extern int clip();
   static int clip()
   {}
   ```

- 동일한 범위 내에서 typedef 재정의 사용:

   ```C
   typedef int INT;
   typedef int INT;
   ```

- 함수 선언 자는 파일 범위를 가집니다.

   ```C
   void func1()
   {
       extern int func2( double );
   }
   int main( void )
   {
       func2( 4 );    //  /Ze passes 4 as type double
   }                  //  /Za passes 4 as type int
   ```

- 비상수 식을 사용해서 초기화된 블록 범위 변수의 사용:

   ```C
   int clip( int );
   int bar( int );
   int main( void )
   {
       int array[2] = { clip( 2 ), bar( 4 ) };
   }
   int clip( int x )
   {
       return x;
   }
   int bar( int x )
   {
       return x;
   }
   ```

## <a name="data-declarations-and-definitions"></a>데이터 선언 및 정의

C 컴파일러는 다음과 같은 데이터 선언 및 정의 기능을 지원합니다.

- 혼합된 문자 및 문자열 상수 이니셜라이저에:

   ```C
   char arr[5] = {'a', 'b', "cde"};
   ```

- 비트 필드는 기본 형식 이외의 **부호 없는 int** 하거나 **int 서명**합니다.

- 형식을 포함하지 않는 선언자:

   ```C
   x;
   int main( void )
   {
       x = 1;
   }
   ```

- 구조체 및 공용 구조체의 마지막 필드와 크기가 지정 되지 않은 배열:

   ```C
   struct zero
   {
       char *c;
       int zarray[];
   };
   ```

- 명명 되지 않은 (익명) 구조:

   ```C
   struct
   {
       int i;
       char *s;
   };
   ```

- 명명 되지 않은 (익명) 공용 구조체

   ```C
   union
   {
       int i;
       float fl;
   };
   ```

- 명명 되지 않은 멤버:

   ```C
   struct s
   {
      unsigned int flag : 1;
      unsigned int : 31;
   }
   ```

## <a name="intrinsic-floating-point-functions"></a>부동 소수점 내장 함수

모두 x86 C++ 컴파일러 및 C 컴파일러의 인라인 생성을 지원 합니다 `atan`, `atan2`, `cos`, `exp`, `log`를 `log10`, `sin`, `sqrt`, 및 `tan` 함수는 경우 **/Oi** 지정 됩니다. C 컴파일러의 경우, 이러한 내장 함수는 `errno` 변수를 설정하지 않기 때문에 이러한 내장 함수가 사용될 경우 ANSI 규칙을 준수할 수 없게 됩니다.

## <a name="passing-a-non-const-pointer-parameter-to-a-function-that-expects-a-reference-to-a-const-pointer-parameter"></a>Const 포인터 매개 변수에 대 한 참조를 예상 하는 함수에는 비 const 포인터 매개 변수를 전달

이 확장입니다 C++입니다. 사용 하 여이 코드는 컴파일되지 **/Ze**:

```cpp
typedef   int   T;

const T  acT = 9;      // A constant of type 'T'
const T* pcT = &acT;   // A pointer to a constant of type 'T'

void func2 ( const T*& rpcT )   // A reference to a pointer to a constant of type 'T'
{
   rpcT = pcT;
}

T*   pT;               // A pointer to a 'T'

void func ()
{
   func2 ( pT );      // Should be an error, but isn't detected
   *pT   = 7;         // Invalidly overwrites the constant 'acT'
}
```

## <a name="iso646h-not-enabled"></a>ISO646 합니다. H를 사용할 수 없습니다

아래 **/Ze**, 텍스트 서식의 다음 연산자를 사용 하려는 경우 iso646.h 포함 해야 합니다.

- & & (및)

- & = (and_eq)

- & (bitand)

- &#124;(bitor)

- ~ (compl)

- ! (not)

- ! = (not_eq)

- &#124;&#124;(또는)

- &#124;= (or_eq)

- ^ (비트 xor)

- ^= (xor_eq)

## <a name="address-of-string-literal-has-type-const-char--not-const-char--"></a>리터럴 문자열의 주소에 const char [형식에서 const char (*)]

다음 예제에서는 출력 `char const (*)[4]` 아래에서 **/Za**, 하지만 `char const [4]` 아래에 있는 **/Ze**합니다.

```cpp
#include <stdio.h>
#include <typeinfo>

int main()
{
    printf_s("%s\n", typeid(&"abc").name());
}
```

## <a name="see-also"></a>참고자료

- [/Za, /Ze(언어 확장 사용 안 함)](za-ze-disable-language-extensions.md)
- [MSVC 컴파일러 옵션](compiler-options.md)
- [MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
