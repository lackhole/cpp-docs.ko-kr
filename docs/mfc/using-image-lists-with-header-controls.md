---
title: 이미지 목록과 헤더 컨트롤 함께 사용
ms.date: 11/04/2016
helpviewer_keywords:
- header controls [MFC], image lists
- CHeaderCtrl class [MFC], image lists
- image lists [MFC], header controls
ms.assetid: d5e9b310-6278-406c-909c-eefa09549a47
ms.openlocfilehash: 3d9a4a0c655fa46c15d8c4d9b2b4e90cd34c2937
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411541"
---
# <a name="using-image-lists-with-header-controls"></a>이미지 목록과 헤더 컨트롤 함께 사용

헤더 항목에는 머리글 항목에 있는 이미지를 표시할 수가 있습니다. 연결 된 이미지 목록에 저장 된이 이미지는 16 x 16 픽셀 및 목록 뷰 컨트롤에 사용 되는 아이콘 이미지와 동일한 특성이 있습니다. 이 동작을 성공적으로 구현 하려면 먼저 만듭니다 및 이미지 목록을 초기화, 헤더 컨트롤과 목록 연결 하며 다음 이미지를 표시 하는 헤더 항목의 특성을 수정 합니다.

다음 절차에서는 헤더 컨트롤에 대 한 포인터를 사용 하 여 세부 정보를 보여 줍니다 (`m_pHdrCtrl`) 및 이미지 목록에 대 한 포인터 (`m_pHdrImages`).

### <a name="to-display-an-image-in-a-header-item"></a>헤더 항목의 이미지를 표시 하려면

1. 새 이미지 목록을 생성 (또는 기존 이미지 목록 개체를 사용 하 여)를 사용 하는 [CImageList](../mfc/reference/cimagelist-class.md) 결과 포인터를 저장 하는 생성자입니다.

1. 호출 하 여 새 이미지 목록 개체를 초기화 [CImageList::Create](../mfc/reference/cimagelist-class.md#create)합니다. 다음 코드는이 호출의 한 가지 예입니다.

   [!code-cpp[NVC_MFCControlLadenDialog#15](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_1.cpp)]

1. 각 헤더 항목에 대 한 이미지를 추가 합니다. 다음 코드는 두 개의 미리 정의 된 이미지를 추가 합니다.

   [!code-cpp[NVC_MFCControlLadenDialog#16](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_2.cpp)]

1. 헤더 컨트롤에 대 한 호출을 사용 하 여 이미지 목록을 연관 [CHeaderCtrl::SetImageList](../mfc/reference/cheaderctrl-class.md#setimagelist)합니다.

1. 연결 된 이미지 목록의 이미지를 표시 하려면 머리글 항목을 수정 합니다. 다음 예제에서 첫 번째 이미지를 할당 `m_phdrImages`를 첫 번째 헤더 항목에 `m_pHdrCtrl`입니다.

   [!code-cpp[NVC_MFCControlLadenDialog#17](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_3.cpp)]

사용 된 매개 변수 값에 대 한 자세한 내용은 참조는 관련 [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)합니다.

> [!NOTE]
>  여러 컨트롤 같은 이미지 목록을 사용 하 여는 것이 가능 합니다. 예를 들어 표준 목록 뷰 컨트롤에 있을 수 있습니다 (16 x 16 픽셀 이미지)의 목록 뷰 컨트롤의 작은 아이콘 보기 및 목록 뷰 컨트롤의 헤더 항목에 사용 되는 이미지 목록입니다.

## <a name="see-also"></a>참고자료

[CHeaderCtrl 사용](../mfc/using-cheaderctrl.md)
