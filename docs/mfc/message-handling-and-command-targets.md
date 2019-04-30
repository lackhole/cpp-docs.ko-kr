---
title: 메시지 처리 및 명령 대상
ms.date: 11/04/2016
f1_keywords:
- IOleCommandTarget
helpviewer_keywords:
- command targets [MFC]
- message handling [MFC], active documents
- IOleCommandTarget interface [MFC]
- command routing [MFC], command targets
ms.assetid: e45ce14c-e6b6-4262-8f3b-4e891e0ec2a3
ms.openlocfilehash: 702cb96da13d6109c17a28e58c08a30af3f77fd4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383804"
---
# <a name="message-handling-and-command-targets"></a>메시지 처리 및 명령 대상

디스패치 인터페이스를 `IOleCommandTarget` 쿼리 명령을 실행 하는 간단 하 고 확장 가능한 메커니즘을 정의 합니다. 이 메커니즘은 Automation 보다 간단한 `IDispatch` ; 명령의 표준 집합을 완전히 사용 하기 때문에 거의 명령에는 인수를 및 관련 된 형식 정보가 없습니다 (형식 안전성도도 명령 인수에 대 한 감소).

자체로 식별 되는 "명령 그룹"에 속한 각 명령을 명령 디스패치 인터페이스 디자인에 **GUID**합니다. 따라서 새 그룹을 정의 하 고 Microsoft와 조정 하기 위해 필요 없이 다른 공급 업체는 해당 그룹 내의 모든 명령을 정의할 수 누구나 합니다. (정의의 동일한 방법을 기본적으로이 **dispinterface** plus **Dispid** Automation에서. 경우 여기에서 겹치는 있지만 자동화 핸들이 명령 라우팅 메커니즘은 대규모로 스크립팅/프로그래밍 아닌에 명령 라우팅에)

`IOleCommandTarget` 다음 시나리오를 처리합니다.

- 개체를 개체의 도구 모음에서 일반적으로 표시 되 고 같은 컨테이너 명령 중 일부에 대 한 개체의 도구 모음 단추가 되어 활성화 될 때 **인쇄**를 **인쇄 미리 보기**합니다  **저장할**, **새로 만들기**, **확대/축소**, 등. (개체를 제거 하는 표준 권장 되는 내부 활성화 또는 해당 도구 모음에서 이러한 단추 적어도 비활성화 합니다. 이 디자인에서는 명령에 사용 하도록 설정 되어 아직 적합 한 처리기로 라우팅됩니다.) 현재 컨테이너에 이러한 명령을 개체에 대 한 장치가 있습니다.

- 액티브 문서가 액티브 문서 컨테이너 (예: Office Binder)에 포함 되 면 컨테이너 보내야 할 명령을 이러한 **인쇄**하십시오 **페이지 설정**, **속성**를 등 포함 된 현재 문서에 있습니다.

기존 Automation 표준을 통해 처리할 수 없습니다이 간단한 명령 라우팅 및 `IDispatch`합니다. 그러나 관련 된 오버 헤드 `IDispatch` 여기서 필요한 것 보다 더 있도록 `IOleCommandTarget` 동일한 끝을 달성 하는 간단한 수단을 제공:

```
interface IOleCommandTarget : IUnknown
    {
    HRESULT QueryStatus(
        [in] GUID *pguidCmdGroup,
        [in] ULONG cCmds,
        [in,out][size_is(cCmds)] OLECMD *prgCmds,
        [in,out] OLECMDTEXT *pCmdText);
    HRESULT Exec(
        [in] GUID *pguidCmdGroup,
        [in] DWORD nCmdID,
        [in] DWORD nCmdExecOpt,
        [in] VARIANTARG *pvaIn,
        [in,out] VARIANTARG *pvaOut);
    }
```

`QueryStatus` 메서드를 다음 명령 집합이 특정 집합을 사용 하 여 식별 되 고 있는지 테스트 하는 **GUID**, 지원 됩니다. 이 호출의 배열을 채웁니다 **OLECMD** 값 (구조체) 지원 되는 목록과 명령과 명령 및/또는 상태 정보의 이름을 설명 하는 텍스트를 반환 합니다. 명령을 호출 하려면 호출자에 게 때, 명령을 전달할 수 있습니다 (집합과 **GUID**)를 `Exec` 옵션 및 인수를 함께 다시 반환 값 가져오기.

## <a name="see-also"></a>참고자료

[액티브 문서 컨테이너](../mfc/active-document-containers.md)
