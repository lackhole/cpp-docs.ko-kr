---
title: 컴파일러 경고 (수준 4) C4456
ms.date: 11/04/2016
f1_keywords:
- C4456
helpviewer_keywords:
- C4456
ms.assetid: 5ab39fc1-0e19-461b-842b-4da80560b044
ms.openlocfilehash: 006628721598d838070412c895f64b9a8d3de4e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391506"
---
# <a name="compiler-warning-level-4-c4456"></a>컴파일러 경고 (수준 4) C4456

> 선언의 '*식별자*' 이전 로컬 선언을 숨깁니다.

선언의 *식별자* 로컬 범위에 동일한 이름의 이전 로컬 선언의 선언을 숨깁니다. 이 경고를 사용 하면에 대 한 참조는 알고 *식별자* 로컬 범위에 로컬로 선언 된 버전으로 의도 하지 않을 수도 있고 이전 로컬 하지 확인 합니다. 이 문제를 해결 하려면 다른 로컬 이름과 충돌 하지 않는 지역 변수 이름을 지정 해야 하는 것이 좋습니다.

## <a name="example"></a>예제

루프 제어 변수 때문에 다음 샘플에서는 C4456 `int x` 및 지역 변수 `double x` 에서 `member_fn` 이름이 같습니다. 이 문제를 해결 하려면 로컬 변수에 대 한 서로 다른 이름을 사용 합니다.

```cpp
// C4456_hide.cpp
// compile with: cl /W4 /c C4456_hide.cpp

struct S {
    void member_fn(unsigned u) {
        double x = 0;
        for (int x = 0; x < 10; ++x) {  // C4456
            u += x; // uses local int x
        }
        x += u; // uses local double x
    }
} s;
```
