---
title: parallel_policy 클래스
ms.date: 04/18/2019
f1_keywords:
- execution/std::execution::parallel_policy
ms.openlocfilehash: 7bb2b095a50e664dfc585e0bd4aaa608a6ad8e95
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268965"
---
# <a name="parallelpolicy-class"></a>parallel_policy 클래스

고유 형식으로 병렬 알고리즘 오버 로드 명확 하 게 병렬 알고리즘의 실행을 병렬 처리할 수를 표시 하는 데 사용 합니다.

## <a name="syntax"></a>구문

```cpp
class execution::parallel_policy;
```

## <a name="remarks"></a>설명

병렬 알고리즘을 실행 하는 동안 합니다 `execution::parallel_policy` 확인할 수 없는 예외를 통해 종료 되는 요소 액세스 함수를 호출 하는 경우 정책을 `terminate()` 호출 됩니다.
