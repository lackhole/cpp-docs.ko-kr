---
title: const (C++)
ms.date: 11/04/2016
f1_keywords:
- const_cpp
helpviewer_keywords:
- const keyword [C++]
ms.assetid: b21c0271-1ad0-40a0-b21c-5e812bba0318
ms.openlocfilehash: 759ee503acb12f6c1a30fbbfaf87a8f66433e571
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154752"
---
# <a name="const-c"></a>const (C++)

데이터 선언을 수정할 때 합니다 **const** 키워드는 개체 또는 변수는 수정할 수를 지정 합니다.

## <a name="syntax"></a>구문

```
const declaration ;
member-function const ;
```

## <a name="const-values"></a>const 값

합니다 **const** 변수 값을 상수 이며 프로그래머가 수정 하지 못하도록 컴파일러가 키워드를 지정 합니다.

```cpp
// constant_values1.cpp
int main() {
   const int i = 5;
   i = 10;   // C3892
   i++;   // C2105
}
```

C++를 사용할 수 있습니다는 **const** 대신 키워드를 [#define](../preprocessor/hash-define-directive-c-cpp.md) 상수 값을 정의할 전처리기 지시문입니다. 로 정의 된 값 **const** 형식 검사가 적용 되며 상수 식 대신 사용할 수 있습니다. C++를 사용 하 여 배열의 크기를 지정할 수 있습니다는 **const** 같이 변수:

```cpp
// constant_values2.cpp
// compile with: /c
const int maxarray = 255;
char store_char[maxarray];  // allowed in C++; not allowed in C
```

C에서 상수 값은 기본적으로 외부 링크로 설정되므로 소스 파일에만 나타날 수 있습니다. C++에서 상수 값은 기본적으로 내부 링크로 설정되므로 헤더 파일에 나타날 수 있습니다.

합니다 **const** 키워드는 포인터 선언에서 에서도 사용할 수 있습니다.

```cpp
// constant_values3.cpp
int main() {
   char *mybuf = 0, *yourbuf;
   char *const aptr = mybuf;
   *aptr = 'a';   // OK
   aptr = yourbuf;   // C3892
}
```

으로 선언 된 변수에 대 한 포인터 **상수** 으로 선언 된 포인터에만 할당할 수 있습니다 **const**합니다.

```cpp
// constant_values4.cpp
#include <stdio.h>
int main() {
   const char *mybuf = "test";
   char *yourbuf = "test2";
   printf_s("%s\n", mybuf);

   const char *bptr = mybuf;   // Pointer to constant data
   printf_s("%s\n", bptr);

   // *bptr = 'a';   // Error
}
```

상수 데이터에 대한 포인터를 함수 매개 변수로 사용하여 함수가 포인터를 통해 전달된 매개 변수를 수정하지 못하게 할 수 있습니다.

로 선언 되는 개체에 대 한 **const**, 있습니다 수만 상수 멤버 함수를 호출 합니다. 이렇게 하면 상수 개체가 절대로 수정되지 않습니다.

```cpp
birthday.getMonth();    // Okay
birthday.setMonth( 4 ); // Error
```

비상수 개체의 경우에는 상수 또는 비상수 멤버 함수를 호출할 수 있습니다. 사용 하 여 멤버 함수를 오버 로드할 수도 있습니다는 **const** 키워드입니다; 이렇게 하면 다른 버전의 상수 및 비상수 개체에 대 한 호출 수는 함수입니다.

생성자 또는 소멸자를 선언할 수 없습니다는 **const** 키워드입니다.

## <a name="const-member-functions"></a>const 멤버 함수

사용 하는 멤버 함수를 선언 합니다 **const** 키워드 함수를 호출 하는 개체를 수정 하지 않는 "읽기 전용" 함수로 지정 합니다. 상수 멤버 함수는 비정적 데이터 멤버를 수정 하거나 상수가 아닌는 함수 멤버를 호출할 수 없습니다. 상수 멤버 함수를 선언 하려면 배치 합니다 **const** 인수 목록의 닫는 괄호 뒤 키워드입니다. 합니다 **const** 키워드는 선언과 정의 둘 다 필요 합니다.

```cpp
// constant_member_function.cpp
class Date
{
public:
   Date( int mn, int dy, int yr );
   int getMonth() const;     // A read-only function
   void setMonth( int mn );   // A write function; can't be const
private:
   int month;
};

int Date::getMonth() const
{
   return month;        // Doesn't modify anything
}
void Date::setMonth( int mn )
{
   month = mn;          // Modifies data member
}
int main()
{
   Date MyDate( 7, 4, 1998 );
   const Date BirthDate( 1, 18, 1953 );
   MyDate.setMonth( 4 );    // Okay
   BirthDate.getMonth();    // Okay
   BirthDate.setMonth( 4 ); // C2662 Error
}
```

## <a name="c-and-c-const-differences"></a>C 및 C++ const 차이점

변수를 선언 하는 경우 **const** C 소스 코드 파일에서 같이:

```cpp
const int i = 2;
```

그런 다음 이 변수를 아래와 같이 다른 모듈에서 사용할 수 있습니다.

```cpp
extern const int i;
```

하지만에서 동일한 결과를 얻으려면 C++를 선언 해야 하 **const** 변수의:

```cpp
extern const int i = 2;
```

선언 하려는 경우는 **extern** 변수를 C++ 사용 하 여 C 소스 코드 파일에서 사용 하기 위해 소스 코드 파일:

```cpp
extern "C" const int x=10;
```

C++ 컴파일러에 의한 이름 변환을 방지해야 합니다.

## <a name="remarks"></a>설명

멤버 함수의 매개 변수 목록을 따를 때 합니다 **const** 키워드 지정 함수가 호출 되는 개체를 수정 하지 않습니다.

에 대 한 자세한 **const**, 다음 항목을 참조 하세요.

- [const 및 volatile 포인터](../cpp/const-and-volatile-pointers.md)

- [형식 한정자 (C 언어 참조)](../c-language/type-qualifiers.md)

- [volatile](../cpp/volatile-cpp.md)

- [#define](../preprocessor/hash-define-directive-c-cpp.md)

## <a name="see-also"></a>참고자료

[C++ 키워드](../cpp/keywords-cpp.md)