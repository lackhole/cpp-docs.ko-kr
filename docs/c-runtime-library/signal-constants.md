---
title: 신호 상수
ms.date: 11/04/2016
f1_keywords:
- SIGTERM
- SIGFPE
- SIGABRT
- SIGILL
- SIGINT
- SIGSEGV
helpviewer_keywords:
- SIGTERM constant
- SIGABRT constant
- SIGSEGV constant
- SIGFPE constant
- SIGINT constant
- signal constants
- SIGILL constant
ms.assetid: a3b39281-dae7-4e44-8d68-e6a610c669dd
ms.openlocfilehash: e9953e967d1c94ae56dfc1063fb0deafa342631c
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57738723"
---
# <a name="signal-constants"></a>신호 상수

## <a name="syntax"></a>구문

```
#include <signal.h>
```

## <a name="remarks"></a>주의

`sig` 인수는 아래에 나열된 매니페스트 상수 중 하나여야 합니다(SIGNAL.H에 정의).

|||
|-|-|
|SIGABRT|비정상적인 종료. 기본 작업은 호출 프로그램을 종료하고 종료 코드 3을 생성합니다.  |
|SIGABRT_COMPAT|SIGABRT와 동일. 다른 플랫폼과의 호환을 위해 필요합니다.  |
|SIGFPE|부동 소수점 오류(오버플로, 0으로 나누기 또는 잘못된 작업) 기본 작업은 호출 프로그램을 종료합니다.  |
|SIGILL|잘못된 명령. 기본 작업은 호출 프로그램을 종료합니다.  |
|SIGINT|Ctrl+C 인터럽트. 기본 작업은 호출 프로그램을 종료하고 종료 코드 3을 생성합니다.  |
|SIGSEGV|잘못된 스토리지 액세스. 기본 작업은 호출 프로그램을 종료합니다.  |
|SIGTERM|프로그램에 종료 요청이 전송됨. 기본 작업은 호출 프로그램을 종료하고 종료 코드 3을 생성합니다.  |
|SIG_ERR|오류가 발생했음을 나타내는 신호의 반환 형식  |

## <a name="see-also"></a>참고 항목

[signal](../c-runtime-library/reference/signal.md)<br/>
[raise](../c-runtime-library/reference/raise.md)<br/>
[전역 상수](../c-runtime-library/global-constants.md)
