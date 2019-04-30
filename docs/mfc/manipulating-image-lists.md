---
title: 이미지 목록 조작
ms.date: 11/04/2016
helpviewer_keywords:
- image lists [MFC], manipulating
- lists [MFC], image
- CImageList class [MFC], manipulating
ms.assetid: 043418f8-077e-4dce-b8bb-2b7b0d7b5156
ms.openlocfilehash: 1e86961980c91ade47a3d6510dec5c04ac36cffb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262790"
---
# <a name="manipulating-image-lists"></a>이미지 목록 조작

합니다 [바꿉니다](../mfc/reference/cimagelist-class.md#replace) 이미지 목록의 이미지를 대체 하는 멤버 함수 ([CImageList](../mfc/reference/cimagelist-class.md)) 새 이미지를 사용 하 여 합니다. 또한 이 기능은 이미지 목록 개체에서 이미지 수를 동적으로 늘려야 할 경우에 유용합니다. 합니다 [SetImageCount](../mfc/reference/cimagelist-class.md#setimagecount) 함수 이미지 목록에 저장 된 이미지의 수를 동적으로 변경 합니다. 이미지 목록의 크기를 늘리는 경우 호출 `Replace` 새 이미지 슬롯에 이미지를 추가 합니다. 이미지 목록의 크기를 줄이면 새 크기를 넘어서는 이미지가 비워집니다.

합니다 [제거](../mfc/reference/cimagelist-class.md#remove) 멤버 함수는 이미지 목록에서 이미지를 제거 합니다. 합니다 [복사](../mfc/reference/cimagelist-class.md#copy) 멤버 함수 이미지 목록에 있는 이미지를 교체 하거나 복사할 수 있습니다. 이 함수에서는 소스 이미지를 대상 인덱스에 복사해야 하는지 또는 소스와 대상 이미지를 스왑해야 하는지를 나타낼 수 있습니다.

두 이미지 목록을 병합 하 여 새 이미지 목록을 만들려면 해당 오버 로드를 사용 합니다 [만들기](../mfc/reference/cimagelist-class.md#create) 멤버 함수입니다. 이 오버 로드 `Create` 기존 이미지의 첫 번째 이미지 목록에서 새 이미지 목록 개체에 결과 이미지를 저장 하는 병합 합니다. 새 이미지는 그리기로 생성되고, 두 번째 이미지는 첫 번째 이미지 위에 투명하게 표시됩니다. 새 이미지에 대한 마스크는 두 개의 기존 이미지에 대한 마스크의 비트에서 논리적 OR 연산을 수행한 결과입니다.

이 작업은 모든 이미지가 병합되고 새 이미지 목록 개체에 추가될 때까지 반복됩니다.

호출 하 여 보관 파일에 이미지 정보를 작성할 수 있습니다 합니다 [작성](../mfc/reference/cimagelist-class.md#write) 멤버 함수 및 호출 하 여 다시 읽을 합니다 [읽기](../mfc/reference/cimagelist-class.md#read) 멤버 함수입니다.

합니다 [GetSafeHandle](../mfc/reference/cimagelist-class.md#getsafehandle), [연결](../mfc/reference/cimagelist-class.md#attach), 및 [분리](../mfc/reference/cimagelist-class.md#detach) 멤버 함수에 연결 된 이미지 목록의 처리를 조작할 수는 `CImageList` 개체 동안는 [DeleteImageList](../mfc/reference/cimagelist-class.md#deleteimagelist) 멤버 함수를 삭제 하지 않고 이미지 목록을 삭제는 `CImageList` 개체입니다.

## <a name="see-also"></a>참고자료

[CImageList 사용](../mfc/using-cimagelist.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
