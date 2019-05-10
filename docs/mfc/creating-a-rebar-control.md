---
title: Rebar 컨트롤 만들기
ms.date: 11/04/2016
helpviewer_keywords:
- rebar controls [MFC], creating
- CReBarCtrl class [MFC], creating
ms.assetid: 0a012e08-772b-4f6a-af86-7cb651d11d3e
ms.openlocfilehash: 0fb651aef599b64b787d96a668e2e1496c1dff8e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62153347"
---
# <a name="creating-a-rebar-control"></a>Rebar 컨트롤 만들기

[CReBarCtrl](../mfc/reference/crebarctrl-class.md) 부모 개체가 표시 되기 전에 개체를 만들어야 합니다. 이렇게 하면 그리기 문제가 발생할 가능성이 최소화됩니다.

예를 들어, rebar 컨트롤(프레임 창 개체에 사용)은 일반적으로 도구 모음 컨트롤에 대한 부모 창으로 사용됩니다. 따라서 rebar 컨트롤의 부모는 프레임 창 개체입니다. 프레임 창 개체가 부모이기 때문에, 해당 부모의 `OnCreate` 멤버 함수는 rebar 컨트롤을 생성하기 위한 최적의 위치입니다.

`CReBarCtrl` 개체를 사용하려면, 일반적으로 다음 단계를 수행해야 합니다.

### <a name="to-use-a-crebarctrl-object"></a>CReBarCtrl 개체를 사용하려면

1. 생성 된 [CReBarCtrl](../mfc/reference/crebarctrl-class.md) 개체입니다.

1. 호출 [Create](../mfc/reference/crebarctrl-class.md#create) Windows rebar 공용 컨트롤을 만들고 연결 하는 `CReBarCtrl` 개체를 원하는 스타일을 지정 합니다.

1. 호출 하 여 비트맵을 로드 [CBitmap::LoadBitmap](../mfc/reference/cbitmap-class.md#loadbitmap), rebar 컨트롤 개체의 배경으로 사용할 수 있습니다.

1. rebar 컨트롤 개체에 포함되는 모든 자식 창 개체(도구 모음, 대화 상자 컨트롤 등)를 만들고 초기화합니다.

1. 초기화 된 **REBARBANDINFO** 를 삽입할 밴드에 필요한 정보를 사용 하 여 구조입니다.

1. 호출 [InsertBand](../mfc/reference/crebarctrl-class.md#insertband) 기존 자식 창에 삽입할 (같은 `m_wndReToolBar`) 새 rebar 컨트롤에 있습니다. 참조를 기존 rebar 컨트롤 밴드를 삽입 하는 방법은 [Rebar 컨트롤 및 밴드](../mfc/rebar-controls-and-bands.md)합니다.

## <a name="see-also"></a>참고자료

[CReBarCtrl 사용](../mfc/using-crebarctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
