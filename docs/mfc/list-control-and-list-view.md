---
title: 목록 컨트롤 및 목록 뷰
ms.date: 11/04/2016
helpviewer_keywords:
- CListView class [MFC], and CListCtrl
- views [MFC], list and list control
- CListCtrl class [MFC], and CListView
- list views [MFC]
- list controls [MFC], List view
ms.assetid: 7aee1c48-b158-4399-be0b-be366993665e
ms.openlocfilehash: 5c9612a22eab27d568c0dbb86d29ba031fe5985e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62365335"
---
# <a name="list-control-and-list-view"></a>목록 컨트롤 및 목록 뷰

편의 위해 MFC는 두 가지 방법으로 목록 컨트롤을 캡슐화합니다. 목록 컨트롤을 사용할 수 있습니다.

- 포함 하 여 직접를 [CListCtrl](../mfc/reference/clistctrl-class.md) 대화 상자 클래스의 개체입니다.

- 클래스를 사용 하 여 직접 [CListView](../mfc/reference/clistview-class.md)합니다.

`CListView` 손쉽게 컨트롤을 캡슐화 하는 MFC 문서/뷰 아키텍처를 사용 하 여 목록 컨트롤을 통합할 수 만큼 [CEditView](../mfc/reference/ceditview-class.md) 편집 컨트롤을 캡슐화: 컨트롤을 MFC 뷰로의 전체 노출 영역을 채웁니다. (뷰 *됩니다* 캐스팅할 컨트롤 `CListView`.)

A `CListView` 개체에서 상속 [CCtrlView](../mfc/reference/cctrlview-class.md) 와 해당 기본 클래스 기본 목록 컨트롤을 검색 하는 멤버 함수를 추가 합니다. 구성원 보기를 사용 하 여 뷰를 뷰로 사용. 사용 된 [GetListCtrl](../mfc/reference/clistview-class.md#getlistctrl) 멤버 함수 목록 컨트롤의 멤버 함수에 대 한 액세스 권한을 얻으려고 합니다. 이러한 멤버를 사용 합니다.

- 추가, 삭제 또는 목록에 표시 된 "항목"을 조작 합니다.

- 목록 컨트롤 특성을 가져오거나 설정 합니다.

에 대 한 참조를 가져오려고 합니다 `CListCtrl` 내부를 `CListView`를 호출 `GetListCtrl` 목록 뷰 클래스에서:

[!code-cpp[NVC_MFCListView#4](../atl/reference/codesnippet/cpp/list-control-and-list-view_1.cpp)]

목록 컨트롤을 사용 하는 두 방법을 설명 합니다.

## <a name="see-also"></a>참고자료

[CListCtrl 사용](../mfc/using-clistctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
