---
title: 머리글 항목을 사용자 지정&#39;모양
ms.date: 11/04/2016
helpviewer_keywords:
- header controls [MFC], customization of items
- CHeaderCtrl class [MFC], customizing the items
- HDS_ styles
ms.assetid: b1e1e326-ec7d-4dbd-a46f-96a3e2055618
ms.openlocfilehash: 081260bd5c1cf6335d398a4fd773c9590dbc8030
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62241588"
---
# <a name="customizing-the-header-item39s-appearance"></a>머리글 항목을 사용자 지정&#39;모양

설정 하 여 합니다 *dwStyle* 헤더 컨트롤을 처음 만들 때 매개 변수 ([CHeaderCtrl::Create](../mfc/reference/cheaderctrl-class.md#create)), 모양을 정의할 수 있으며 헤더의 동작은 항목 또는 헤더 컨트롤 자체입니다.

샘플링을 설정할 수 있는 스타일 및 용도 다음과 같습니다.

- 누름 같이 머리글 항목을 사용 합니다 **HDS_BUTTONS** 스타일입니다.

   Microsoft Outlook에서와 같이 특정 열에 의해 데이터 정렬 등의 헤더 항목에 대해 마우스 클릭에 대 한 응답으로 작업을 수행 하려는 경우에이 스타일을 사용 합니다.

- 에 부여 하려면 헤더 항목에 "핫 트래킹을" 모양으로 표시 하려면 마우스 커서를 위로 가져갈 때 사용 합니다 **사용 하려면 HDS_HOTTRACK** 스타일입니다.

   그렇지 않으면 플랫의 항목 위에 포인터를 움직이면 3D 개요를 표시 하는 핫 트래킹 모음입니다.

- 헤더 컨트롤을 숨겨야 함을 나타내려면 사용 합니다 **HDS_HIDDEN** 스타일입니다.

   합니다 **HDS_HIDDEN** 스타일은 헤더 컨트롤 데이터 컨테이너 및 시각적 컨트롤이 아닌로 사용할 것을 나타냅니다. 이 스타일 컨트롤을 자동으로 숨겨지지 않습니다 하지만 대신의 동작에 영향을 `CHeaderCtrl::Layout`입니다. 반환 되는 값을 *cy* 의 멤버는 `WINDOWPOS` 구조는 0이 됩니다 컨트롤은 사용자에 게 표시할 수 없음을 나타내는.

이러한 속성에 대 한 자세한 내용은 참조 하세요. [항목](/windows/desktop/Controls/header-controls) Windows SDK에 있습니다. 헤더 컨트롤에 항목을 추가 하는 방법에 대 한 내용은 [헤더 컨트롤에 항목 추가](../mfc/adding-items-to-the-header-control.md)합니다.

## <a name="see-also"></a>참고자료

[CHeaderCtrl 사용](../mfc/using-cheaderctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
