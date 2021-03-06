---
title: 목록 컨트롤 만들기
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating control
- list controls [MFC]
ms.assetid: a4cb1729-31b6-4d2b-a44b-367474848a39
ms.openlocfilehash: f1c5d8db93421e1d3ae0e39aec82bdf0f5529f1f
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907918"
---
# <a name="creating-the-list-control"></a>목록 컨트롤 만들기

목록 컨트롤 ([CListCtrl](../mfc/reference/clistctrl-class.md))은 컨트롤을 직접 사용 하는지 대신 [CListView](../mfc/reference/clistview-class.md) 클래스를 사용 하는지에 따라 달라 집니다. 를 사용 `CListView`하는 경우 프레임 워크는 뷰를 문서/뷰 만들기 시퀀스의 일부로 생성 합니다. 목록 뷰를 만들면 목록 컨트롤도 만들어집니다 (두 항목은 동일 합니다). 컨트롤은 뷰의 [OnCreate](../mfc/reference/cwnd-class.md#oncreate) handler 함수에서 만들어집니다. 이 경우, 컨트롤은 [Getlistctrl](../mfc/reference/clistview-class.md#getlistctrl)호출을 통해 항목을 추가할 준비가 된 것입니다.

### <a name="to-use-clistctrl-directly-in-a-dialog-box"></a>대화 상자에서 직접 CListCtrl를 사용 하려면

1. 대화 상자 편집기에서 목록 컨트롤을 대화 상자 템플릿 리소스에 추가 합니다. 해당 컨트롤 ID를 지정합니다.

1. [멤버 변수 추가 마법사](../ide/adding-a-member-variable-visual-cpp.md) 를 사용 하 여 컨트롤 속성을 사용 하 `CListCtrl` 여 형식의 멤버 변수를 추가 합니다. 이 멤버를 사용하여 `CListCtrl` 멤버 함수를 호출할 수 있습니다.

1. [클래스 마법사](reference/mfc-class-wizard.md) 를 사용 하 여 처리 해야 하는 목록 컨트롤 알림 메시지에 대 한 대화 상자 클래스의 처리기 함수를 매핑할 수 있습니다 ( [메시지를 함수에 매핑](../mfc/reference/mapping-messages-to-functions.md)참조).

1. [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)에서에 대 한 `CListCtrl`스타일을 설정 합니다. [목록 컨트롤 스타일 변경](../mfc/changing-list-control-styles.md)을 참조 하십시오. 이는 나중에 뷰를 변경할 수 있지만 컨트롤에서 가져오는 "뷰"의 종류를 결정 합니다.

### <a name="to-use-clistctrl-in-a-nondialog-window"></a>비 모달 창에서 CListCtrl를 사용 하려면

1. 뷰 또는 창 클래스에서 컨트롤을 정의합니다.

1. 부모 창의 [OnCreate](../mfc/reference/cwnd-class.md#oncreate) handler 함수 (컨트롤을 서브클래싱 하는 경우)의 초기에는 [oninitialupdate](../mfc/reference/cview-class.md#oninitialupdate)에서 컨트롤의 [Create](../mfc/reference/clistctrl-class.md#create) 멤버 함수를 호출 합니다. 컨트롤의 스타일을 설정합니다.

## <a name="see-also"></a>참고자료

[CListCtrl 사용](../mfc/using-clistctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
