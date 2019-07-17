---
title: parallel_unsequenced_policy 클래스
ms.date: 04/18/2019
f1_keywords:
- execution/std::execution::parallel_unsequenced_policy
ms.openlocfilehash: 92b4e3ce3743fdd3d5ba112a333b2306829b95d4
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268785"
---
# <a name="parallelunsequencedpolicy-class"></a>parallel_unsequenced_policy 클래스

병렬 알고리즘 오버 로드를 명확히 구분 하는 병렬 알고리즘의 실행은 병렬 처리 되 고 벡터화 있습니다 나타내려면 고유 형식으로 사용 합니다.

## <a name="syntax"></a>구문

```cpp
class execution::parallel_unsequenced_policy;
```

## <a name="remarks"></a>설명

병렬 알고리즘을 실행 하는 동안 합니다 `execution::parallel_unsequenced_policy` 확인할 수 없는 예외를 통해 종료 되는 요소 액세스 함수를 호출 하는 경우 정책을 `terminate()` 호출 됩니다.
