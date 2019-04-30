---
title: CToolBarCtrl 개체 만들기
ms.date: 11/04/2016
f1_keywords:
- CToolBarCtrl
helpviewer_keywords:
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: a4f6bf0c-0195-4dbf-a09e-aee503e19dc3
ms.openlocfilehash: d0f41731e3a4db7b15d4f2a7ebaac94135d5350d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406134"
---
# <a name="creating-a-ctoolbarctrl-object"></a>CToolBarCtrl 개체 만들기

[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 여러 개의 내부 데이터 구조를 포함 하는 개체-단추 이미지 비트맵의 목록을, 단추 레이블 문자열 목록이 및 목록은 `TBBUTTON` 구조-는 이미지를 연결 및/또는 위치, 스타일, 상태를 사용 하 여 문자열 및 단추의 명령 ID입니다. 각 이러한 데이터 구조의 요소의 0부터 시작 인덱스에 의해 참조 됩니다. 사용 하기 전에 `CToolBarCtrl` 개체를 이러한 데이터 구조를 설정 해야 합니다. 데이터 구조 목록을 참조 하세요 [도구 모음 컨트롤](controls-mfc.md) Windows SDK에 있습니다. 단추 레이블;에 대 한 문자열의 목록 에서만 사용할 수 있습니다. 도구 모음에서 문자열을 검색할 수 없습니다.

`CToolBarCtrl` 개체를 사용하려면, 일반적으로 다음 단계를 수행해야 합니다.

### <a name="to-use-a-ctoolbarctrl-object"></a>CToolBarCtrl 개체를 사용 하려면

1. 생성 된 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 개체입니다.

1. 호출 [Create](../mfc/reference/ctoolbarctrl-class.md#create) Windows 도구 모음 공용 컨트롤을 만들고 연결 하는 `CToolBarCtrl` 개체입니다. 단추에 대 한 비트맵 이미지를 원하는 경우 추가 단추 비트맵 도구 모음을 호출 하 여 [AddBitmap](../mfc/reference/ctoolbarctrl-class.md#addbitmap)합니다. 단추에 대 한 문자열 레이블을 하려는 경우 추가 문자열을 도구 모음을 호출 하 여 [AddString](../mfc/reference/ctoolbarctrl-class.md#addstring) 및/또는 [AddStrings](../mfc/reference/ctoolbarctrl-class.md#addstrings)합니다. 호출한 후 `AddString` 및/또는 `AddStrings`를 호출 해야 [AutoSize](../mfc/reference/ctoolbarctrl-class.md#autosize) 문자열 또는 표시할 문자열을 가져오려면.

1. 호출 하 여 도구 모음에 단추 구조를 추가할 [AddButtons](../mfc/reference/ctoolbarctrl-class.md#addbuttons)합니다.

1. 도구 팁을 원한다 면 처리할 **TTN_NEEDTEXT** 모음의 소유자 창의 메시지에 설명 된 대로 [도구 팁 알림 처리](../mfc/handling-tool-tip-notifications.md)합니다.

1. 사용자가 도구 모음을 사용자 지정할 수 있게 되기를 원하는 경우에 설명 된 대로 소유자 창에서 사용자 지정 알림 메시지를 처리 [사용자 지정 알림 처리](../mfc/handling-customization-notifications.md)합니다.

## <a name="see-also"></a>참고자료

[CToolBarCtrl 사용](../mfc/using-ctoolbarctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
