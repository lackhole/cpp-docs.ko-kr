---
title: _CRT_DISABLE_PERFCRIT_LOCKS
ms.date: 11/04/2016
f1_keywords:
- _CRT_DISABLE_PERFCRIT_LOCKS
- CRT_DISABLE_PERFCRIT_LOCKS
helpviewer_keywords:
- CRT_DISABLE_PERFCRIT_LOCKS constant
- _CRT_DISABLE_PERFCRIT_LOCKS constant
ms.assetid: 36cc2d86-cdb1-4b2b-a03c-c0d3818e7c6f
ms.openlocfilehash: b6f4d8dee5577e88aa59af9bff017aab0c7eef89
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57740260"
---
# <a name="crtdisableperfcritlocks"></a>_CRT_DISABLE_PERFCRIT_LOCKS

I/O 연산에서 성능이 중요한 잠금을 해제합니다.

## <a name="syntax"></a>구문

```
#define _CRT_DISABLE_PERFCRIT_LOCKS
```

## <a name="remarks"></a>주의

이 기호를 정의하면 모든 I/O 연산에서 단일 스레드 I/O 모델을 가정하도록 강제 지정하여 단일 스레드 I/O 바인딩 프로그램의 성능을 향상시킬 수 있습니다. [다중 스레드 라이브러리 성능](../c-runtime-library/multithreaded-libraries-performance.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[전역 상수](../c-runtime-library/global-constants.md)
