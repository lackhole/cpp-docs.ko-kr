---
title: 도구 모음 도구 설명
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], activating
- CBRS_TOOLTIPS constant [MFC]
- tool tips [MFC], adding text
- updates [MFC]
- CBRS_FLYBY constant [MFC]
- tool tips [MFC]
- updating status bar messages
- updates, status bar messages
- status bars [MFC], tool tips
- flyby status bar updates
ms.assetid: d1696305-b604-4fad-9f09-638878371412
ms.openlocfilehash: 4582b03844e1be3d4cf70bcc3fff1c3b66119ae3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351776"
---
# <a name="toolbar-tool-tips"></a>도구 모음 도구 설명

도구 팁은 기간에 대 한 단추 위로 마우스를 이동 도구 모음 단추의 용도 한 간단한 설명을 제공 하는 작은 팝업 창입니다. 도구 모음에 있는 응용 프로그램 마법사를 사용 하 여 응용 프로그램을 만들 때 도구 설명 지원을 제공 됩니다. 이 문서는 모두 도구 설명 지원을 응용 프로그램에 도구 설명 지원을 추가 하는 방법과 응용 프로그램 마법사에서 만든를 설명 합니다.

이 문에서는 다음과 같은 내용을 설명합니다.

- [도구 설명을 활성화](#_core_activating_tool_tips)

- [Flyby 상태 표시줄 업데이트](#_core_fly_by_status_bar_updates)

##  <a name="_core_activating_tool_tips"></a> 도구 설명을 활성화

응용 프로그램에서 도구 팁을 활성화 하려면 두 가지 작업을 수행 해야 합니다.

- CBRS_TOOLTIPS 스타일 다른 스타일을 추가 (WS_CHILD, WS_VISIBLE, 및 기타와 같은 **CBRS_** 스타일)으로 전달 합니다 *dwStyle* 매개 변수를 합니다 [CToolBar::Create](../mfc/reference/ctoolbar-class.md#create) 함수 또는 [SetBarStyle](../mfc/reference/ccontrolbar-class.md#setbarstyle)합니다.

- 아래 절차에서 설명한 대로, 도구 모음 명령에 대 한 명령줄 프롬프트를 포함 하는 문자열 리소스에 줄 바꿈 문자 ('\n')으로 구분 된 도구 설명 텍스트를 추가 합니다. 문자열 리소스 도구 모음 단추의 ID를 공유합니다.

#### <a name="to-add-the-tool-tip-text"></a>도구 설명 텍스트를 추가 하려면

1. 도구 모음 편집기 도구 모음을 편집 하는 동안 엽니다는 **도구 모음 단추 속성** 지정 된 단추에 대 한 창.

1. 에 **프롬프트** 상자에서 해당 단추에 대 한 도구 설명에 표시할 텍스트를 지정 합니다.

> [!NOTE]
>  문자열 리소스 편집를 열고 도구 모음 편집기에서 단추 속성에 해야 했던 이전 절차를 대체 하는 대로 텍스트를 설정 합니다.

도구 설명이 활성화를 사용 하 여 컨트롤 막대 자식 컨트롤 배치에 있는 경우에 컨트롤 막대 다음 조건을 충족 하는지와 모든 자식 컨트롤은 컨트롤 막대에 대 한 도구 설명에 표시 됩니다.

- 컨트롤의 ID가 1 않습니다.

- 리소스 파일의 자식 컨트롤로 동일한 ID 사용 하 여 문자열 테이블 항목에 도구 설명 문자열이 있습니다.

##  <a name="_core_fly_by_status_bar_updates"></a> Flyby 상태 표시줄 업데이트

도구 설명에 관련 된 기능은 "flyby" 상태 표시줄 업데이트 합니다. 기본적으로 상태 표시줄에 메시지가 단추가 활성화 되 면 특정 도구 모음 단추를 설명 합니다. 에 전달 하는 스타일 목록에서 CBRS_FLYBY를 포함 하 여 `CToolBar::Create`, 실제로 단추를 활성화 하지 않고 도구 모음 위로 마우스 커서를 이동할 때 업데이트 하는 이러한 메시지를 사용할 수 있습니다.

### <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [MFC 도구 모음 구현 (도구 모음에 대 한 개요 정보)](../mfc/mfc-toolbar-implementation.md)

- [도킹 및 부동 도구 모음](../mfc/docking-and-floating-toolbars.md)

- 합니다 [CToolBar](../mfc/reference/ctoolbar-class.md) 하 고 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 클래스

- [Toolbar 컨트롤 사용](../mfc/working-with-the-toolbar-control.md)

- [이전 도구 모음 사용](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>참고자료

[MFC 도구 모음 구현](../mfc/mfc-toolbar-implementation.md)
