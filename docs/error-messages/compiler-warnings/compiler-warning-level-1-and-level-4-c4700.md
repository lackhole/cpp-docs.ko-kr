---
title: 컴파일러 경고(수준 1 및 수준 4) C4700
ms.date: 02/21/2018
f1_keywords:
- C4700
helpviewer_keywords:
- C4700
ms.assetid: 2da0deb4-77dd-4b05-98d3-b78d74ac4ca7
ms.openlocfilehash: fa3326bd5ab495dbc4c54130bb168422eb827dce
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300299"
---
# <a name="compiler-warning-level-1-and-level-4-c4700"></a>컴파일러 경고(수준 1 및 수준 4) C4700

> 초기화 되지 않은 지역 변수 '*이름을*' 사용

지역 변수 *이름을* 되었습니다 *사용*에서 즉, 읽기, 설정 되기 전에 값이 할당 되었습니다. C에서 및 C++를 기본적으로는 로컬 변수가 초기화 되지 않습니다. 초기화 되지 않은 변수 값을 포함할 수 있습니다 및 용도 정의 되지 않은 동작이 발생 합니다. 경고 C4700 거의 항상 프로그램에서 예기치 않은 결과 또는 충돌을 일으킬 수 있는 버그를 나타냅니다.

이 문제를 해결 하려면 선언 된 경우 로컬 변수를 초기화 하거나 사용 하기 전에 값을 할당 수 있습니다. 해당 주소를 포인터 매개 변수로 전달 되는 경우 또는 참조 매개 변수로 전달 되는 변수를 초기화 하려면 함수를 사용할 수 있습니다.

## <a name="example"></a>예제

이 샘플에서는 변수 t, u 및 v 사용 하는 경우 초기화 됩니다 하 고 발생할 수 있는 가비지 값의 종류를 표시 하려면 먼저 C4700를 생성 합니다. 변수 x, y 및 z 수행 하므로 사용 하기 전에 초기화 된다고 경고를 발생 하지:

```cpp
// c4700.cpp
// compile by using: cl /EHsc /W4 c4700.cpp
#include <iostream>

// function takes an int reference to initialize
void initialize(int& i)
{
    i = 21;
}

int main()
{
    int s, t, u, v;   // Danger, uninitialized variables

    s = t + u + v;    // C4700: t, u, v used before initialization
    std::cout << "Value in s: " << s << std::endl;

    int w, x;         // Danger, uninitialized variables
    initialize(x);    // fix: call function to init x before use
    int y{10};        // fix: initialize y, z when declared
    int z{11};        // This C++11 syntax is recommended over int z = 11;

    w = x + y + z;    // Okay, all values initialized before use
    std::cout << "Value in w: " << w << std::endl;
}
```

초기화 되지 않은이 코드 실행, t, u 및 v 경우 고 s에 대 한 출력 예측할 수 없습니다.

```Output
Value in s: 37816963
Value in w: 42
```
