---
title: 목록 컨트롤 만들기
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating control
- list controls [MFC]
ms.assetid: a4cb1729-31b6-4d2b-a44b-367474848a39
ms.openlocfilehash: 7b2cb47699339dd413dc1bfae7623069da56e7a4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62242252"
---
# <a name="creating-the-list-control"></a>목록 컨트롤 만들기

목록 제어 하는 방법 ([CListCtrl](../mfc/reference/clistctrl-class.md)) 만들어질 컨트롤을 직접 사용 또는 클래스를 사용 하는 여부에 따라 달라 집니다 [CListView](../mfc/reference/clistview-class.md) 대신 합니다. 사용 하는 경우 `CListView`, 프레임 워크가 해당 문서/뷰 만들기 시퀀스의 일부로 뷰를 생성 합니다. 목록 뷰를 만드는 컨트롤을 만듭니다 목록도 (두는 동일). 컨트롤의 보기에서 만들어집니다 [OnCreate](../mfc/reference/cwnd-class.md#oncreate) 처리기 함수입니다. 이 경우 컨트롤은 호출을 통해 항목을 추가할 수 있습니다 [GetListCtrl](../mfc/reference/clistview-class.md#getlistctrl)합니다.

### <a name="to-use-clistctrl-directly-in-a-dialog-box"></a>CListCtrl 대화 상자에서 직접 사용 하려면

1. 대화 상자 편집기, 대화 상자 템플릿 리소스 목록 컨트롤을 추가 합니다. 해당 컨트롤 ID를 지정합니다.

1. 사용 된 [멤버 변수 추가 마법사](../ide/adding-a-member-variable-visual-cpp.md) 형식의 멤버 변수를 추가 하려면 `CListCtrl` 컨트롤 속성을 사용 하 여 합니다. 이 멤버를 사용하여 `CListCtrl` 멤버 함수를 호출할 수 있습니다.

1. 모든 목록 컨트롤 알림 메시지에 대 한 대화 상자 클래스의 처리기 함수를 매핑할 속성 창에서 처리 해야 하는 사용 (참조 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)).

1. [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)의 스타일을 설정 합니다 `CListCtrl`합니다. 참조 [목록 컨트롤 스타일 변경](../mfc/changing-list-control-styles.md)합니다. 나중에 보기를 변경할 수 있지만 컨트롤에서 표시 하는 "보기"의 종류를 결정 합니다.

### <a name="to-use-clistctrl-in-a-nondialog-window"></a>CListCtrl 비 모달 창에서 사용 하려면

1. 뷰 또는 창 클래스에서 컨트롤을 정의합니다.

1. 컨트롤의 호출 [Create](../mfc/reference/clistctrl-class.md#create) 멤버 함수를 [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), 부모 창의 만큼 [OnCreate](../mfc/reference/cwnd-class.md#oncreate) 처리기 함수 (있는 경우 컨트롤 서브클래싱). 컨트롤의 스타일을 설정합니다.

## <a name="see-also"></a>참고자료

[CListCtrl 사용](../mfc/using-clistctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
