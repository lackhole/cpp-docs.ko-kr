---
title: 적용 단추 처리
ms.date: 11/04/2016
helpviewer_keywords:
- Apply button in property sheet
- property sheets, Apply button
ms.assetid: 7e977015-59b8-406f-b545-aad0bfd8d55b
ms.openlocfilehash: 30ee549a334a684deeb4a845f2fc49ee8bbe11db
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58770839"
---
# <a name="handling-the-apply-button"></a>적용 단추 처리

속성 시트 기능이 표준 대화 상자는 그렇지 않습니다. 속성 시트를 닫기 전에 변경한 내용을 적용 하려면 사용자를 수 있습니다. 이 작업 수행 [적용] 단추를 사용 하 여 합니다. 이 문서에서는이 기능을 제대로 구현 하려면 사용할 수 있습니다 하는 방법을 설명 합니다.

일반적으로 모달 대화 상자 대화 상자를 닫으려면 확인을 두 번 클릭할 때 설정을 외부 개체에 게 적용 합니다. 속성 시트에 대 한 마찬가지입니다. 사용자가 확인을 클릭 하면 속성 시트에서 새 설정을 적용 합니다.

그러나 다음 사용자가 속성 시트 대화 상자를 종료 하지 않고 설정을 저장 하도록 허용 하는 것이 좋습니다. 이것이 [적용] 단추의 기능입니다. [적용] 단추 외부 개체에 현재 페이지의 현재 설정을 적용 하는 대신 모든 속성 페이지의 현재 설정을 적용 합니다.

기본적으로 [적용] 단추 항상 비활성화 됩니다. 적절 한 시간에 [적용] 단추를 사용 하도록 설정 하려면 코드를 작성 해야 하 고 아래 설명 된 대로 적용의 효과 구현 하는 코드를 작성 해야 합니다.

사용자에 게 적용 기능을 제공 하려는 경우 [적용] 단추를 제거할 필요 하지 않습니다. Windows의 향후 버전에서 사용할 수 있는 표준 속성 시트 지원을 사용 하는 응용 프로그램에 공통적으로 사용 하지 않도록 둘 수 있습니다.

수정 되는 페이지를 보고 하 고 [적용] 단추를 사용 하도록 설정 하려면 호출 `CPropertyPage::SetModified( TRUE )`합니다. 보고 수정 하 고 있는 경우 [적용] 단추 현재 활성 페이지가 수정 되었는지 여부에 관계 없이 설정 된 상태로 유지 됩니다.

호출 해야 [CPropertyPage::SetModified](../mfc/reference/cpropertypage-class.md#setmodified) 사용자가 페이지에서 모든 설정을 변경할 때마다 합니다. 사용자 페이지에서 설정을 변경 하는 시기를 감지 하는 한 가지 방법은 같은 각 속성 페이지에서 컨트롤에 대 한 변경 알림 처리기를 구현 하는 것 **EN_CHANGE** 하거나 **BN_CLICKED**합니다.

[적용] 단추의 효과 구현 하려면 속성 시트가 해당 소유자 또는 일부 기타 외부 개체 속성 페이지에서 현재 설정을 적용 하려면 응용 프로그램에 지시 해야 합니다. 같은 시간에 속성 시트를 사용 하지 않도록 [적용] 단추를 호출 하 여 `CPropertyPage::SetModified( FALSE )` 외부 개체에 해당 수정 내용을 적용 하는 모든 페이지에 대 한 합니다.

이 프로세스는 예로, MFC 일반 샘플을 참조 하세요 [PROPDLG](../overview/visual-cpp-samples.md)합니다.

## <a name="see-also"></a>참고자료

[속성 시트](../mfc/property-sheets-mfc.md)
