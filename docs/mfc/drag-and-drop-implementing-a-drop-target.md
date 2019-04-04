---
title: '끌어서 놓기: 놓기 대상 구현'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE drag and drop [MFC], implementing drop targets
- OLE drag and drop [MFC], drop target
- drag and drop [MFC], drop target
ms.assetid: 0689f1ec-5326-4008-b226-4b373c881358
ms.openlocfilehash: 46501193569d7f3098e23c67c68c76ce20a82ea3
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58766679"
---
# <a name="drag-and-drop-implementing-a-drop-target"></a>끌어서 놓기: 놓기 대상 구현

이 문서는 놓기 대상 응용 프로그램을 확인 하는 방법을 설명 합니다. 놓기 대상 구현 놓기 소스 구현 보다 약간 더 많은 작업이 많이 걸리지만 것은 여전히 비교적 간단 합니다. 이러한 기술은 비 OLE 응용 프로그램에도 적용 됩니다.

#### <a name="to-implement-a-drop-target"></a>놓기 대상 구현

1. 놓기 대상으로 사용할 수 있는 응용 프로그램에서 각 보기로 멤버 변수를 추가 합니다. 이 멤버 변수가 형식 이어야 합니다 `COleDropTarget` 또는 클래스에서 파생 됩니다.

1. 처리 하는 뷰 클래스의 함수는 **WM_CREATE** 메시지 (일반적으로 `OnCreate`), 새 멤버 변수를 호출 `Register` 멤버 함수입니다. `Revoke` 이름은 자동으로 사용자에 대 한 보기 소멸 될 때입니다.

1. 다음 함수를 재정의 합니다. 응용 프로그램 전체에서 동일한 동작을 원하는 경우 뷰 클래스에서 이러한 함수를 재정의 합니다. 격리 된 경우에는 동작을 수정 또는 삭제에 비-사용 하도록 설정 하려는 경우`CView` 에서 이러한 함수를 재정의 하는 windows에 `COleDropTarget`-클래스를 파생 합니다.

    |재정의|허용|
    |--------------|--------------|
    |`OnDragEnter`|창에서 발생 하는 작업을 삭제 합니다. 커서를 창에 먼저 들어가면 호출 됩니다.|
    |`OnDragLeave`|끌기 작업에 지정된 된 창을 나갈 때 특별 한 동작입니다.|
    |`OnDragOver`|창에서 발생 하는 작업을 삭제 합니다. 창 간에 커서를 끄는 경우 호출 됩니다.|
    |`OnDrop`|지정된 된 창에 배치 되는 데이터의 처리를 제공 합니다.|
    |`OnScrollBy`|경우 스크롤이 필요 대상 창에서에 대 한 특별 한 동작입니다.|

MAINVIEW를 참조 하세요. CPP 파일 MFC OLE 샘플의 일부입니다 [OCLIENT](../overview/visual-cpp-samples.md) 이러한 함수의 함께 작동 하는 방법의 예입니다.

자세한 내용은 다음을 참조하세요.

- [놓기 소스 구현](../mfc/drag-and-drop-implementing-a-drop-source.md)

- [OLE 데이터 개체 및 데이터 소스를 만들었다가](../mfc/data-objects-and-data-sources-creation-and-destruction.md)

- [OLE 데이터 개체 및 데이터 소스를 조작합니다.](../mfc/data-objects-and-data-sources-manipulation.md)

## <a name="see-also"></a>참고자료

[끌어서 놓기(OLE)](../mfc/drag-and-drop-ole.md)<br/>
[COleDropTarget 클래스](../mfc/reference/coledroptarget-class.md)
