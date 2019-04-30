---
title: 모덜리스 속성 시트 만들기
ms.date: 11/04/2016
helpviewer_keywords:
- modeless property sheets
- property sheets, modeless
- Create method [MFC], property sheets
ms.assetid: eafd8a92-cc67-4a69-a5fb-742c920d1ae8
ms.openlocfilehash: 39285927b67091f5b8762dab56009712d806d259
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407993"
---
# <a name="creating-a-modeless-property-sheet"></a>모덜리스 속성 시트 만들기

일반적으로 만든 속성 시트 모달 됩니다. 모달 속성 시트를 사용 하는 경우 사용자 응용 프로그램의 다른 부분을 사용 하기 전에 속성 시트를 닫아야 합니다. 이 문서에는 응용 프로그램의 다른 부분을 사용 하는 동안 속성 시트를 열어 사용자를 허용 하는 모덜리스 속성 시트를 만드는 데 사용할 수 있는 방법을 설명 합니다.

속성 시트 모달 대화 상자로 대신 모덜리스 대화 상자로 표시할 호출 [CPropertySheet::Create](../mfc/reference/cpropertysheet-class.md#create) of [DoModal](../mfc/reference/cpropertysheet-class.md#domodal)합니다. 모덜리스 속성 시트를 지원 하기 위해 몇 가지 추가 작업을 구현 해야 합니다.

속성 시트 및 속성 시트 열려 있는 경우 수정 하는 외부 개체 간에 데이터를 교환 하는 추가 작업 중 하나입니다. 이 일반적으로 표준 모덜리스 대화 상자와 같은 작업입니다. 이 작업의 일부로 모덜리스 속성 시트 및 속성 설정을 적용 하는 외부 개체 간의 통신 채널을 구현 합니다. 이 구현은에서 클래스를 파생 하는 경우 훨씬 [CPropertySheet](../mfc/reference/cpropertysheet-class.md) 모덜리스 속성 시트에 대 한 합니다. 이 문서에서는 않았으면 지금 가정 합니다.

모덜리스 속성 시트와 외부 간 통신 하는 한 가지 방법은 개체 (예: 보기에서 현재 선택) 속성 시트에서 외부 개체에 대 한 포인터를 정의 하는 것입니다. 함수를 정의 (같은 호출 `SetMyExternalObject`)에 `CPropertySheet`-파생 클래스 간 외부 개체에서 포커스가 변경 될 때마다 포인터를 변경 합니다. `SetMyExternalObject` 함수 새로 선택된 된 외부 개체를 반영 하도록 각 속성 페이지에 대 한 설정을 다시 설정 해야 합니다. 이를 위해를 `SetMyExternalObject` 함수에 액세스할 수 있어야 합니다 [CPropertyPage](../mfc/reference/cpropertypage-class.md) 에 속하는 개체는 `CPropertySheet` 클래스.

속성 시트에서 속성 페이지에 대 한 액세스를 제공 하는 가장 편리한 방법은 포함 하는 것은 `CPropertyPage` 개체는 `CPropertySheet`-파생 개체입니다. 포함 `CPropertyPage` 개체를 `CPropertySheet`-모달 대화 상자, 속성 시트의 소유자를 만들어 위치에 대 한 일반적인 디자인에서 파생 된 개체와 다른 합니다 `CPropertyPage` 개체를 통해 속성 시트에 전달 [ CPropertySheet::AddPage](../mfc/reference/cpropertysheet-class.md#addpage)합니다.

모덜리스 속성 시트의 설정의 외부 개체에 적용 해야 하는 경우를 결정 하기 위한 사용자 인터페이스 다른 방법도 많습니다 있습니다. 한 가지 대안은 사용자 값이 변경 될 때마다 현재 속성 페이지의 설정을 적용 하는 것입니다. 또 다른 방법은 외부 개체에 커밋하기 전에 속성 페이지에서 변경 내용을 누적 할 수 있는 적용 단추를 제공 하는 것입니다. [적용] 단추를 처리 하는 방법에 대 한 내용은 문서 참조 [적용 단추 처리](../mfc/handling-the-apply-button.md)합니다.

## <a name="see-also"></a>참고자료

[속성 시트](../mfc/property-sheets-mfc.md)<br/>
[데이터 교환](../mfc/exchanging-data.md)<br/>
[대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)
