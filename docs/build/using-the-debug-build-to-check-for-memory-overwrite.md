---
title: 디버그 빌드를 사용한 메모리 덮어쓰기 확인
ms.date: 11/04/2016
helpviewer_keywords:
- memory, overwrites
ms.assetid: 1345eb4d-24ba-4595-b1cc-2da66986311e
ms.openlocfilehash: 42e3a7f1f1c34ba5a263adfca7496c24e162ab5d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826882"
---
# <a name="using-the-debug-build-to-check-for-memory-overwrite"></a>디버그 빌드를 사용한 메모리 덮어쓰기 확인

메모리 덮어쓰기 확인 하려면 디버그 빌드를 사용 하려면 먼저 디버그에 대 한 프로젝트를 다시 만들어야 합니다. 그런 다음 응용 프로그램의 처음 부분으로 이동 `InitInstance` 다음 줄을 추가 합니다.

```
afxMemDF |= checkAlwaysMemDF;
```

디버그 메모리 할당자는 모든 메모리 할당 주위 보호 바이트를 배치 합니다. 하지만 바이트 이러한 보호, 이러한 변경 되었는지 여부 (덮어쓰기가 메모리)를 확인 하지 않으면 아무런 소용이 없습니다. 이 고, 그렇지 버퍼 수를 실제로 제공 되어 메모리 덮어쓰기 달은 얼렁뚱땅 넘어갈 수 있습니다.

설정 하 여 합니다 `checkAlwaysMemDF`, MFC에 대 한 호출 되도록 할 합니다 `AfxCheckMemory` 때마다 함수를 호출 **새** 또는 **삭제** 이루어집니다. 메모리 덮어쓰기 검색 된 경우 다음과 유사한 추적 메시지를 생성 됩니다.

```
Damage Occurred! Block=0x5533
```

이러한 메시지 중 하나가 표시 되 면 손상이 발생 한 위치를 확인 하는 코드를 단계별로 실행 해야 합니다. 메모리 덮어쓰기 발생 한 부분을 보다 정확 하 게 하려면를 명시적으로 호출할 수 있게 `AfxCheckMemory` 직접. 예를 들어:

```
ASSERT(AfxCheckMemory());
    DoABunchOfStuff();
    ASSERT(AfxCheckMemory());
```

첫 번째 어설션이 성공 하는 경우 실패 하는 두 번째 메모리 덮어쓰기 두 호출 간에 함수에서 발생 했을 의미 합니다.

응용 프로그램의 특성에 따라 있을 수도 있습니다. `afxMemDF` 프로그램이 테스트할 너무 느리게 실행 합니다. 합니다 `afxMemDF` 변수 하면 `AfxCheckMemory` new에 대 한 모든 호출에 대 한 호출을 삭제 합니다. 호출을 분산형 해야 하는 경우 `AfxCheckMemory`위에 표시 된 것 처럼 ()와 메모리 덮어쓰기를 이렇게 합니다.

## <a name="see-also"></a>참고자료

[릴리스 빌드 문제 해결](fixing-release-build-problems.md)
