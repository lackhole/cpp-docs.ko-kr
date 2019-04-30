---
title: 날짜 및 시간 선택 컨트롤 만들기
ms.date: 11/04/2016
helpviewer_keywords:
- DateTimePicker control [MFC], creating
- CDateTimeCtrl class [MFC], creating
ms.assetid: 764ec2fb-98cd-478b-a5f2-d63f0bb12279
ms.openlocfilehash: b3dd04d917667ff04001a455263d2a2f4af9bf9c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62242395"
---
# <a name="creating-the-date-and-time-picker-control"></a>날짜 및 시간 선택 컨트롤 만들기

날짜 및 시간 선택 컨트롤의 인스턴스가 만들어지는 방법을 대화 상자에서 컨트롤을 사용 또는 비 모달 창에서 만드는 하는지 여부에 따라 달라 집니다.

### <a name="to-use-cdatetimectrl-directly-in-a-dialog-box"></a>CDateTimeCtrl 대화 상자에서 직접 사용 하려면

1. 대화 상자 편집기에서 대화 상자 템플릿 리소스에는 날짜 및 시간 선택 컨트롤을 추가 합니다. 해당 컨트롤 ID를 지정합니다.

1. 날짜 및 시간 선택 컨트롤의 속성 대화 상자를 사용 하 여 필요한 스타일을 지정 합니다.

1. 사용 된 [멤버 변수 추가 마법사](../ide/adding-a-member-variable-visual-cpp.md) 형식의 멤버 변수를 추가 하려면 [CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md) 컨트롤 속성을 사용 하 여 합니다. 이 멤버를 사용하여 `CDateTimeCtrl` 멤버 함수를 호출할 수 있습니다.

1. 속성 창을 사용 하 여 모든 날짜 시간 선택 컨트롤에 대 한 대화 상자 클래스의 처리기 함수에 매핑할 [알림을](../mfc/processing-notification-messages-in-date-and-time-picker-controls.md) 처리 해야 하는 메시지 (참조 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)).

1. [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)에 대 한 추가 스타일을 설정 합니다 `CDateTimeCtrl` 개체입니다.

### <a name="to-use-cdatetimectrl-in-a-nondialog-window"></a>CDateTimeCtrl 비 모달 창에서 사용 하려면

1. 뷰 또는 창 클래스에서 컨트롤을 선언 합니다.

1. 컨트롤의 호출 [Create](../mfc/reference/ctabctrl-class.md#create) 멤버 함수를 [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), 부모 창의 만큼 [OnCreate](../mfc/reference/cwnd-class.md#oncreate) 처리기 함수 (있는 경우 컨트롤 서브클래싱). 컨트롤의 스타일을 설정합니다.

## <a name="see-also"></a>참고자료

[CDateTimeCtrl 사용](../mfc/using-cdatetimectrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
