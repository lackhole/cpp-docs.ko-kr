---
title: 도구 설명 알림 처리
ms.date: 11/04/2016
helpviewer_keywords:
- TOOLTIPTEXT structure [MFC]
- CToolBarCtrl class [MFC], handling notifications
- notifications [MFC], tool tips
- tool tips [MFC], notifications
ms.assetid: ddb93b5f-2e4f-4537-8053-3453c86e2bbb
ms.openlocfilehash: 079dc26fdd355c5b5e3f89f28219902e5fd74a79
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62240239"
---
# <a name="handling-tool-tip-notifications"></a>도구 설명 알림 처리

지정 하는 경우는 **TBSTYLE_TOOLTIPS** 스타일 도구 모음을 만들고 도구 설명 컨트롤을 관리 합니다. 도구 팁을 도구 모음 단추를 설명 하는 텍스트의 줄을 포함 하는 작은 팝업 창입니다. 사용자 도구 모음 단추에 커서를 놓습니다 고 그대로 남아 있는 약 절반에 대 한 두 번째 경우에 나타나는 도구 설명이 숨겨집니다. 커서 주위 도구 설명이 표시 됩니다.

도구 설명 표시 되기 전에 **TTN_NEEDTEXT** 단추에 대 한 설명 텍스트를 검색 하는 도구 모음 소유자 창에 알림 메시지 전송 됩니다. 소유자 창 도구 모음에서의 경우는 `CFrameWnd` 때문에 모든 추가 작업 없이 설명이 표시 되는 도구 창 `CFrameWnd` 에 대 한 기본 처리기가 합니다 **TTN_NEEDTEXT** 알림. 도구 모음의 소유자 창에서 파생 되지 않은 경우 `CFrameWnd`, 대화 상자나 폼 보기와 같은 소유자 창의 메시지 맵에 항목을 추가 및 메시지 맵에서 알림 처리기를 제공 해야 합니다. 소유자 창의 메시지 맵에 항목을 아래와 같습니다.

[!code-cpp[NVC_MFCControlLadenDialog#40](../mfc/codesnippet/cpp/handling-tool-tip-notifications_1.cpp)]

## <a name="remarks"></a>설명

*memberFxn*<br/>
이 단추에 대 한 텍스트가 필요할 때 호출 되는 멤버 함수입니다.

도구 설명의 id는 항상 0입니다.

이외에 **TTN_NEEDTEXT** 알림, 도구 설명 컨트롤 도구 모음 컨트롤에 다음과 같은 알림이 보낼 수 있습니다.

|알림|의미|
|------------------|-------------|
|**TTN_NEEDTEXTA**|도구 설명 컨트롤이 필요 ASCII 텍스트 (Windows 95에만 해당)|
|**TTN_NEEDTEXTW**|도구 설명 컨트롤이 필요한 유니코드 텍스트 (Windows NT에만 해당)|
|**TBN_HOTITEMCHANGE**|핫 (선택한) 항목이 변경 되었음을 나타냅니다.|
|**NM_RCLICK**|사용자 단추를 마우스 오른쪽 단추로 클릭에 나타냅니다.|
|**TBN_DRAGOUT**|사용자가 단추를 클릭 하 고 끌어 포인터를 단추 밖을 나타냅니다. 응용 프로그램을을 끌어서를 구현 하 고 도구 모음 단추에서 삭제할 수 있습니다. 이 알림을 수신 하는 경우 응용 프로그램 끌기 시작 하 고 작업을 삭제 합니다.|
|**TBN_DROPDOWN**|사용자가 사용 하는 단추 클릭 나타냅니다 합니다 **TBSTYLE_DROPDOWN** 스타일입니다.|
|**TBN_GETOBJECT**|사용자는 단추 위로 포인터를 이동 나타냅니다 합니다 **TBSTYLE_DROPPABLE** 스타일입니다.|

처리기 함수 예제 및 도구 설명을 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 참조 하십시오 [도구 팁](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)합니다.

## <a name="see-also"></a>참고자료

[CToolBarCtrl 사용](../mfc/using-ctoolbarctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
