---
title: 함수 오버로드
ms.date: 03/27/2019
helpviewer_keywords:
- function overloading [C++], about function overloading
- function overloading
- declaring functions [C++], overloading
ms.assetid: 3c9884cb-1d5e-42e8-9a49-6f46141f929e
ms.openlocfilehash: 6cc432e404a7a66de63cf87f0fe87f0ccdcb5d70
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154277"
---
# <a name="function-overloading"></a>함수 오버로드

C++에서는 동일한 범위에서 이름이 같은 함수를 둘 이상 지정할 수 있습니다. 이러한 함수가 호출 될 *오버 로드 된* 함수입니다. 오버 로드 된 함수를 사용 하면 함수의 경우, 형식 및 인수 개수에 따라 서로 다른 의미 체계를 제공할 수 있습니다.

예를 들어를 `print` 사용 하는 함수를 `std::string` 인수는 형식의 인수를 사용 하는 매우 다른 작업을 수행할 수 있습니다 **double**합니다. 오버 로드와 같은 이름을 사용 하는 것과 줄어듭니다 `print_string` 또는 `print_double`합니다. 컴파일 타임에 컴파일러는 오버 로드를 사용 하 여 호출자에 의해 전달 된 인수의 형식에 따라 선택 합니다.  호출 하는 경우 `print(42.0)`, 그런 다음 `void print(double d)` 함수가 호출 됩니다. 호출 하는 경우 `print("hello world")`, 그런 다음 `void print(std::string)` 오버 로드 호출 됩니다.

멤버 함수와 비멤버 함수를 오버 로드할 수 있습니다. 다음 표에서는 C++에서 동일한 범위에서 이름이 동일한 함수 그룹 간을 구별하는 데 사용하는 함수 선언 부분을 보여 줍니다.

### <a name="overloading-considerations"></a>오버로드 고려 사항

|함수 선언 요소|오버로드에 사용되는지 여부|
|----------------------------------|---------------------------|
|함수 반환 형식|아니요|
|인수의 수|예|
|인수 형식|예|
|줄임표의 존재 여부|예|
|이용 **typedef** 이름|아니요|
|지정하지 않은 배열 범위|아니요|
|**const** 또는 **volatile**|전체 함수에 적용 하는 경우 예|
|[Ref 한정자](#ref-qualifiers)|예|

## <a name="example"></a>예제

다음 예제에서는 오버로드 사용 방법을 보여 줍니다.

```cpp
// function_overloading.cpp
// compile with: /EHsc
#include <iostream>
#include <math.h>
#include <string>

// Prototype three print functions.
int print(std::string s);             // Print a string.
int print(double dvalue);            // Print a double.
int print(double dvalue, int prec);  // Print a double with a
                                     //  given precision.
using namespace std;
int main(int argc, char *argv[])
{
    const double d = 893094.2987;
    if (argc < 2)
    {
        // These calls to print invoke print( char *s ).
        print("This program requires one argument.");
        print("The argument specifies the number of");
        print("digits precision for the second number");
        print("printed.");
        exit(0);
    }

    // Invoke print( double dvalue ).
    print(d);

    // Invoke print( double dvalue, int prec ).
    print(d, atoi(argv[1]));
}

// Print a string.
int print(string s)
{
    cout << s << endl;
    return cout.good();
}

// Print a double in default precision.
int print(double dvalue)
{
    cout << dvalue << endl;
    return cout.good();
}

//  Print a double in specified precision.
//  Positive numbers for precision indicate how many digits
//  precision after the decimal point to show. Negative
//  numbers for precision indicate where to round the number
//  to the left of the decimal point.
int print(double dvalue, int prec)
{
    // Use table-lookup for rounding/truncation.
    static const double rgPow10[] = {
        10E-7, 10E-6, 10E-5, 10E-4, 10E-3, 10E-2, 10E-1,
        10E0, 10E1,  10E2,  10E3,  10E4, 10E5,  10E6 };
    const int iPowZero = 6;

    // If precision out of range, just print the number.
    if (prec < -6 || prec > 7)
    {
        return print(dvalue);
    }
    // Scale, truncate, then rescale.
    dvalue = floor(dvalue / rgPow10[iPowZero - prec]) *
        rgPow10[iPowZero - prec];
    cout << dvalue << endl;
    return cout.good();
}
```

앞의 코드에서는 파일 범위에서의 `print` 함수의 오버로드를 보여 줍니다.

기본 인수에는 함수 형식의 일부로 간주 되지 않습니다. 따라서 오버 로드 된 함수를 선택 합니다. 사용 되지 않습니다. 해당 기본 인수에만 다른 두 개의 함수는 오버로드된 함수 대신 여러 정의로 간주됩니다.

오버 로드 된 연산자에 대 한 기본 인수를 제공할 수 없습니다.

## <a name="argument-matching"></a>인수 일치

현재 범위에서 함수 호출에 제공된 인수와 가장 일치하는 함수 선언에 대해 오버로드된 함수가 선택됩니다. 적절한 함수를 찾으면 함수가 호출됩니다. 이 컨텍스트에서 "적합 한" 중 하나를 의미 합니다.

- 정확히 일치하는 항목을 찾았습니다.

- 간단한 변환을 수행했습니다.

- 정수 계열 확장이 수행되었습니다.

- 원하는 인수 형식에 대한 표준 변환이 존재합니다.

- 원하는 인수 형식에 대한 사용자 정의 변환(변환 연산자 또는 생성자)이 존재합니다.

- 줄임표로 나타낸 인수를 찾았습니다.

컴파일러가 각 인수의 후보 함수 집합을 만듭니다. 후보 함수는 해당 위치의 실제 인수를 형식 인수의 형식으로 변환할 수 있는 함수입니다.

"가장 일치하는 함수" 집합이 각 인수에 대해 빌드되고 모든 집합에 공통된 함수가 선택됩니다. 공통된 함수가 2개 이상일 경우 오버로드가 모호해지고 오류를 생성합니다. 최종적으로 선택되는 함수는 하나 이상의 인수에 대해 그룹의 다른 함수보다 일치합니다. 함수 호출이 없는 일반 우승자 인 경우 오류가 발생 합니다.

다음과 같은 선언이 있습니다. 알아보기 쉽게 함수가 `Variant 1`, `Variant 2` 및 `Variant 3`으로 표시되었습니다.

```cpp
Fraction &Add( Fraction &f, long l );       // Variant 1
Fraction &Add( long l, Fraction &f );       // Variant 2
Fraction &Add( Fraction &f, Fraction &f );  // Variant 3

Fraction F1, F2;
```

다음과 같은 문이 있습니다.

```cpp
F1 = Add( F2, 23 );
```

위의 문에서는 두 집합을 빌드합니다.

|설정 1: 분수 형식의 첫 번째 인수가 있는 후보 함수|설정 2 후보 함수가 있는 두 번째 인수가 변환할 수 형식 **int**|
|--------------------------------------------------------------------------|-----------------------------------------------------------------------------------|
|변형 1|변형 1 (**int** 변환할 수 있습니다 **긴** 표준 변환을 사용 하 여)|
|변형 3||

집합 2의 함수는 존재의 암시적 변환은 실제 매개 변수 형식에서 정식 매개 변수 형식 및 이러한 함수 간에 실제 매개 변수 형식을 정식 매개 변수 형식으로 변환 하는 "cost" 되는 함수는 가장 작은 값입니다.

두 집합의 공통된 함수는 변형 1입니다. 다음은 모호한 함수 호출의 예입니다.

```cpp
F1 = Add( 3, 6 );
```

앞의 함수 호출에서 다음 집합을 빌드합니다.

|설정 1: 후보 함수의 첫 번째 인수 형식의 있는 **int**|설정 2 후보 함수의 두 번째 인수 형식의 있는 **int**|
|---------------------------------------------------------------------|----------------------------------------------------------------------|
|변형 2 (**int** 변환할 수 있습니다 **긴** 표준 변환을 사용 하 여)|변형 1 (**int** 변환할 수 있습니다 **긴** 표준 변환을 사용 하 여)|

이러한 두 집합의 교집합이 비어 있으므로 컴파일러는 오류 메시지를 생성 합니다.

인수 일치를 사용 하는 함수에 대 한 *n* 기본 인수는 취급 *n*다른 개수의 인수를 사용 하 여 각 + 1 별도 함수입니다.

줄임표(...)는 와일드카드로 사용되어 실제 인수와 일치합니다. 해당 주의 사용 하 여 오버 로드 된 함수 집합을 디자인 하지 않도록 하는 경우 모호한 집합이 여러 개 발생할 수 있습니다.

> [!NOTE]
>  함수 호출에 도달할 때까지 오버 로드 된 함수의 모호성을 확인할 수 없습니다. 이때 함수 호출의 각 인수에 대해 집합이 빌드되고 명확한 오버로드가 존재하는지 여부를 확인할 수 있습니다. 즉, 특정 함수 호출에서 호출할 때까지 코드에 모호성이 남아있을 수 있습니다.

## <a name="argument-type-differences"></a>인수 형식 차이

오버로드된 함수는 다른 이니셜라이저를 사용하는 인수 형식을 구분합니다. 따라서, 주어진 형식의 인수와 그 형식에 대한 참조는 오버로드 목적의 형식과 동일한 것으로 간주됩니다. 이들은 같은 이니셜라이저를 사용하기 때문에 동일한 것으로 간주됩니다. 예를 들어, `max( double, double )`는 `max( double &, double & )`와 동일한 것으로 간주됩니다. 이러한 두 함수를 선언하면 오류가 발생합니다.

동일한 이유로, 함수에 의해 수정 된 형식의 인수 **상수** 또는 **volatile** 오버 로드를 위해 기본 형식을 다르게 취급 되지 않습니다.

그러나 메커니즘 오버 로드 함수를 구별할 수로 정규화 된 참조 **상수** 하 고 **volatile** 및 기본 형식에 대 한 참조. 다음 가능한 같은 코드 수 있습니다.

```cpp
// argument_type_differences.cpp
// compile with: /EHsc /W3
// C4521 expected
#include <iostream>

using namespace std;
class Over {
public:
   Over() { cout << "Over default constructor\n"; }
   Over( Over &o ) { cout << "Over&\n"; }
   Over( const Over &co ) { cout << "const Over&\n"; }
   Over( volatile Over &vo ) { cout << "volatile Over&\n"; }
};

int main() {
   Over o1;            // Calls default constructor.
   Over o2( o1 );      // Calls Over( Over& ).
   const Over o3;      // Calls default constructor.
   Over o4( o3 );      // Calls Over( const Over& ).
   volatile Over o5;   // Calls default constructor.
   Over o6( o5 );      // Calls Over( volatile Over& ).
}
```

### <a name="output"></a>출력

```Output
Over default constructor
Over&
Over default constructor
const Over&
Over default constructor
volatile Over&
```

에 대 한 포인터 **상수** 하 고 **volatile** 개체는 오버 로드를 위해도 기본 형식 포인터와 다르게 간주 됩니다.

## <a name="argument-matching-and-conversions"></a>인수 일치 및 변환

컴파일러가 실제 인수를 함수 선언의 인수와 일치시키려고 할 때 정확히 일치하는 항목이 없을 경우 표준 또는 사용자 정의 변환을 통해 올바른 형식을 가져오도록 할 수 있습니다. 변환 응용 프로그램에는 다음의 규칙이 적용됩니다.

- 둘 이상의 사용자 정의 변환이 포함된 변환 시퀀스는 고려하지 않습니다.

- 중간 변환을 제거하여 단축할 수 있는 변환 시퀀스는 고려하지 않습니다.

변환 결과 시퀀스가 있을 경우 이를 가장 일치하는 시퀀스라고 합니다. 형식의 개체를 변환 하는 방법은 여러 가지가 있습니다 **int** 입력할 **부호 없는 long** 표준 변환을 통한 (에 설명 된 [표준 변환](../cpp/standard-conversions.md)):

- 변환 **int** 하 **긴** 한 다음 **긴** 에 **부호 없는 long**합니다.

- 변환할 **int** 하 **부호 없는 long**합니다.

첫 번째 시퀀스가 기대한 목적을 달성 한다 하더라도 되지 가장 근접 한 순서-짧은 시퀀스가 존재할 합니다.

다음 표에서는 가장 일치하는 시퀀스를 결정하는 데 제한된 영향을 미치는 trivial 변환이라는 변환 그룹을 보여 줍니다. 이 표의 다음 목록에서는 시퀀스 선택에 영향을 미치는 trivial 변환이 이루어지는 인스턴스에 대해 설명합니다.

### <a name="trivial-conversions"></a>Trivial 변환

|변환 전 형식|변환 후 형식|
|-----------------------|---------------------|
|*type-name*|*type-name* **&**|
|*type-name* **&**|*type-name*|
|*type-name* **[ ]**|*type-name* __\*__|
|*type-name* **(** *argument-list* **)**|**(** __\*__ *type-name* **) (** *argument-list* **)**|
|*type-name*|**const** *type-name*|
|*type-name*|**volatile** *type-name*|
|*type-name* __\*__|**const** *type-name* __\*__|
|*type-name* __\*__|**volatile** *type-name* __\*__|

변환이 시도되는 시퀀스는 다음과 같습니다.

1. 정확한 일치. 함수가 호출되는 형식과 함수 프로토타입에서 선언된 형식 간 정확한 일치는 항상 가장 좋은 일치입니다. trivial 변환 시퀀스는 정확히 일치하는 항목으로 분류됩니다. 그러나 이러한 변환 통하지 않는 시퀀스 변환 시키는 시퀀스 보다 나은 간주 됩니다.

   - 에 대 한 포인터에 대 한 포인터에서 **상수** (`type` <strong>\*</strong> 하 **const** `type` <strong>\*</strong> ).

   - 에 대 한 포인터에 대 한 포인터에서 **volatile** (`type` <strong>\*</strong> 하 **volatile** `type` <strong>\*</strong>).

   - 참조에 대 한 참조에서 **상수** (`type` **&** 하 **const** `type` **&**).

   - 참조에 대 한 참조에서 **volatile** (`type` **&** 하 **volatile** `type` **&**).

1. 승격을 통한 일치. 정수 계열 승격에서 변환을 포함 하는 정확한 일치로 분류 되지 않은 모든 시퀀스 **float** 에 **double**, 및 trivial 변환이 승격을 통한 일치로 분류 됩니다. 승격을 통한 일치는 정확한 일치만큼 양호하지는 않지만 표준 변환을 통한 일치에 비해 좋습니다.

1. 표준 변환을 통한 일치. 표준 변환과 trivial 변환만 포함 포함하는, 정확한 일치 또는 승격을 통한 일치로 분류되지 않은 시퀀스는 표준 변환을 통한 일치로 분류됩니다. 이 범주에는 다음 규칙이 적용됩니다.

   - 포인터에서 파생 클래스를 직접 또는 간접 기본 클래스에 대 한 포인터로 변환이을 변환 하기 위한 것이 좋습니다 `void *` 또는 `const void *`합니다.

   - 파생 클래스에 대한 포인터에서 기본 클래스에 대한 포인터로 변환할 경우 기본 클래스가 직접 기본 클래스에 가까울수록 더 잘 일치합니다. 클래스 계층 구조가 다음 그림과 같다고 가정합니다.

![기본 변환에 대 한 그래프](../cpp/media/vc391t1.gif "기본 변환에 대 한 그래프") <br/>
기본 변환을 보여 주는 그래프

`D*` 형식에서 `C*` 형식으로 변환하는 것이 `D*` 형식에서 `B*` 형식으로 변환하는 것보다 좋습니다. 마찬가지로 `D*` 형식에서 `B*` 형식으로 변환하는 것이 `D*` 형식에서 `A*` 형식으로 변환하는 것보다 좋습니다.

이 규칙은 참조 변환에 동일하게 적용됩니다. `D&` 형식에서 `C&` 형식으로 변환하는 것이 `D&` 형식에서 `B&` 형식 등으로 변환하는 것보다 좋습니다.

이 규칙은 멤버 포인터 변환에 동일하게 적용됩니다. `T D::*` 형식에서 `T C::*` 형식으로 변환하는 것이 `T D::*` 형식에서 `T B::*` 형식 등으로 변환하는 것보다 좋습니다. 여기서 `T`는 멤버 형식입니다.

앞의 규칙은 지정된 파생 경로에만 적용됩니다. 다음 그림에 표시된 그래프를 살펴보세요.

![여러&#45;기본 변환을 보여 주는 상속](../cpp/media/vc391t2.gif "여러&#45;기본 변환을 보여 주는 상속") <br/>
기본 변환을 보여 주는 다중 상속 그래프

`C*` 형식에서 `B*` 형식으로 변환하는 것이 `C*` 형식에서 `A*` 형식으로 변환하는 것보다 좋습니다. 이유는 이들이 동일한 경로에 있고 `B*`가 더 가깝기 때문입니다. 그러나 형식에서 변환 `C*` 형식으로 `D*` 형식으로 변환 하는 것이 좋습니다 없는 `A*`; 변환은 서로 다른 경로 따라 됩니다.

1. 사용자 정의 변환을 통한 일치. 이 시퀀스는 정확히 일치, 승격을 통한 일치 또는 표준 변환을 통한 일치로 분류 될 수 없습니다. 이 시퀀스가 사용자 정의 변환을 통한 일치로 분류되려면 사용자 정의 변환, 표준 변환 또는 trivial 변환이 포함되어야 합니다. 사용자 정의 변환을 통한 일치는 줄임표를 통한 일치보다 좋은 것으로 간주되지만 표준 변환을 통한 일치만큼 양호하지는 않습니다.

1. 줄임표를 통한 일치. 선언에서 줄임표와 일치하는 모든 시퀀스는 줄임표를 통한 일치로 분류됩니다. 것이 가장 취약 한 일치 합니다.

기본 승격 또는 변환이 존재하지 않는 경우 사용자 정의 변환이 적용됩니다. 이러한 변환은 일치하는 인수의 형식을 기준으로 선택됩니다. 다음 코드를 살펴보세요.

```cpp
// argument_matching1.cpp
class UDC
{
public:
   operator int()
   {
      return 0;
   }
   operator long();
};

void Print( int i )
{
};

UDC udc;

int main()
{
   Print( udc );
}
```

클래스에 대 한 사용 가능한 사용자 정의 변환을 `UDC` 형식에서 됩니다 **int** 형식과 **긴**합니다. 따라서 컴파일러가 일치하는 개체 형식을 위한 변환을 고려합니다(`UDC`). 변환할 **int** 존재 하며 선택 되었습니다.

일치하는 인수를 처리하는 동안 인수 및 사용자 정의 변환 결과 모두에 표준 변환을 적용할 수 있습니다. 따라서 다음 코드가 작동합니다.

```cpp
void LogToFile( long l );
...
UDC udc;
LogToFile( udc );
```

위의 예제에서는 사용자 정의 변환이 **긴 연산자**를 변환 하기 위해 호출 되 `udc` 형식으로 **긴**합니다. 경우 형식으로 사용자 정의 변환이 **긴** 같다고 정의 변환은 진행 다음과 같습니다: 형식 `UDC` 형식으로 변환 된 **int** 사용자 정의 변환을 사용 하 여 합니다. 다음 유형에 서 표준 변환을 **int** 입력할 **긴** 선언의 인수와 일치 하도록 적용 되었을 합니다.

모든 사용자 정의 변환에 해야 하는 인수 일치 하는 경우 표준 변환은 가장 일치 하는 평가할 때 사용 되지 않습니다. 둘 이상의 후보 함수는 사용자 정의 변환에 필요한 경우에 함수 간주 됩니다. 예를 들어:

```cpp
// argument_matching2.cpp
// C2668 expected
class UDC1
{
public:
   UDC1( int );  // User-defined conversion from int.
};

class UDC2
{
public:
   UDC2( long ); // User-defined conversion from long.
};

void Func( UDC1 );
void Func( UDC2 );

int main()
{
   Func( 1 );
}
```

두 버전 모두 `Func` 형식으로 변환 하는 사용자 정의 변환이 필요 **int** 클래스 형식 인수입니다. 가능한 변환은 다음과 같습니다.

- 형식에서 변환할 **int** 형식으로 `UDC1` (사용자 정의 변환).

- 형식에서 변환할 **int** 형식으로 **긴**; 형식으로 다음 `UDC2` (2 단계 변환).

두 번째는 표준 변환과 사용자 정의 변환에 필요한 경우에 두 변환은 여전히 간주 됩니다.

> [!NOTE]
>  사용자 정의 변환은 생성 또는 초기화(함수 변환)에 의한 변환으로 간주됩니다. 두 메서드가 최상의 일치일 경우 동일하다고 간주됩니다.

## <a name="argument-matching-and-the-this-pointer"></a>인수 일치 및 this 포인터

클래스 멤버 함수의으로 선언 되었는지 여부에 따라 다르게 처리 됩니다 **정적**합니다. 비정적 함수에 제공 하는 암시적 인수가 있으므로 합니다 **이** 포인터 비정적 함수는 정적 함수 보다 인수를 하나 더 있는 것으로 간주 됩니다;이 고, 그렇지 선언 된 동일 하 게 합니다.

위해서는 이러한 비정적 멤버 함수는 암시적 **이** 포인터는 함수가 호출 되는 개체 형식에 일치, 오버 로드 된 연산자에 대 한 첫 번째 인수는 개체와 일치 하는 필요 합니다 연산자를 적용 하는 중입니다. (오버 로드 된 연산자에 대 한 자세한 내용은 참조 하세요. [오버 로드 된 연산자](../cpp/operator-overloading.md).)

오버 로드 된 함수의 다른 인수와 달리 임시 개체가 소개 되 고 일치 하는 동안 변환이 시도 되는 **이** 포인터 인수입니다.

경우는 `->` 멤버 선택 연산자는 클래스의 멤버 함수에 액세스 하는 데 사용 됩니다 `class_name`의 **이** 포인터 인수 형식이 `class_name * const`합니다. 멤버로 선언 된 경우 **상수** 또는 **volatile**, 유형은 `const class_name * const` 및 `volatile class_name * const`각각.

명시적 `.` 주소 연산자가 개체 이름 앞에 추가된다는 점을 제외하면 `&` 멤버 선택 연산자는 동일하게 작동합니다. 다음 예제에서는 그 작동 방식을 보여 줍니다.

```cpp
// Expression encountered in code
obj.name

// How the compiler treats it
(&obj)->name
```

`->*`의 왼쪽 피연산자와 `.*`(멤버에 대한 포인터) 연산자는 인수 일치와 관련하여 `.` 및 `->`(멤버 선택) 연산자와 동일한 방식으로 처리됩니다.

## <a name="ref-qualifiers"></a> 멤버 함수에서 ref-qualifier

Ref 한정자를 확인 하는지 여부를 가리키는 개체를 기준으로 멤버 함수를 오버 로드할 수 **이** rvalue 또는 lvalue입니다.  이 기능은을 데이터에 대 한 포인터 액세스를 제공 하지 않으려는 시나리오에서 불필요 한 복사 작업을 방지 하려면 사용할 수 있습니다. 예를 들어, 클래스를 가정 `C` 생성자를 통해 일부 데이터를 초기화 하 고 멤버 함수에 해당 데이터의 복사본을 반환 합니다. `get_data()`합니다. 형식의 개체가 `C` 이 컴파일러는 선택한 소멸 되려고 할는 rvalue를 `get_data() &&` 복사 하는 것이 아니라 데이터를 이동 하는 오버 로드 합니다.

```cpp
#include <iostream>
#include <vector>

using namespace std;

class C
{

public:
    C() {/*expensive initialization*/}
    vector<unsigned> get_data() &
    {
        cout << "lvalue\n";
        return _data;
    }
    vector<unsigned> get_data() &&
    {
        cout << "rvalue\n";
        return std::move(_data);
    }

private:
    vector<unsigned> _data;
};

int main()
{
    C c;
    auto v = c.get_data(); // get a copy. prints "lvalue".
    auto v2 = C().get_data(); // get the original. prints "rvalue"
    return 0;
}
```

## <a name="restrictions-on-overloading"></a>오버 로드에 대 한 제한

여러 제한은 사용할 수 있는 오버로드된 함수 집합을 관리합니다.

- 오버로드된 함수 집합의 임의의 두 함수에는 서로 다른 인수 목록이 있어야 합니다.

- 반환 형식을 기준으로 동일한 형식의 인수 목록을 가진 함수를 오버 로드하면 오류가 발생합니다.

     **Microsoft 전용**

오버 로드할 수 있습니다 **new 연산자** 만에 반환 형식 기준-구체적으로 지정 하는 메모리 모델 한정자를 기준으로 합니다.

**Microsoft 전용 종료**

- 멤버 함수는 하나의 정적 및 다른 비정적을 기반으로 단독으로 오버 로드할 수 없습니다.

- **typedef** 선언은 새 형식을 정의 하지 않으면 기존 형식에 대 한 동의어를 초래 합니다. 이러한 오버 로드 메커니즘에 영향을 주지 않습니다. 다음 코드를 살펴보세요.

    ```cpp
    typedef char * PSTR;

    void Print( char *szToPrint );
    void Print( PSTR szToPrint );
    ```

   위의 두 함수에는 동일한 인수 목록이 있습니다. `PSTR` 형식에 대 한 동의어가 `char *`합니다. 멤버 범위에서 이 코드를 사용하면 오류가 발생합니다.

- 열거 형식은 고유한 형식이며 오버로드된 함수 사이를 구분하는 데 사용할 수 있습니다.

- 형식 "배열" 및 "포인터" 오버 로드 된 함수 사이 대해서만 구별 하기 위해 동일한 배열에 단독으로 차원이 것으로 간주 됩니다. 이유는 이러한 오버 로드 된 함수 충돌 및 오류 메시지를 생성 합니다.

    ```cpp
    void Print( char *szToPrint );
    void Print( char szToPrint[] );
    ```

   다차원 배열의 경우 둘째 및 이후의 모든 차원은 형식의 일부로 간주됩니다. 따라서 이들은 오버로드된 함수를 구별하는 데 사용됩니다.

    ```cpp
    void Print( char szToPrint[] );
    void Print( char szToPrint[][7] );
    void Print( char szToPrint[][9][42] );
    ```

## <a name="overloading-overriding-and-hiding"></a>오버 로드, 재정의 및 숨기기

동일한 범위에서 동일한 이름의 두 함수 선언은 같은 함수 또는 오버로드된 두 개별 함수를 참조할 수 있습니다. 선언의 인수 목록에 동일한 형식의 인수가 포함되어 있으면(이전 단원 참조) 함수 선언은 같은 함수를 참조하고, 그렇지 않으면 오버로드를 사용하여 선택된 서로 다른 두 함수를 참조합니다.

클래스 범위는 엄격 하 게 준수 합니다. 기본 클래스에서 선언 된 함수를 함수로 동일한 범위에서 되지 따라서 파생된 클래스에서 선언 합니다. 파생 클래스는 기본 클래스에서 가상 함수와 동일한 이름을 가진 파생된 클래스에서 함수를 선언 하는 경우 *재정의* 기본 클래스 함수입니다. 자세한 내용은 [가상 함수](../cpp/virtual-functions.md)를 참조하세요.

기본 클래스 함수가으로 'virtual', 선언 되지 경우 파생된 클래스 함수 라고 *숨기기* 것입니다. 재정의 및 숨기기에 오버 로드와 다릅니다.

블록 범위는 엄격 하 게 준수 합니다. 파일 범위에서 선언 된 함수를 함수로 동일한 범위에서 되지 따라서 로컬로 선언 합니다. 로컬로 선언된 함수의 이름이 파일 범위에서 선언된 함수의 이름과 같을 경우 로컬로 선언된 함수는 오버로드를 유발하는 대신 파일 범위의 함수를 숨깁니다. 예를 들어:

```cpp
// declaration_matching1.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
void func( int i )
{
    cout << "Called file-scoped func : " << i << endl;
}

void func( char *sz )
{
   cout << "Called locally declared func : " << sz << endl;
}

int main()
{
   // Declare func local to main.
   extern void func( char *sz );

   func( 3 );   // C2664 Error. func( int ) is hidden.
   func( "s" );
}
```

위의 코드에서는 `func` 함수의 두 정의를 보여 줍니다. 형식의 인수를 사용 하는 정의 `char *` 로컬인 `main` 때문에 **extern** 문입니다. 형식의 인수를 사용 하는 정의 따라서 **int** 숨겨져 및 첫 번째 호출은 `func` 는 오류가 발생 합니다.

오버로드된 멤버 함수의 경우 함수의 버전마다 서로 다른 액세스 권한을 부여할 수 있습니다. 이러한 함수는 여전히 바깥쪽 클래스의 범위에 있는 것으로 간주되므로 오버로드된 함수입니다. 멤버 함수 `Deposit`가 오버로드되는 다음 코드를 살펴보겠습니다. 한 버전은 public이고 다른 버전은 private입니다.

이 샘플의 목적은 입금을 하려면 올바른 암호가 필요한 `Account` 클래스를 제공하는 것입니다. 오버 로드를 사용 하 여 수행 됩니다.

에 대 한 호출 `Deposit` 에서 `Account::Deposit` private 멤버 함수를 호출 합니다. 이 호출은 올바릅니다 있으므로 `Account::Deposit` 멤버 함수 및 클래스의 private 멤버에 대 한 액세스 권한이 있습니다.

```cpp
// declaration_matching2.cpp
class Account
{
public:
   Account()
   {
   }
   double Deposit( double dAmount, char *szPassword );

private:
   double Deposit( double dAmount )
   {
      return 0.0;
   }
   int Validate( char *szPassword )
   {
      return 0;
   }

};

int main()
{
    // Allocate a new object of type Account.
    Account *pAcct = new Account;

    // Deposit $57.22. Error: calls a private function.
    // pAcct->Deposit( 57.22 );

    // Deposit $57.22 and supply a password. OK: calls a
    //  public function.
    pAcct->Deposit( 52.77, "pswd" );
}

double Account::Deposit( double dAmount, char *szPassword )
{
   if ( Validate( szPassword ) )
      return Deposit( dAmount );
   else
      return 0.0;
}
```

## <a name="see-also"></a>참고자료

[함수(C++)](../cpp/functions-cpp.md)