---
title: 마법사 역할을 하는 속성 시트
ms.date: 11/04/2016
helpviewer_keywords:
- property sheets, as wizards
ms.assetid: 1ea66ecb-23b0-484a-838d-58671a2999b5
ms.openlocfilehash: c60148c099b34993bef0c9808e6561e37c26cc7f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391363"
---
# <a name="property-sheets-as-wizards"></a>마법사 역할을 하는 속성 시트

마법사 속성 시트의 주요 특징 탐색 탭 대신 다음 또는 다시, Finish 및 Cancel 단추와 함께 제공 되는 경우 호출할 필요가 [CPropertySheet::SetWizardMode](../mfc/reference/cpropertysheet-class.md#setwizardmode) 호출 하기 전에 [CPropertySheet::DoModal](../mfc/reference/cpropertysheet-class.md#domodal) 이 기능을 활용 하려면 속성 시트 개체입니다.

사용자에 게 동일한 [CPropertyPage::OnSetActive](../mfc/reference/cpropertypage-class.md#onsetactive) 하 고 [CPropertyPage::OnKillActive](../mfc/reference/cpropertypage-class.md#onkillactive) 한 페이지에서 다른 페이지로 이동 하는 동안 알림. 다음 마침 단추와 함께 사용할 수 없는 컨트롤입니다. 즉, 한 번에 둘 중 하나만 표시 됩니다. 첫 번째 페이지에서 다음 단추를 사용 해야 합니다. 마지막 페이지에서 사용자 인 경우에 "마침" 단추를 활성화 되어야 합니다. 이렇게 하지 않으면 자동으로 프레임 워크에서. 호출 해야 [CPropertySheet::SetWizardButton](../mfc/reference/cpropertysheet-class.md#setwizardbuttons) 이렇게 하려면 마지막 페이지입니다.

모든 기본 단추를 표시 하려면 모두 "마침" 단추를 표시 하 고 단추를 이동 합니다. 다음 단추를 상대 위치로 유지 되도록 한 다음 뒤로 단추를 이동 합니다.

## <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#5](../mfc/codesnippet/cpp/property-sheets-as-wizards_1.cpp)]

## <a name="see-also"></a>참고자료

[속성 시트](../mfc/property-sheets-mfc.md)
