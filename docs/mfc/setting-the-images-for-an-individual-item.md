---
title: 개별 항목에 대한 이미지 설정
ms.date: 11/04/2016
helpviewer_keywords:
- extended combo boxes [MFC], images
- images [MFC], combo box items
ms.assetid: bde83db8-23a7-4e35-837a-c86447d2c0af
ms.openlocfilehash: 177c06acfe665a43921b19407d9d357d4545e748
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511281"
---
# <a name="setting-the-images-for-an-individual-item"></a>개별 항목에 대한 이미지 설정

확장 된 콤보 상자 항목에서 사용 하는 다양 한 형식의 이미지는 [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) 구조의 *iimage*, *iSelectedImage*및 *iimage* 멤버 값에 의해 결정 됩니다. 각 값은 컨트롤의 연결 된 이미지 목록에 있는 이미지의 인덱스입니다. 기본적으로 이러한 멤버는 0으로 설정 되어 컨트롤에서 항목에 대 한 이미지를 표시 하지 않습니다. 특정 항목에 대해 이미지를 사용 하려는 경우에는 콤보 상자 항목을 삽입 하거나 기존 콤보 상자 항목을 수정 하 여 구조체를 적절 하 게 수정할 수 있습니다.

## <a name="setting-the-image-for-a-new-item"></a>새 항목에 대 한 이미지 설정

새 항목을 삽입 하는 경우에는 적절 한 값을 사용 하 여 *Iimage*, *ISelectedImage*및 *iimage* Structure 멤버를 초기화 한 다음 [CComboBoxEx:: InsertItem](../mfc/reference/ccomboboxex-class.md#insertitem)를 호출 하 여 항목을 삽입 합니다.

다음 예제에서는 확장 combo box 컨트롤 (`cbi``m_comboEx`)에 새 확장 된 콤보 상자 항목 ()을 삽입 하 여 세 가지 이미지 상태 모두에 대 한 인덱스를 제공 합니다.

[!code-cpp[NVC_MFCControlLadenDialog#12](../mfc/codesnippet/cpp/setting-the-images-for-an-individual-item_1.cpp)]

## <a name="setting-the-image-for-an-existing-item"></a>기존 항목에 대 한 이미지 설정

기존 항목을 수정 하는 경우 **COMBOBOXEXITEM** 구조체의 *mask* 멤버를 사용 해야 합니다.

#### <a name="to-modify-an-existing-item-to-use-images"></a>이미지를 사용 하도록 기존 항목을 수정 하려면

1. **COMBOBOXEXITEM** 구조체를 선언 하 고 *마스크* 데이터 멤버를 수정 하려는 값으로 설정 합니다.

1. 이 구조체를 사용 하 여 [CComboBoxEx:: GetItem](../mfc/reference/ccomboboxex-class.md#getitem)를 호출 합니다.

1. 적절 한 값을 사용 하 여 새로 반환 된 구조체의 *mask*, *Iimage*및 *iSelectedImage* 멤버를 수정 합니다.

1. 수정 된 구조체를 전달 하 여 [CComboBoxEx:: SetItem](../mfc/reference/ccomboboxex-class.md#setitem)를 호출 합니다.

다음 예에서는 세 번째 확장 된 콤보 상자 항목의 선택 된 이미지와 선택 되지 않은 이미지를 교환 하 여이 절차를 보여 줍니다.

[!code-cpp[NVC_MFCControlLadenDialog#13](../mfc/codesnippet/cpp/setting-the-images-for-an-individual-item_2.cpp)]

## <a name="see-also"></a>참고자료

[CComboBoxEx 사용](../mfc/using-ccomboboxex.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
