---
title: break 문 (C++)
ms.date: 11/04/2016
f1_keywords:
- break_cpp
helpviewer_keywords:
- break keyword [C++]
ms.assetid: 63739928-8985-4b05-93ce-016322e6da3d
ms.openlocfilehash: 3dda0b19fffaaf725ab363a0c4fe70d2ca54e3f7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62267717"
---
# <a name="break-statement-c"></a>break 문 (C++)

합니다 **중단** 바로 바깥쪽의 실행을 종료 하는 문을 루프 또는 표시 되는 조건문입니다. 제어는 종료된 문 뒤의 문이 있는 경우 전달됩니다.

## <a name="syntax"></a>구문

```
break;
```

## <a name="remarks"></a>설명

**나누기** 문을 사용 하는 조건부를 사용 하 여 [전환](../cpp/switch-statement-cpp.md) 문을 합니다 [수행](../cpp/do-while-statement-cpp.md), [에 대 한](../cpp/for-statement-cpp.md), 및 [하는동안](../cpp/while-statement-cpp.md) loop 문을 사용 합니다.

에 **전환** 문을 **중단** 문 외부에서 다음 문을 실행 하려면 프로그램이 **전환** 문. 없이 **중단** 문, 일치에서 모든 문 **사례** 의 끝에 레이블을 **전환** 문을 포함 하 여는 **기본**절을이 실행 됩니다.

루프에는 **나누기** 문은 가장 가까운 바깥쪽의 실행을 종료 **수행**, **에 대 한**, 또는 **하는 동안** 문. 종료된 문 뒤에 문이 있는 경우 제어가 해당 문으로 전달됩니다.

중첩 된 문 내의 합니다 **중단** 문을 종료 합니다 **수행**, **에 대 한**, **전환**, 또는 **하는동안**문을 둘러싼입니다. 사용할 수는 **반환** 또는 **goto** 좀 더 많이 제어를 전송 하는 문은 중첩 된 구조입니다.

## <a name="example"></a>예제

다음 코드를 사용 하는 방법을 보여 줍니다 합니다 **중단** 문에서 **에 대 한** 루프입니다.

```cpp
#include <iostream>
using namespace std;

int main()
{
    // An example of a standard for loop
    for (int i = 1; i < 10; i++)
    {
        if (i == 4) {
            break;
        }
        cout << i << '\n';
    }

    // An example of a range-based for loop
int nums []{1, 2, 3, 4, 5, 6, 7, 8, 9, 10};

    for (int i : nums) {
        if (i == 4) {
            break;
        }
        cout << i << '\n';
    }
}
```

```Output
In each case:
1
2
3
```

다음 코드를 사용 하는 방법을 보여 줍니다 **나누기** 에 **하는 동안** 루프 및 **수행** 루프입니다.

```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 0;

    while (i < 10) {
        if (i == 4) {
            break;
        }
        cout << i << '\n';
        i++;
    }

    i = 0;
    do {
        if (i == 4) {
            break;
        }
        cout << i << '\n';
        i++;
    } while (i < 10);
}
```

```Output
In each case:
0123
```

다음 코드를 사용 하는 방법을 보여 줍니다 **중단** switch 문에서 합니다. 사용 해야 합니다 **중단** 사용 하지 않는 경우 각 사례를 별도로 처리 하려는 경우 항상에서 **중단**가 다음 case로 코드 실행 합니다.

```cpp
#include <iostream>
using namespace std;

enum Suit{ Diamonds, Hearts, Clubs, Spades };

int main() {

    Suit hand;
    . . .
    // Assume that some enum value is set for hand
    // In this example, each case is handled separately
    switch (hand)
    {
    case Diamonds:
        cout << "got Diamonds \n";
        break;
    case Hearts:
        cout << "got Hearts \n";
        break;
    case Clubs:
        cout << "got Clubs \n";
        break;
    case Spades:
        cout << "got Spades \n";
        break;
    default:
          cout << "didn't get card \n";
    }
    // In this example, Diamonds and Hearts are handled one way, and
    // Clubs, Spades, and the default value are handled another way
    switch (hand)
    {
    case Diamonds:
    case Hearts:
        cout << "got a red card \n";
        break;
    case Clubs:
    case Spades:
    default:
        cout << "didn't get a red card \n";
    }
}
```

## <a name="see-also"></a>참고자료

[점프 문](../cpp/jump-statements-cpp.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[continue 문](../cpp/continue-statement-cpp.md)