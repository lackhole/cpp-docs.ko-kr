---
title: 할당 연산자
ms.date: 03/27/2019
f1_keywords:
- =
- '*='
- /=
- '%='
- +=
- -=
- <<=
- '>>='
- '&='
- ^=
- '|='
helpviewer_keywords:
- operators [C++], assignment
- assignment operators [C++], C++
- '&= operator'
- ^= operator
- += operator
- '>>= operator'
- '|= operator'
- operator>>=
- '*= operator'
- '%= operator'
- ^= operator
- operator >>=
- = operator
- -= operator
- /= operator
- <<= operator
ms.assetid: b028cf35-2ff1-4f14-9027-fd53ebec8aa0
ms.openlocfilehash: 758c82f02d2b113f6c750f7f0ede662c97b646b0
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565482"
---
# <a name="assignment-operators"></a>할당 연산자

## <a name="syntax"></a>구문

*expression* *assignment-operator* *expression*

*할당 연산자* : 중<br/>
&nbsp;&nbsp;&nbsp;&nbsp;<strong>=&nbsp;&nbsp;&nbsp;*=&nbsp;&nbsp;&nbsp;/=&nbsp;&nbsp;&nbsp;%=&nbsp;&nbsp;&nbsp;+=&nbsp;&nbsp;&nbsp;-=&nbsp;&nbsp;&nbsp;\<\<=&nbsp;&nbsp;&nbsp;>>=&nbsp;&nbsp;&nbsp;&=&nbsp;&nbsp;&nbsp;^=&nbsp;&nbsp;&nbsp;\|=</strong>

## <a name="remarks"></a>설명

할당 연산자는 왼쪽 피연산자가 지정된 개체에 값을 저장합니다. 할당 연산의 두 종류가 있습니다.

1. *단순 할당*, 두 번째 피연산자의 값은 첫 번째 피연산자가 지정한 개체에 저장 합니다.

1. *복합 할당*는 산술, 시프트 또는 비트 연산 결과 저장 하기 전에 수행 됩니다.

다음 표에 있는 모든 할당 연산자(= 연산자 제외)는 복합 할당 연산자입니다.

### <a name="assignment-operators-table"></a>할당 연산자 표

|연산자|의미|
|--------------|-------------|
|**=**|첫 번째 피연산자에서 지정한 개체에 두 번째 피연산자의 값을 저장합니다(단순 할당).|
|**\*=**|첫 번째 피연산자의 값과 두 번째 피연산자의 값을 곱하여 첫 번째 피연산자가 지정한 개체에 결과를 저장합니다.|
|**/=**|첫 번째 피연산자의 값을 두 번째 피연산자의 값으로 나누어 첫 번째 피연산자가 지정한 개체에 결과를 저장합니다.|
|**%=**|두 번째 피연산자의 값에서 지정한 첫 번째 피연산자의 모듈러스를 가져와서 첫 번째 피연산자가 지정한 개체에 결과를 저장합니다.|
|**+=**|두 번째 연산자의 값과 첫 번째 연산자의 값을 더하여 첫 번째 피연산자가 지정한 개체에 결과를 저장합니다.|
|**-=**|첫 번째 피연산자의 값에서 두 번째 피연산자의 값을 빼서 첫 번째 피연산자가 지정한 개체에 결과를 저장합니다.|
|**<\<=**|두 번째 피연산자의 값에서 지정한 비트 수만큼 첫 번째 피연산자의 값을 왼쪽으로 이동하여 첫 번째 피연산자가 지정한 개체에 결과를 저장합니다.|
|**>>=**|두 번째 피연산자의 값에서 지정한 비트 수만큼 첫 번째 피연산자의 값을 오른쪽으로 이동하여 첫 번째 피연산자가 지정한 개체에 결과를 저장합니다.|
|**&=**|첫 번째 및 두 번째 피연산자의 비트 AND를 구하여 첫 번째 피연산자가 지정한 개체에 결과를 저장합니다.|
|**^=**|첫 번째 및 두 번째 피연산자의 비트 배타적 OR를 구하여 첫 번째 피연산자가 지정한 개체에 결과를 저장합니다.|
|**\|=**|첫 번째 및 두 번째 피연산자의 비트 포함 OR를 구하여 첫 번째 피연산자가 지정한 개체에 결과를 저장합니다.|

### <a name="operator-keywords"></a>연산자 키워드

세 복합 할당 연산자는 동일한 텍스트를 갖고 있습니다. 다음 창이 여기에 포함됩니다.

|연산자|해당 항목|
|--------------|----------------|
|**&=**|`and_eq`|
|**\|=**|`or_eq`|
|**^=**|`xor_eq`|

프로그램에서 이러한 연산자 키워드에 액세스 하는 방법은 두 가지: 헤더 파일을 포함 `iso646.h`를 사용 하 여 컴파일해야 합니다 [/Za](../build/reference/za-ze-disable-language-extensions.md) (언어 확장명 사용 안 함) 컴파일러 옵션.

## <a name="example"></a>예제

```cpp
// expre_Assignment_Operators.cpp
// compile with: /EHsc
// Demonstrate assignment operators
#include <iostream>
using namespace std;
int main() {
   int a = 3, b = 6, c = 10, d = 0xAAAA, e = 0x5555;

   a += b;      // a is 9
   b %= a;      // b is 6
   c >>= 1;      // c is 5
   d |= e;      // Bitwise--d is 0xFFFF

   cout  << "a = 3, b = 6, c = 10, d = 0xAAAA, e = 0x5555" << endl
         << "a += b yields " << a << endl
         << "b %= a yields " << b << endl
         << "c >>= 1 yields " << c << endl
         << "d |= e yields " << hex << d << endl;
}
```

## <a name="simple-assignment"></a>단순 할당

단순 할당 연산자 (**=**) 첫 번째 피연산자가 지정한 개체에 저장할 두 번째 피연산자의 값입니다. 두 개체가 모두 산술 형식인 경우 값을 저장하기 전에 오른쪽 피연산자가 왼쪽 피연산자의 형식으로 변환됩니다.

개체의 **const** 및 **volatile** 은 형식의 l-value에 형식을 할당할 수 있습니다 **volatile** 또는 둘 다 **const** 또는 **volatile**합니다.

클래스 형식 (구조체, 공용 구조체 및 클래스 형식)의 개체에 할당 이라는 함수에 의해 수행 됩니다 `operator=`합니다. 이 연산자 함수의 기본 동작은 비트 복사를 수행하는 것이지만, 이 동작은 오버로드된 연산자를 사용하여 수정할 수 있습니다. 참조 [연산자 오버 로드](../cpp/operator-overloading.md) 자세한 내용은 합니다. 또한 클래스 형식을 가질 수 있습니다 *복사 할당* 하 고 *이동 할당* 연산자입니다. 자세한 내용은 [복사 생성자 및 복사 할당 연산자](copy-constructors-and-copy-assignment-operators-cpp.md) 하 고 [이동 생성자 및 이동 할당 연산자](move-constructors-and-move-assignment-operators-cpp.md)합니다.

지정된 기본 클래스에서 명확히 파생된 모든 클래스의 개체는 기본 클래스의 개체에 할당될 수 있습니다. 하지만 반대의 경우는 성립되지 않습니다. 파생 클래스에서 기본 클래스로의 암시적 변환이 있지만 기본 클래스에서 파생 클래스로의 암시적 변환은 없기 때문입니다. 예를 들어:

```cpp
// expre_SimpleAssignment.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;
class ABase
{
public:
    ABase() { cout << "constructing ABase\n"; }
};

class ADerived : public ABase
{
public:
    ADerived() { cout << "constructing ADerived\n"; }
};

int main()
{
    ABase aBase;
    ADerived aDerived;

    aBase = aDerived; // OK
    aDerived = aBase; // C2679
}
```

참조 형식에 대한 할당은 참조가 가리키는 개체에 할당이 수행되는 것처럼 작동합니다.

클래스 형식 개체의 경우 할당은 초기화와 다릅니다. 할당과 초기화가 어떻게 다를 수 있는지를 알아보려면 다음 코드를 살펴보세요.

```cpp
UserType1 A;
UserType2 B = A;
```

위의 코드에서는 이니셜라이저를 보여 줍니다. 여기에서는 `UserType2` 형식의 인수를 사용하는 `UserType1`의 생성자를 호출합니다. 다음 코드에서

```cpp
UserType1 A;
UserType2 B;

B = A;
```

아래의 할당 문은

```cpp
B = A;
```

다음과 같은 결과 중 하나를 생성할 수 있습니다.

- 함수 호출 `operator=` 에 대 한 `UserType2`제공 `operator=` 와 함께 제공 되는 `UserType1` 인수입니다.

- 명시적 변환 함수 `UserType1::operator UserType2`를 호출합니다(이러한 함수가 있는 경우).

- `UserType2::UserType2` 인수를 사용하고 결과를 복사하는 생성자 `UserType1`를 호출합니다(이러한 생성자가 있는 경우).

## <a name="compound-assignment"></a>복합 할당

에 표시 된 복합 대입 연산자를는 [할당 연산자 표](#assignment-operators-table), 형식에 지정 된 *e1* *op*= *e2*, 여기서 *e1* 를 수정 가능한 l-value가 아닌 **const** 형식 및 *e2* 다음 중 하나입니다.

- 산술 형식

- 포인터를 하는 경우 *op* 됩니다 **+** 또는 **-**

합니다 *e1* *op*= *e2* 폼 처럼 *e1* **=** *e1* *op* *e2*, 하지만 *e1* 한 번만 평가 됩니다.

열거 형식에 대한 복합 할당은 오류 메시지를 생성합니다. 왼쪽 피연산자가 포인터 형식일 경우 오른쪽 피연산자가 포인터 형식이거나 0으로 계산되는 상수 식이어야 합니다. 왼쪽 피연산자가 정수 계열 형식일 경우 오른쪽 피연산자가 포인터 형식이 아니어야 합니다.

## <a name="result-of-assignment-operators"></a>할당 연산자의 결과

대입 연산자는 할당된 후 왼쪽 피연산자에서 지정한 개체 값을 반환합니다. 결과 형식은 왼쪽 피연산자의 형식입니다. 할당 식의 결과는 항상 l-value입니다. 이러한 연산자는 오른쪽에서 왼쪽으로 결합됩니다. 왼쪽 피연산자는 수정 가능한 l-value여야 합니다.

ANSI C에서 할당 식의 결과는 l-value가 아닙니다. 따라서 올바른 C++ 식 `(a += b) += c`가 C에서는 올바르지 않습니다.

## <a name="see-also"></a>참고자료

[이항 연산자가 있는 식](../cpp/expressions-with-binary-operators.md)<br/>
[C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C 할당 연산자](../c-language/c-assignment-operators.md)
