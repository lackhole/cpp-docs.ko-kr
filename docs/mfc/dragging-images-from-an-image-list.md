---
title: 이미지 목록에서 이미지 끌기
ms.date: 11/04/2016
helpviewer_keywords:
- CImageList class [MFC], dragging images from
- dragging images from image lists [MFC]
- image lists [MFC], dragging images from
- images [MFC], dragging from image lists
ms.assetid: af691db8-e4f0-4046-b7b9-9acc68d3713d
ms.openlocfilehash: ba56a38cfc5ccf808c7d95f24666fff0313ecc43
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262621"
---
# <a name="dragging-images-from-an-image-list"></a>이미지 목록에서 이미지 끌기

[CImageList](../mfc/reference/cimagelist-class.md) 화면의 이미지 끌기를 위한 함수가 포함 됩니다. 끌기 함수가 색에 커서의 모든 깜박임 없이 원활 하 게 이미지를 이동합니다. 마스크 및 마스크 해제 된 이미지를 끌 수 있습니다.

합니다 [BeginDrag](../mfc/reference/cimagelist-class.md#begindrag) 멤버 함수는 끌기 작업을 시작 합니다. 매개 변수 인덱스를 끌기 이미지와 이미지 내의 핫 스폿 위치를 포함 합니다. 핫 스폿 단일 픽셀 이미지의 정확한 화면 위치로 끌어 놓고 함수를 인식 하는 경우 일반적으로 응용 프로그램 설정 핫 스폿 마우스 커서의 핫 스폿 일치 하는 것입니다. 합니다 [DragMove](../mfc/reference/cimagelist-class.md#dragmove) 멤버 함수는 이미지를 새 위치로 이동 합니다.

합니다 [DragEnter](../mfc/reference/cimagelist-class.md#dragenter) 멤버 함수는 창에서 끌어 이미지의 초기 위치를 설정 하 고 위치에 이미지를 그립니다. 매개 변수를 창 내에서 처음 위치 좌표를 지정 하는 점과 이미지를 그릴 창에 대 한 포인터를 포함 합니다. 좌표가 클라이언트 영역이 아니라 창의 왼쪽 위 모퉁이 기준으로 합니다. 모든 좌표를 매개 변수로 사용 하는 이미지 끌기 함수에도 마찬가지입니다. 즉, 좌표를 지정 하는 경우 테두리, 제목 표시줄, 메뉴 모음 등의 창 요소의 너비에 대 한 보완 해야 합니다. 지정 하는 경우는 **NULL** 호출 하는 경우에 창 핸들 `DragEnter`, 끌기 함수가 데스크톱 창에 연결 된 장치 컨텍스트에서 이미지를 그리기 및 좌표는 화면 왼쪽 위 모퉁이 기준으로 합니다.

`DragEnter` 끌기 작업 중 지정된 된 창에 대 한 다른 모든 업데이트를 잠급니다. 끌어온된 이미지를 사용 하 여 일시적으로 숨길 수 끌어서 놓기 작업의 대상 강조 표시 하는 등의 끌기 작업을 하는 동안에 그리기를 수행 해야 할 경우는 [현재의](../mfc/reference/cimagelist-class.md#dragleave) 멤버 함수입니다. 사용할 수도 있습니다는 [DragShowNoLock](../mfc/reference/cimagelist-class.md#dragshownolock) 멤버 함수입니다.

호출 [EndDrag](../mfc/reference/cimagelist-class.md#enddrag) 완료 되 면 이미지를 끌기.

합니다 [SetDragCursorImage](../mfc/reference/cimagelist-class.md#setdragcursorimage) 멤버 함수는 현재 끌기 이미지를 사용 하 여 지정된 된 이미지 (일반적으로 마우스 커서 이미지)를 결합 하 여 새 끌기 이미지를 만듭니다. 끌기 작업 중 새 이미지를 사용 하는 끌어 놓고 함수, 있으므로 Windows를 사용 해야 [ShowCursor](/windows/desktop/api/winuser/nf-winuser-showcursor) 함수를 호출한 후 실제 마우스 커서를 숨기려면 `SetDragCursorImage`합니다. 이 고, 그렇지 시스템 끌기 작업의 기간에 대 한 두 마우스 커서를 표시할 수도 있습니다.

응용 프로그램을 호출 하면 `BeginDrag`시스템 내부 임시 이미지 목록을 만들고 복사본이 지정된 된 내부 목록에 이미지를 끌어옵니다. 사용 하 여 임시 끌기 이미지 목록에 대 한 포인터를 검색할 수 있습니다 합니다 [GetDragImage](../mfc/reference/cimagelist-class.md#getdragimage) 멤버 함수입니다. 함수는 또한 끌어서 위치를 기준으로 끌기 이미지의 오프셋과 현재 끌어서 위치를 검색합니다.

## <a name="see-also"></a>참고자료

[CImageList 사용](../mfc/using-cimagelist.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
