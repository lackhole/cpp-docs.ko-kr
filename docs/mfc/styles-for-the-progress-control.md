---
title: 진행률 컨트롤 스타일
ms.date: 11/19/2018
helpviewer_keywords:
- PBS_SMOOTH style
- progress controls [MFC], styles
- PBS_VERTICAL style
- CProgressCtrl class [MFC], styles
ms.assetid: 39eb8081-bc20-4552-91b9-e7cdd1b7d8ae
ms.openlocfilehash: 3adbd32456b1375bd2dc8574220e083ca3d83ee9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62306816"
---
# <a name="styles-for-the-progress-control"></a>진행률 컨트롤 스타일

진행률 컨트롤을 처음 만들기 ([CProgressCtrl::Create](../mfc/reference/cprogressctrl-class.md#create))를 사용 합니다 *dwStyle* 진행률 컨트롤에 대 한 원하는 창 스타일을 지정 하려면 매개 변수. 다음은 적용할 수 있는 창 스타일을 자세히 설명합니다. 컨트롤은 여기에 나열 된 것 이외의 모든 창 스타일을 무시 합니다. 일반적으로 대화 상자 부모의 자식 창으로 컨트롤 항상 만들어야 합니다.

|창 스타일|효과|
|------------------|------------|
|WS_BORDER|창 주위에 테두리를 만듭니다.|
|WS_CHILD|자식 창을 만듭니다 (에 항상 사용할 `CProgressCtrl`).|
|WS_CLIPCHILDREN|부모 창 안에서 그릴 경우 자식 창이 차지 하는 영역을 제외 합니다. 부모 창을 만들 때 사용 합니다.|
|WS_CLIPSIBLINGS|서로 기준으로 자식 창을 자릅니다.|
|WS_DISABLED|처음부터 사용할 수 있는 창을 만듭니다.|
|WS_VISIBLE|처음에 표시 되는 창을 만듭니다.|
|WS_TABSTOP|이동 하려면 TAB 키를 누를 때 컨트롤이 포커스를 받을 수 있는지를 지정 합니다.|

또한 두 스타일 진행률 컨트롤에만 적용 되는 PBS_VERTICAL 및 PBS_SMOOTH를 지정할 수 있습니다.

PBS_VERTICAL 가로로 아닌 세로 방향으로 컨트롤 하려면 사용 합니다. PBS_SMOOTH를 사용 하 여 증분 방식으로 컨트롤을 작성 하는 작은 구분 된 사각형을 표시 하지 않고 컨트롤을 완전히 채웁니다.

PBS_SMOOTH 스타일 없이:

![표준 진행률 막대 스타일](../mfc/media/vc4ruw1.gif "표준 진행률 막대 스타일")

PBS_SMOOTH 및 PBS_VERTICAL 스타일를 사용 하 여:

![진행률 표시줄 스타일을 원활 하 고 세로](../mfc/media/vc4ruw2.gif "진행률 막대 스타일을 원활 하 고 세로")

자세한 내용은 [창 스타일](../mfc/reference/styles-used-by-mfc.md#frame-window-styles-mfc) 에 *MFC 참조*합니다.

## <a name="see-also"></a>참고자료

[CProgressCtrl 사용](../mfc/using-cprogressctrl.md)
