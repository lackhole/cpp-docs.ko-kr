---
title: 개별 항목에 대한 이미지 설정
ms.date: 11/04/2016
helpviewer_keywords:
- extended combo boxes [MFC], images
- images [MFC], combo box items
ms.assetid: bde83db8-23a7-4e35-837a-c86447d2c0af
ms.openlocfilehash: 39aa4761dbc753c42f1aedbb18f1832eab471e50
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307733"
---
# <a name="setting-the-images-for-an-individual-item"></a>개별 항목에 대한 이미지 설정

다양 한 확장 된 콤보 상자 항목에서 사용 되는 이미지의 값에 의해 결정 됩니다 합니다 *iImage*, *iSelectedImage*, 및 *iOverlay* 합니다 의멤버[ COMBOBOXEXITEM](/windows/desktop/api/commctrl/ns-commctrl-tagcomboboxexitema) 구조입니다. 각 값은 컨트롤의 연결 된 이미지 목록의 이미지의 인덱스입니다. 기본적으로 이러한 멤버는 항목에 대 한 이미지가 없는 표시 하도록 컨트롤을 일으키는 0으로 설정 됩니다. 특정 항목에 대 한 이미지를 사용 하려는 경우 수정할 수 있습니다 구조 따라서 콤보 상자 항목을 삽입할 때 또는 기존 콤보 상자 항목을 수정 하 여.

## <a name="setting-the-image-for-a-new-item"></a>새 항목에 대 한 이미지 설정

새 항목을 삽입 하는 경우 초기화 된 *iImage*를 *iSelectedImage*, 및 *iOverlay* 적절 한 값을 사용 하 여 멤버 구조체이 고 다음에 대 한 호출을 사용 하 여 항목을 삽입 [CComboBoxEx::InsertItem](../mfc/reference/ccomboboxex-class.md#insertitem)합니다.

새 확장 된 콤보 상자 항목을 삽입 하는 다음 예제 (`cbi`) 확장 된 콤보 상자 컨트롤에 (`m_comboEx`), 모든 세 이미지 상태에 대 한 인덱스를 제공 합니다.

[!code-cpp[NVC_MFCControlLadenDialog#12](../mfc/codesnippet/cpp/setting-the-images-for-an-individual-item_1.cpp)]

## <a name="setting-the-image-for-an-existing-item"></a>기존 항목에 대 한 이미지 설정

기존 항목을 수정 하는 경우 사용 해야 합니다는 *마스크* 의 멤버는 **COMBOBOXEXITEM** 구조입니다.

#### <a name="to-modify-an-existing-item-to-use-images"></a>이미지를 사용 하는 기존 항목을 수정 하려면

1. 선언를 **COMBOBOXEXITEM** 구조체이 고 설정 합니다 *마스크* 데이터 멤버 값에 관심을 수정 합니다.

1. 이 구조를 사용 하 여 호출할 [CComboBoxEx::GetItem](../mfc/reference/ccomboboxex-class.md#getitem)합니다.

1. 수정 된 *마스크*를 *iImage*, 및 *iSelectedImage* 적절 한 값을 사용 하 여 새로 반환된 된 구조체의 멤버입니다.

1. 호출할 [CComboBoxEx::SetItem](../mfc/reference/ccomboboxex-class.md#setitem)수정 된 구조에 전달 합니다.

다음 예제에서는 세 번째 확장 된 콤보 상자 항목의 선택 또는 선택 하지 않은 이미지를 교환 하 여이 절차를 보여 줍니다.

[!code-cpp[NVC_MFCControlLadenDialog#13](../mfc/codesnippet/cpp/setting-the-images-for-an-individual-item_2.cpp)]

## <a name="see-also"></a>참고자료

[CComboBoxEx 사용](../mfc/using-ccomboboxex.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
