---
title: '끌어서 놓기: 놓기 소스 구현'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE drag and drop [MFC], initiating drag operations
- drag and drop [MFC], calling DoDragDrop
- OLE drag and drop [MFC], drop source
- OLE drag and drop [MFC], calling DoDragDrop
- drag and drop [MFC], initiating drag operations
- drag and drop [MFC], drop source
ms.assetid: 0ed2fda0-63fa-4b1e-b398-f1f142f40035
ms.openlocfilehash: 2aa593fa953f7a9874036d48124ae7b92d88e0a6
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58768642"
---
# <a name="drag-and-drop-implementing-a-drop-source"></a>끌어서 놓기: 놓기 소스 구현

이 문서에서는 응용 프로그램을 끌어서 놓기 작업에 데이터를 제공 하는 방법에 설명 합니다.

기본 구현의 놓기 소스는 비교적 간단 합니다. 첫 번째 단계는 끌기 작업을 시작 하는 이벤트를 결정 하는 것입니다. 사용자 인터페이스 지침 데이터의 선택으로 끌기 작업의 시작 부분을 정의 하는 것이 좋습니다와 **WM_LBUTTONDOWN** 선택한 데이터 내에서 지점에서 발생 하는 이벤트입니다. MFC OLE 샘플 [OCLIENT](../overview/visual-cpp-samples.md) 하 고 [HIERSVR](../overview/visual-cpp-samples.md) 다음이 지침을 따릅니다.

응용 프로그램 컨테이너 이며 선택한 데이터 연결 또는 포함된 된 개체 형식의 경우 `COleClientItem`, 호출 해당 `DoDragDrop` 멤버 함수입니다. 그렇지 않은 경우 생성을 `COleDataSource` 개체, 선택 항목을 사용 하 여 초기화 및 데이터 원본 개체를 호출 `DoDragDrop` 멤버 함수입니다. 사용 하 여 응용 프로그램 서버인 경우 `COleServerItem::DoDragDrop`합니다. 표준 끌어서 놓기 동작을 사용자 지정에 대 한 자세한 문서를 참고 [끌어다 놓습니다. 사용자 지정](../mfc/drag-and-drop-customizing.md)합니다.

하는 경우 `DoDragDrop` 반환 **DROPEFFECT_MOVE**, 소스 문서에서 원본 데이터를 즉시 삭제 합니다. 다른 반환 값이 없으므로에서 `DoDragDrop` 놓기 소스에 적용 합니다.

자세한 내용은 다음을 참조하세요.

- [놓기 대상 구현](../mfc/drag-and-drop-implementing-a-drop-target.md)

- [사용자 지정 끌어서 놓기](../mfc/drag-and-drop-customizing.md)

- [OLE 데이터 개체 및 데이터 소스를 만들었다가](../mfc/data-objects-and-data-sources-creation-and-destruction.md)

- [OLE 데이터 개체 및 데이터 소스를 조작합니다.](../mfc/data-objects-and-data-sources-manipulation.md)

## <a name="see-also"></a>참고자료

[끌어서 놓기(OLE)](../mfc/drag-and-drop-ole.md)<br/>
[COleDataSource::DoDragDrop](../mfc/reference/coledatasource-class.md#dodragdrop)<br/>
[COleClientItem::DoDragDrop](../mfc/reference/coleclientitem-class.md#dodragdrop)<br/>
[CView::OnDragLeave](../mfc/reference/cview-class.md#ondragleave)
