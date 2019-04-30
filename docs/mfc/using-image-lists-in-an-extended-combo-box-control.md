---
title: 확장 콤보 상자 컨트롤에서 이미지 목록 사용
ms.date: 11/04/2016
helpviewer_keywords:
- image lists [MFC], combo boxes
- extended combo boxes [MFC], images
- images [MFC], combo box items
ms.assetid: dfff25fe-af70-47a2-8032-3901d1e6842d
ms.openlocfilehash: 6e4d983d53e49fc8d9c80c206f1a23078eb82f61
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411554"
---
# <a name="using-image-lists-in-an-extended-combo-box-control"></a>확장 콤보 상자 컨트롤에서 이미지 목록 사용

확장 된 콤보 상자 컨트롤의 기본 기능은 콤보 상자 컨트롤에서 개별 항목을 사용 하 여 이미지 목록에서 이미지를 연결할 수 있습니다. 각 항목은 세 개의 서로 다른 이미지를 표시할 수 있습니다: 선택한 상태로, 선택 되지 않은 상태와 오버레이 이미지에 대 한 세 번째 하나에 대 한 합니다.

다음 절차는 확장 된 콤보 상자 컨트롤을 사용 하 여 이미지 목록을 연결합니다.

### <a name="to-associate-an-image-list-with-an-extended-combo-box-control"></a>확장 된 콤보 상자 컨트롤을 사용 하 여 이미지 목록을 연결 하려면

1. 새 이미지 목록을 생성 합니다 (또는 기존 이미지 목록 개체를 사용 하 여)를 사용 하 여 합니다 [CImageList](../mfc/reference/cimagelist-class.md) 생성자 및 결과 포인터를 저장 합니다.

1. 호출 하 여 새 이미지 목록 개체를 초기화 [CImageList::Create](../mfc/reference/cimagelist-class.md#create)합니다. 다음 코드는이 호출의 한 가지 예입니다.

   [!code-cpp[NVC_MFCControlLadenDialog#10](../mfc/codesnippet/cpp/using-image-lists-in-an-extended-combo-box-control_1.cpp)]

1. 가능한 각 상태에 대 한 선택적 이미지 추가: 선택한 또는, 선택 되지 않은 오버레이 합니다. 다음 코드는 세 가지 미리 정의 된 이미지를 추가합니다.

   [!code-cpp[NVC_MFCControlLadenDialog#11](../mfc/codesnippet/cpp/using-image-lists-in-an-extended-combo-box-control_2.cpp)]

1. 이미지 목록 컨트롤에 대 한 호출을 연결할 [CComboBoxEx::SetImageList](../mfc/reference/ccomboboxex-class.md#setimagelist)합니다.

이미지 목록 컨트롤을 사용 하 여 연결 되 면 각 항목의 세 가지 가능한 상태에 사용할 이미지를 개별적으로 지정할 수 있습니다. 자세한 내용은 [개별 항목에 대 한 이미지 설정](../mfc/setting-the-images-for-an-individual-item.md)합니다.

## <a name="see-also"></a>참고자료

[CComboBoxEx 사용](../mfc/using-ccomboboxex.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
