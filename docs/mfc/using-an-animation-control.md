---
title: 애니메이션 컨트롤 사용
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], animation
- CAnimateCtrl class [MFC], animation controls
- animation controls [MFC]
ms.assetid: a009a464-e12d-4112-bf52-04a09b28dd88
ms.openlocfilehash: 10bd8c0c26f92ce5de2261d6aca6fc7cc3a37365
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180505"
---
# <a name="using-an-animation-control"></a>애니메이션 컨트롤 사용

애니메이션 컨트롤의 일반적인 사용 패턴을 따릅니다.

- 컨트롤이 만들어집니다. 컨트롤이 대화 상자 템플릿에 지정될 경우 대화 상자를 만들 때 자동으로 만들어집니다. (해야는 [CAnimateCtrl](../mfc/reference/canimatectrl-class.md) 애니메이션 컨트롤에 해당 하는 대화 상자 클래스의 멤버입니다.) 사용할 수 있습니다 합니다 [만들기](../mfc/reference/canimatectrl-class.md#create) 모든 창의 자식 창으로 컨트롤을 만드는 데 멤버 함수입니다.

- AVI 클립을 호출 하 여 애니메이션 컨트롤에 로드 된 [열려](../mfc/reference/canimatectrl-class.md#open) 멤버 함수입니다. 애니메이션 컨트롤 대화 상자에서이 작업을 수행 하는 것이 좋습니다 경우 대화 상자 클래스의 [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) 함수입니다.

- 호출 하 여 클립을 재생 합니다 [재생](../mfc/reference/canimatectrl-class.md#play) 멤버 함수입니다. 애니메이션 컨트롤 대화 상자에서이 작업을 수행 하는 것이 좋습니다 경우 대화 상자 클래스의 `OnInitDialog` 함수입니다. 호출 `Play` 애니메이션 컨트롤 스타일이 ACS_AUTOPLAY 설정 하는 경우 필요 하지 않습니다.

- 클립의 일부를 표시 하거나 프레임별으로 사용 하 여 재생 하려는 경우는 `Seek` 멤버 함수입니다. 클립의 재생을 중지 하려면 사용 된 `Stop` 멤버 함수입니다.

- 컨트롤을 즉시 삭제 하려는 경우 클립 메모리에서 호출 하 여 제거를 `Close` 멤버 함수입니다.

- 애니메이션 컨트롤이 대화 상자에 있으면이 고 `CAnimateCtrl` 개체는 자동으로 소멸 됩니다. 그렇지 않은 경우 컨트롤 및 `CAnimateCtrl` 개체가 모두 제대로 소멸되었는지 확인해야 합니다. 컨트롤을 자동으로 제거 AVI 클립을 닫습니다.

## <a name="see-also"></a>참고자료

[CAnimateCtrl 사용](../mfc/using-canimatectrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
