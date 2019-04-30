---
title: 인라인 함수(C++)
ms.date: 10/09/2018
f1_keywords:
- __forceinline_cpp
- __inline_cpp
- inline_cpp
- __inline
- _inline
- __forceinline
- _forceinline
helpviewer_keywords:
- inline functions [C++], class members
ms.assetid: 355f120c-2847-4608-ac04-8dda18ffe10c
ms.openlocfilehash: 55cf598877c2447e0f80e783b53b290699042b8b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400593"
---
# <a name="inline-functions-c"></a>인라인 함수(C++)

클래스 선언의 본문에 정의된 함수는 인라인 함수입니다.

## <a name="example"></a>예제

다음 클래스 선언에서 `Account` 생성자는 인라인 함수입니다. 멤버 함수는 `GetBalance`, `Deposit`, 및 `Withdraw` 으로 지정 되지 않은 **인라인** 있지만 인라인 함수로 구현할 수 있습니다.

```cpp
// Inline_Member_Functions.cpp
class Account
{
public:
    Account(double initial_balance) { balance = initial_balance; }
    double GetBalance();
    double Deposit( double Amount );
    double Withdraw( double Amount );
private:
    double balance;
};

inline double Account::GetBalance()
{
    return balance;
}

inline double Account::Deposit( double Amount )
{
    return ( balance += Amount );
}

inline double Account::Withdraw( double Amount )
{
    return ( balance -= Amount );
}
int main()
{
}
```

> [!NOTE]
>  없이 선언 된 함수를 클래스 선언에는 **인라인** 키워드입니다. 합니다 **인라인** 클래스 선언에서 키워드를 지정할 수 있습니다; 결과 동일 합니다.

주어진 인라인 멤버 함수는 모든 컴파일 단위에서 동일한 방식으로 선언되어야 합니다. 이 제한 사항으로 인해 인라인 함수는 마치 인스턴스화된 함수처럼 동작합니다. 또한 인라인 함수의 정의는 정확히 하나만 있어야 합니다.

해당 함수에 대 한 정의가 포함 되어 있지 않으면 외부 링크를 기본적으로 클래스 멤버 함수는 **인라인** 지정자입니다. 앞의 예제를 보여 줍니다는 이러한 함수가 필요 하지 명시적으로 선언 될 합니다 **인라인** 지정자를 사용 하 여 **인라인** 함수에서 정의에 따라 인라인 함수입니다. 그러나이 유효 하지 않은 함수로 다시 선언 **인라인** 해당 함수를 호출한 후입니다.

## <a name="inline-inline-and-forceinline"></a>인라인 __inline 및 \__forceinline

합니다 **인라인** 하 고 **__inline** 지정자는 함수 본문의 복사본을 함수가 호출 되는 각 위치에 삽입 하도록 컴파일러에 지시 합니다.

삽입(인라인 확장 또는 인라인 처리라고 함)은 컴파일러의 비용/이익 분석에서 수익성이 있는 것으로 표시되는 경우에만 수행됩니다. 인라인 확장을 사용하면 더 큰 코드 크기를 줄여 함수 호출 오버헤드를 줄일 수 있습니다.

합니다 **__forceinline** 키워드는 비용/이익 분석을 재정의 하 고 대신 프로그래머의 판단에 의존 합니다. 사용할 때는 주의 **__forceinline**합니다. 무분별 하 게 활용 **__forceinline** 수 한계 성능 향상만을 사용 하 여 더 큰 코드가 생성, 일부 경우에도 성능이 손실 (으로 인해 페이징 증가 더 큰 실행 파일의 예를 들어).

인라인 함수를 사용하면 함수 호출과 연관된 오버헤드가 제거되어 프로그램 속도가 더 빨라질 수 있습니다. 인라인으로 확장된 함수에는 일반 함수에 사용할 수 없는 코드 최적화가 적용됩니다.

컴파일러는 인라인 확장 옵션과 키워드를 제안으로 처리합니다. 함수가 인라인으로 처리된다는 보장은 없습니다. 컴파일러에서 특정 함수를 인라인에도 강제할 수는 없습니다 합니다 **__forceinline** 키워드입니다. 사용 하 여 컴파일하면 **/clr**, 컴파일러는 인라인 처리 하지 않습니다 함수의 경우 함수에 적용 된 보안 특성.

합니다 **인라인** 키워드는 에서만 사용할 수 있습니다 C++합니다. **__inline** 하 고 **__forceinline** 키워드는 C에서 사용할 수 있습니다 하 고 C++. 이전 버전과 호환성에 대 한 **_inline** 하 고 **_forceinline** 은 **__inline**, 및 **__forceinline** 하지 않으면 컴파일러 옵션 [/Za \(언어 확장 사용 안 함)](../build/reference/za-ze-disable-language-extensions.md) 지정 됩니다.

합니다 **인라인** 키워드는 컴파일러가 인라인 확장을 다른 사용자는 것이 좋습니다. 그러나 컴파일러는 함수의 별도 인스턴스를 만들고(인스턴스화) 인라인으로 코드를 삽입하는 대신 표준 호출 링크를 만들 수 있습니다. 다음은 이런 상황이 발생할 수 있는 두 가지 경우입니다.

- 재귀 함수.

- 변환 단위의 다른 위치에서 포인터를 통해 참조되는 함수.

이러한 이유 때문에 방해가 될 수 인라이닝 *다른으로*, 컴파일러의 판단에 따라 하면 종속 되어서는 안를 **인라인** 인라인 될 함수 지정자.

일반 함수에서처럼 인라인 함수에 대한 인수의 계산 순서는 정의되어 있지 않습니다. 실제로 일반 함수 호출 프로토콜을 사용하여 전달될 때 인수가 계산되는 순서와 다를 수 있습니다.

합니다 [/Ob](../build/reference/ob-inline-function-expansion.md) 컴파일러 최적화 옵션 인라인 함수 확장이 실제로 발생 하는지 여부를 확인 하는 것입니다.

[/LTCG](../build/reference/ltcg-link-time-code-generation.md) 크로스 모듈 인라인 소스 코드에서 요청 되었는지 여부에 관계 없이 수행 합니다.

### <a name="example-1"></a>예제 1

```cpp
// inline_keyword1.cpp
// compile with: /c
inline int max( int a , int b ) {
   if( a > b )
      return a;
   return b;
}
```

클래스의 멤버 함수는 사용 하 여 인라인으로 선언할 수 있습니다 합니다 **인라인** 키워드 또는 클래스 정의 내에서 함수 정의 배치 합니다.

### <a name="example-2"></a>예제 2

```cpp
// inline_keyword2.cpp
// compile with: /EHsc /c
#include <iostream>
using namespace std;

class MyClass {
public:
   void print() { cout << i << ' '; }   // Implicitly inline
private:
   int i;
};
```

### <a name="microsoft-specific"></a>Microsoft 전용

합니다 **__inline** 키워드 같습니다 **인라인**합니다.

있어도 **__forceinline**, 컴파일러가 모든 상황에서 인라인 코드를 수 없습니다. 다음과 같은 경우 컴파일러에서 함수를 인라인 처리할 수 없습니다.

- 함수 또는 해당 호출자가 /Ob0(디버그 빌드에 대한 기본 옵션)으로 컴파일됩니다.

- 함수 및 호출자가 다양한 형식의 예외 처리(한 경우 C++ 예외 처리, 다른 경우 구조적 예외 처리)를 사용합니다.

- 함수에 가변 인수 목록이 있습니다.

- /Og, /Ox, /O1 또는 /O2로 컴파일되지 않은 경우 함수에서 인라인 어셈블리를 사용합니다.

- 함수는 재귀 및 하지 않습니다 **#pragma inline_recursion**합니다. pragma를 사용하면 재귀 함수가 기본 깊이 16번 호출로 인라인 처리됩니다. 사용 하 여 인라인 처리 깊이 줄이려면 [inline_depth](../preprocessor/inline-depth.md) pragma입니다.

- 가상 함수이며 실제로 호출됩니다. 가상 함수에 대한 직접 호출은 인라인 처리할 수 있습니다.

- 프로그램에서 함수의 주소를 사용하고 함수에 대한 포인터를 통해 호출합니다. 주소가 사용된 함수에 대한 직접 호출은 인라인 처리할 수 있습니다.

- 함수는도 표시 합니다 [naked](../cpp/naked-cpp.md) [__declspec](../cpp/declspec.md) 한정자입니다.

컴파일러에 인라인 할 수 없습니다. 함수를 사용 하 여 선언 **__forceinline**, 경우를 제외 하 고 수준 1 경고를 생성 합니다.

- 함수는 /Od 또는 /Ob0을 사용 하 여 컴파일됩니다. 이상 인라인 이러한 경우에 필요 합니다.

- 함수는 포함 된 라이브러리나 다른 변환 단위에 외부적으로 정의 되어 있거나 가상 호출 대상 또는 간접 호출 대상 인 합니다. 컴파일러는 현재 변환 단위에서 찾을 수 없다는 인라인되지 않은 코드를 식별할 수 없습니다.

재귀 함수는 지정 된 깊이까지 인라인으로 대체할된 수는 [inline_depth](../preprocessor/inline-depth.md) pragma에는 최대 16 번 호출 합니다. 해당 깊이 이후 재귀 함수 호출은 함수의 인스턴스 호출로 처리됩니다.  인라인 추론에서 재귀 함수를 검사하는 깊이는 16을 초과할 수 없습니다. 합니다 [inline_recursion](../preprocessor/inline-recursion.md) pragma 확장에서 현재 함수의 인라인 확장을 제어 합니다. 참조 된 [인라인 함수 확장](../build/reference/ob-inline-function-expansion.md) (/ Ob) 관련된 정보에 대 한 컴파일러 옵션입니다.

**Microsoft 전용 종료**

사용 하 여 대 한 자세한 내용은 합니다 **인라인** 지정자를 참조 하세요.

- [인라인 클래스 멤버 함수](../cpp/inline-functions-cpp.md)

- [dllexport 및 dllimport로 인라인 C++ 함수 정의](../cpp/defining-inline-cpp-functions-with-dllexport-and-dllimport.md)

## <a name="when-to-use-inline-functions"></a>인라인 함수 사용 시기

인라인 함수는 전용 데이터 멤버에 액세스하는 것처럼 작은 함수에서 가장 적합하게 사용됩니다. 한 줄 또는 두 줄 "접근자" 함수의 주요 목적은 개체에 대한 상태 정보를 반환하는 것입니다. 간단한 함수는 함수 호출의 오버헤드에 민감합니다. 긴 함수는 호출/반환 시퀀스에서 상당히 시간이 적게 소요되며 인라이닝으로 인한 이점이 크지 않습니다.

`Point` 클래스를 다음과 같이 정의할 수 있습니다.

```cpp
// when_to_use_inline_functions.cpp
class Point
{
public:
    // Define "accessor" functions as
    //  reference types.
    unsigned& x();
    unsigned& y();
private:
    unsigned _x;
    unsigned _y;
};

inline unsigned& Point::x()
{
    return _x;
}
inline unsigned& Point::y()
{
    return _y;
}
int main()
{
}
```

이러한 클래스의 두 접근자 함수를 지정 하는 클라이언트에서 비교적 일반적인 작업은 좌표 조작이 가정 하 고 (`x` 하 고 `y` 앞의 예제에서)로 **인라인** 일반적으로 저장 합니다 에 대 한 오버 헤드:

- 함수 호출(개체의 주소를 스택에 전달 및 배치하는 매개 변수 포함)

- 호출자의 스택 프레임의 보존

- 새 스택 프레임 설정

- 반환 값 전달

- 기존 스택 프레임 복원

- 반환

## <a name="inline-functions-vs-macros"></a>인라인 함수 및 매크로

컴파일할 때 호출 시점에 함수 코드가 확장된다는 점에서 인라인 함수는 매크로와 비슷하지만 인라인 함수는 컴파일러에 의해 구문이 분석되며 매크로는 전처리기에 의해 확장됩니다. 그 결과 몇 가지 중요한 차이가 생깁니다.

- 인라인 함수는 일반 함수에 적용되는 모든 형식 안전성 프로토콜을 따릅니다.

- 포함 한다는 다른 함수와 동일한 구문을 사용 하 여 인라인 함수는 지정 된 **인라인** 함수 선언에서 키워드입니다.

- 인라인 함수에 인수로 전달된 식은 한 번 계산됩니다. 매크로에 인수로 전달된 식은 경우에 따라 여러 번 계산할 수 있습니다.

다음 예제에서는 소문자를 대문자로 변환하는 매크로를 보여 줍니다.

```cpp
// inline_functions_macro.c
#include <stdio.h>
#include <conio.h>

#define toupper(a) ((a) >= 'a' && ((a) <= 'z') ? ((a)-('a'-'A')):(a))

int main() {
   char ch;
   printf_s("Enter a character: ");
   ch = toupper( getc(stdin) );
   printf_s( "%c", ch );
}
//  Sample Input:  xyz
// Sample Output:  Z
```

식의 의도 `toupper(getc(stdin))` 문자를 콘솔 장치에서 읽어야 하는 (`stdin`) 및 필요한 경우 대문자로 변환 합니다.

매크로 구현으로 인해 문자가 "a"보다 크거나 같은지 확인하기 위해 한 번, "z"보다 작거나 같은지 확인하기 위해 한 번 `getc`를 실행합니다. 해당 범위에 속할 경우 문자를 대문자로 변환하기 위해 `getc`가 다시 실행됩니다. 즉, 문자를 1개만 기다려야 하는데 프로그램이 문자를 2개나 3개 기다립니다.

인라인 함수는 전에 설명한 문제를 해결합니다.

```cpp
// inline_functions_inline.cpp
#include <stdio.h>
#include <conio.h>

inline char toupper( char a ) {
   return ((a >= 'a' && a <= 'z') ? a-('a'-'A') : a );
}

int main() {
   printf_s("Enter a character: ");
   char ch = toupper( getc(stdin) );
   printf_s( "%c", ch );
}
```

```Output
Sample Input: a
Sample Output: A
```

## <a name="see-also"></a>참고자료

[noinline](../cpp/noinline.md)<br/>
[auto_inline](../preprocessor/auto-inline.md)