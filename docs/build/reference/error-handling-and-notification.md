---
title: 오류 처리 및 알림
ms.date: 11/04/2016
helpviewer_keywords:
- error handling, and notification
ms.assetid: b621cf60-d869-451a-b05e-dc86d78addaa
ms.openlocfilehash: 29fe46e15712609ec0c4f268749aaefed103117e
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812943"
---
# <a name="error-handling-and-notification"></a>오류 처리 및 알림

알림 및 오류 처리에 대 한 자세한 내용은 참조 하세요. [도우미 함수 이해](understanding-the-helper-function.md)합니다.

후크 함수에 대 한 자세한 내용은 참조 하세요. [구조체 및 상수 정의](structure-and-constant-definitions.md)합니다.

프로그램이 Dll 지연 로드를 사용 하는 경우 하므로 처리 해야 오류 안정적으로 프로그램 실행 되는 동안 발생 하는 실패 하면 처리 되지 않은 예외가 발생 합니다. 오류 처리는 두 부분으로 구성 됩니다.

후크를 통해 복구 합니다.
코드를 복구 하거나 실패 한 경우 대체 라이브러리 및/또는 루틴을 제공 하는 경우 제공 하거나 문제를 해결할 수 있는 도우미 함수를 후크를 제공할 수 있습니다. 처리 되도록 적절 한 값을 반환할 후크 일상적인 요구 (HINSTANCE 또는 관련 없으므로 FARPROC) 계속할 수 또는 예외를 throw 해야는 나타내기 위해 0입니다. 자체 예외 throw 할 수도 수 또는 **longjmp** 후크 부족 합니다. 알림 후크 및 오류 후크 됩니다.

예외를 통해 보고 합니다.
프로시저를 중단 하는 오류를 처리 하는 데 필요한 모든 경우와 사용자 코드에서 예외를 처리할 수 없는 후크는 필요 합니다.

다음 항목에는 오류 처리 및 알림 설명합니다.

- [알림 후크](notification-hooks.md)

- [오류 후크](failure-hooks.md)

- [예외](exceptions-c-cpp.md)

## <a name="see-also"></a>참고자료

[링커의 지연 로드된 DLL 지원](linker-support-for-delay-loaded-dlls.md)
