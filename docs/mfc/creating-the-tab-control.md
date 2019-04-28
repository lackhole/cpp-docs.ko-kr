---
title: 탭 컨트롤 만들기
ms.date: 11/04/2016
f1_keywords:
- TCS_EX_REGISTERDROP
- TCS_EX_FLATSEPARATORS
helpviewer_keywords:
- TCS_EX_REGISTERDROP extended style [MFC]
- tab controls [MFC], creating
- CTabCtrl class [MFC], creating
- TCS_EX_FLATSEPARATORS extended style
ms.assetid: 3a9c2d64-f5f4-41ea-84ab-fceb73c3dbdc
ms.openlocfilehash: 4627009e2e07d1c5692d83d8d6262a9fcd37977e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62241964"
---
# <a name="creating-the-tab-control"></a>탭 컨트롤 만들기

탭 컨트롤이 만들어지는 방법을 대화 상자에서 컨트롤을 사용 또는 비 모달 창에서 만드는 하는지 여부에 따라 달라 집니다.

### <a name="to-use-ctabctrl-directly-in-a-dialog-box"></a>CTabCtrl에서에서 직접 사용 하는 대화 상자

1. 대화 상자 편집기, 대화 상자 템플릿 리소스에는 Tab 컨트롤을 추가 합니다. 해당 컨트롤 ID를 지정합니다.

1. 사용 된 [멤버 변수 추가 마법사](../ide/adding-a-member-variable-visual-cpp.md) 형식의 멤버 변수를 추가 하려면 [CTabCtrl](../mfc/reference/ctabctrl-class.md) 컨트롤 속성을 사용 하 여 합니다. 이 멤버를 사용하여 `CTabCtrl` 멤버 함수를 호출할 수 있습니다.

1. 처리 해야 할 모든 탭 컨트롤 알림 메시지에 대 한 대화 상자 클래스의 처리기 함수를 매핑하십시오. 자세한 내용은 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)합니다.

1. [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)의 스타일을 설정 합니다 `CTabCtrl`합니다.

### <a name="to-use-ctabctrl-in-a-nondialog-window"></a>CTabCtrl 비 모달 창에서 사용 하려면

1. 뷰 또는 창 클래스에서 컨트롤을 정의합니다.

1. 컨트롤의 호출 [Create](../mfc/reference/ctabctrl-class.md#create) 멤버 함수를 [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), 부모 창의 만큼 [OnCreate](../mfc/reference/cwnd-class.md#oncreate) 처리기 함수 (있는 경우 컨트롤 서브클래싱). 컨트롤의 스타일을 설정합니다.

이후에 `CTabCtrl` 개체가 생성 되었음을, 설정 하거나 다음 확장 스타일 지울 수:

- **TCS_EX_FLATSEPARATORS** 탭 컨트롤은 탭 항목 간의 구분 기호를 그립니다. 영향을 줍니다 탭이 있는 컨트롤에만이 확장 스타일을 **TCS_BUTTONS** 하 고 **TCS_FLATBUTTONS** 스타일입니다. 기본적으로 사용 하 여 탭 컨트롤 만들기 합니다 **TCS_FLATBUTTONS** 이 확장 스타일을 설정 하는 스타일입니다.

- **TCS_EX_REGISTERDROP** tab 컨트롤 생성 **TCN_GETOBJECT** 컨트롤의 탭 항목에 대해 개체를 끌 때 알림 메시지를 놓기 대상 요청 개체입니다.

    > [!NOTE]
    >  수신 하는 **TCN_GETOBJECT** 알림을 호출 하 여 OLE 라이브러리를 초기화 해야 합니다 [AfxOleInit](../mfc/reference/ole-initialization.md#afxoleinit)합니다.

이러한 스타일을 검색 컨트롤을 만든 후, 해당 호출 하 여 설정 하 고는 [GetExtendedStyle](../mfc/reference/ctabctrl-class.md#getextendedstyle) 하 고 [SetExtendedStyle](../mfc/reference/ctabctrl-class.md#setextendedstyle) 멤버 함수입니다.

예를 들어 설정 된 **TCS_EX_FLATSEPARATORS** 코드의 다음 줄을 사용 하 여 스타일:

[!code-cpp[NVC_MFCControlLadenDialog#33](../mfc/codesnippet/cpp/creating-the-tab-control_1.cpp)]

선택을 취소 합니다 **TCS_EX_FLATSEPARATORS** 에서 스타일을 `CTabCtrl` 코드의 다음 줄을 사용 하 여 개체:

[!code-cpp[NVC_MFCControlLadenDialog#34](../mfc/codesnippet/cpp/creating-the-tab-control_2.cpp)]

단추 사이 표시 되는 구분 기호가 제거 됩니다 프로그램 `CTabCtrl` 개체입니다.

## <a name="see-also"></a>참고자료

[CTabCtrl 사용](../mfc/using-ctabctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
