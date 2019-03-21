---
title: 오류 후크
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, failure hooks
ms.assetid: 12bb303b-ffe6-4471-bffe-9ef4f8bb2d30
ms.openlocfilehash: 2fc22ae77d729868adbf8c37d40e450e35a8e866
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811994"
---
# <a name="failure-hooks"></a>오류 후크

오류 후크는 동일한 방식으로 사용 하도록 설정 합니다 [알림 후크](notification-hooks.md)합니다. 처리 되도록 적합 한 값을 반환 하려면 후크 일상적인 요구 (HINSTANCE 또는 관련 없으므로 FARPROC) 계속할 수 또는 예외를 throw 해야는 나타내기 위해 0입니다.

사용자 정의 함수를 가리키는 포인터 변수는 다음과 같습니다.

```
// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}
ExternC
PfnDliHook   __pfnDliFailureHook2;
```

합니다 **DelayLoadInfo** 정확 하 게 값을 포함 하 여 오류를 보고 하는 데 필요한 모든 관련 데이터를 포함 하는 구조 `GetLastError`합니다.

알림 **dliFailLoadLib**, 후크 함수를 반환할 수 있습니다.

- 오류를 처리할 수 없는 경우 0입니다.

- HMODULE 오류 후크 문제를 해결 하 고 라이브러리 자체를 로드 합니다.

알림 **dliFailGetProc**, 후크 함수를 반환할 수 있습니다.

- 오류를 처리할 수 없는 경우 0입니다.

- 유효한 proc 주소 (가져오기 함수 주소), 오류 연결 하는 경우 주소에서 성공 했습니다.

## <a name="see-also"></a>참고자료

[오류 처리 및 알림](error-handling-and-notification.md)
