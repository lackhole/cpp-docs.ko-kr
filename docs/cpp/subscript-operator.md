---
title: 첨자 연산자]
ms.date: 11/04/2016
f1_keywords:
- '[]'
helpviewer_keywords:
- operators [C++], subscript
- postfix operators [C++]
- '[] operator'
- subscript operator [C++], syntax
ms.assetid: 69c31494-52da-4dd0-8bbe-6ccbfd50f197
ms.openlocfilehash: 2d55c18d2c9faa1a704bea129f2551937e76133c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62266896"
---
# <a name="subscript-operator-"></a>첨자 연산자]

## <a name="syntax"></a>구문

```
postfix-expression [ expression ]
```

## <a name="remarks"></a>설명

뒤에 첨자 연산자, 후 위 식 (수 있는 기본 식) **[ ]**, 배열 인덱싱 지정 합니다.

C + 관리 되는 배열에 대 한 자세한 + CLI 참조 [배열](../extensions/arrays-cpp-component-extensions.md)합니다.

나타내는 값을 일반적으로 *후 위 식* 은 배열 식별자와 같은 포인터 값, 및 *식* 은 정수 계열 값 (열거형된 형식 포함). 그러나 구문적 요구 사항은 식 중 하나가 포인터 형식이고 다른 하나는 정수 계열 형식이어야 한다는 것 밖에 없습니다. 에 정수 값을 사용할 수 있으므로 합니다 *후 위 식* 위치 및 포인터 값에서 대괄호 안에 수 합니다 *식* 또는 첨자 위치 합니다. 다음과 같은 코드 조각을 생각해 봅시다.

```cpp
int nArray[5] = { 0, 1, 2, 3, 4 };
cout << nArray[2] << endl;            // prints "2"
cout << 2[nArray] << endl;            // prints "2"
```

위의 예제에서 `nArray[2]` 식은 `2[nArray]`와 동일합니다. 이유는 첨자 식의 결과 `e1[e2]` 로 지정 됩니다.

`*((e2) + (e1))`

식에서 생성 된 주소 아닙니다 *e2* 주소의 바이트 *e1*합니다. 대신 주소의 크기가 조정 되는 배열의 다음 개체가 생성 *e2*합니다. 예를 들어:

```cpp
double aDbl[2];
```

주소 `aDb[0]` 하 고 `aDb[1]` 8 바이트 떨어져-형식의 개체 크기인 **double**합니다. 개체 형식에 따른이 크기 조정을 자동으로 수행 됩니다는 C++ 언어에 정의 된 [가감 연산자](../cpp/additive-operators-plus-and.md) 포인터 형식의 피연산자의 덧셈과 뺄셈 설명 되어 있습니다.

첨자 식에는 다음과 같이 여러 첨자가 있을 수도 있습니다.

*expression1* **[** *expression2* **] [** *expression3* **]** ...

첨자 식은 왼쪽에서 오른쪽으로 연결합니다. 맨 왼쪽 첨자 식인 *expression1* **[** *expression2* **]** 가 먼저 계산됩니다. *expression1* 및 *expression2*를 추가한 결과인 주소는 포인터 식을 형성합니다. 그런 다음 이 포인터 식에 *expression3*이 추가되어 새 포인터 식을 형성하고 마지막 첨자 식이 추가될 때까지 계속됩니다. 간접 참조 연산자 (<strong>\*</strong>) 최종 포인터 값이 배열 형식을 해결 하지 않으면 마지막 첨자 식이 계산 된 후 적용 됩니다.

여러 첨자가 포함된 식은 다차원 배열의 요소를 참조합니다. 다차원 배열은 요소가 배열인 배열입니다. 예를 들어 3차원 배열의 첫 번째 요소는 2차원 배열입니다. 다음 예제에서는 간단한 2차원 문자 배열을 선언 및 초기화합니다.

```cpp
// expre_Subscript_Operator.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
#define MAX_ROWS 2
#define MAX_COLS 2

int main() {
  char c[ MAX_ROWS ][ MAX_COLS ] = { { 'a', 'b' }, { 'c', 'd' } };
  for ( int i = 0; i < MAX_ROWS; i++ )
     for ( int j = 0; j < MAX_COLS; j++ )
        cout << c[ i ][ j ] << endl;
}
```

## <a name="positive-and-negative-subscripts"></a>양수 및 음수 아래 첨자

배열의 첫 번째 요소는 요소 0입니다. 범위는 C++ 에서 배열이 *배열*[0] 하 *배열*[*크기* -1]입니다. 하지만 C++는 양수 및 음수 첨자를 지원합니다. 음수 첨자는 배열 경계 내에 속해야 하며, 그렇지 않으면 결과를 예측할 수 없습니다. 다음 코드에서는 양수 및 음수 배열 첨자를 보여줍니다.

```cpp
#include <iostream>
using namespace std;

int main() {
    int intArray[1024];
    for (int i = 0, j = 0; i < 1024; i++)
    {
        intArray[i] = j++;
    }

    cout << intArray[512] << endl;   // 512

    cout << 257[intArray] << endl;   // 257

    int *midArray = &intArray[512];  // pointer to the middle of the array

    cout << midArray[-256] << endl;  // 256

    cout << intArray[-256] << endl;  // unpredictable, may crash
}
```

256 주소를 가리키기 때문에 마지막 줄의 음수 첨자는 런타임 오류를 생성할 수 있습니다 **int** 배열의 원점 보다 메모리에 낮은 위치 합니다. 포인터 `midArray` 의 중간으로 초기화 됩니다 `intArray`; 되므로 (위험) 이지만 둘 다 양수 및 음수 배열 인덱스에서 사용 하도록 합니다. 배열 첨자 오류는 컴파일 시간 오류를 발생시키지 않지만 예측할 수 없는 결과를 생성합니다.

첨자 연산자는 가환적입니다. 따라서 *배열*[*인덱스*] 및 *인덱스*[*배열*] 첨자 오랫동안 동등한 것으로 보장 됩니다 연산자 오버 로드 되지 않았는지 (참조 [오버 로드 된 연산자](../cpp/operator-overloading.md)). 첫 번째 형태가 가장 일반적인 코딩 방법이지만, 둘 다 작동합니다.

## <a name="see-also"></a>참고자료

[후위 식](../cpp/postfix-expressions.md)<br/>
[C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[배열](../cpp/arrays-cpp.md)<br/>
[1차원 배열](../c-language/one-dimensional-arrays.md)<br/>
[다차원 배열](../c-language/multidimensional-arrays-c.md)<br/>
