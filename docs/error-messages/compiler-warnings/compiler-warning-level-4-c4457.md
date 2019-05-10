---
title: 컴파일러 경고 (수준 4) C4457
ms.date: 11/04/2016
f1_keywords:
- C4457
helpviewer_keywords:
- C4457
ms.assetid: 02fd149a-917d-4f67-97a6-eb714572271f
ms.openlocfilehash: 11307ddc3b13a9cd9b36f1ee927082104792b07f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391441"
---
# <a name="compiler-warning-level-4-c4457"></a>컴파일러 경고 (수준 4) C4457

> 선언의 '*식별자*' 숨깁니다 함수 매개 변수

선언의 *식별자* 로컬 범위에서 동일 하 게 명명 된 함수 매개 변수의 선언을 숨깁니다. 이 경고를 사용 하면에 대 한 참조는 알고 *식별자* 로컬 범위에 없습니다 매개 변수를 의도 하지 않을 수도 있고는 로컬로 선언 된 버전을 확인 합니다. 이 문제를 해결 하려면 매개 변수 이름과 충돌 하지 않는 지역 변수 이름을 지정 해야 하는 것이 좋습니다.

## <a name="example"></a>예제

때문에 다음 샘플에서는 C4457 매개 변수 `x` 및 지역 변수 `x` 에서 `member_fn` 이름이 같습니다. 이 문제를 해결 하려면 다른 이름을 매개 변수 및 지역 변수를 사용 합니다.

```cpp
// C4457_hide.cpp
// compile with: cl /W4 /c C4457_hide.cpp

struct S {
    void member_fn(unsigned x) {
        double a = 0;
        for (int x = 0; x < 10; ++x) {  // C4457
            a += x; // uses local x
        }
        a += x; // uses parameter x
    }
} s;
```
