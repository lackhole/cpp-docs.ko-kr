---
title: 'MFC ActiveX 컨트롤: 앰비언트 속성 액세스'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], accessing ambient properties
- properties [MFC], accessing ambient
ms.assetid: fdc9db29-e6b0-45d2-a879-8bd60e2058a7
ms.openlocfilehash: 585ec8720a654bbcb728330d70ddb914f2543e41
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62239741"
---
# <a name="mfc-activex-controls-accessing-ambient-properties"></a>MFC ActiveX 컨트롤: 앰비언트 속성 액세스

이 문서에서는 ActiveX 컨트롤을 컨트롤 컨테이너의 앰비언트 속성에 액세스할 수는 방법을 설명 합니다.

컨트롤은 컨테이너의 앰비언트 속성에 액세스 하 여 해당 컨테이너에 대 한 정보를 가져올 수 있습니다. 이러한 속성은 컨테이너의 배경색을 컨테이너 인지 현재 사용자 모드 또는 디자이너 모드와 같은 컨테이너 및 작업 특성에 의해 사용 된 현재 글꼴 등의 시각적 특성을 노출 합니다. 컨트롤을 앰비언트 속성을 사용 하 여 모양과 동작을 포함 하는 특정 컨테이너에 맞게 수 있습니다. 그러나 컨트롤은 해당 컨테이너에서 모든 앰비언트 속성을 지원 하는지을 가정 하지 않아야 합니다. 사실, 일부 컨테이너는 앰비언트 속성을 전혀 지원 하지 않을 수 있습니다. 가 없을 경우 앰비언트 속성의 컨트롤을 적절 한 기본값을 가정해 야 합니다.

앰비언트 속성에 액세스 하려면 호출할 [COleControl::GetAmbientProperty](../mfc/reference/colecontrol-class.md#getambientproperty)합니다. 이 함수는 첫 번째 매개 변수 (olectl 앰비언트 속성에 대 한 디스패치 ID. H 정의 앰비언트 속성의 표준 집합에 대 한 디스패치 Id)입니다.

매개 변수는 `GetAmbientProperty` 함수를 디스패치 ID, variant 태그는 필요한 속성 형식 및 메모리에 대 한 포인터를 나타내는 값을 반환 해야 합니다. 이 포인터 참조 하는 데이터 형식을 variant 태그에 따라 달라 집니다. 함수 반환 **TRUE** 컨테이너 속성을 지 원하는 경우 그렇지 않으면 반환 **FALSE**합니다.

다음 코드 예제에서는 "UserMode." 라는 앰비언트 속성의 값을 가져옵니다. 속성의 기본값을 컨테이너에서 지원 되지 않습니다 **TRUE** 것으로 간주 됩니다.

[!code-cpp[NVC_MFC_AxUI#30](../mfc/codesnippet/cpp/mfc-activex-controls-accessing-ambient-properties_1.cpp)]

사용자 편의 위해 `COleControl` 대부분의 자주 사용 되는 앰비언트 속성 액세스 및 속성을 사용할 수 없는 경우 적절 한 기본값을 반환 하는 도우미 함수를 제공 합니다. 이러한 도우미 함수는 다음과 같습니다.

- [COleControl::AmbientBackColor](../mfc/reference/colecontrol-class.md#ambientbackcolor)

- [AmbientDisplayName](../mfc/reference/colecontrol-class.md#ambientdisplayname)

- [AmbientFont](../mfc/reference/colecontrol-class.md#ambientfont)

    > [!NOTE]
    >  호출자가 호출 해야 `Release( )` 반환 된 글꼴에 따라 합니다.

- [AmbientForeColor](../mfc/reference/colecontrol-class.md#ambientforecolor)

- [AmbientLocaleID](../mfc/reference/colecontrol-class.md#ambientlocaleid)

- [AmbientScaleUnits](../mfc/reference/colecontrol-class.md#ambientscaleunits)

- [AmbientTextAlign](../mfc/reference/colecontrol-class.md#ambienttextalign)

- [AmbientUserMode](../mfc/reference/colecontrol-class.md#ambientusermode)

- [AmbientUIDead](../mfc/reference/colecontrol-class.md#ambientuidead)

- [AmbientShowHatching](../mfc/reference/colecontrol-class.md#ambientshowhatching)

- [AmbientShowGrabHandles](../mfc/reference/colecontrol-class.md#ambientshowgrabhandles)

(몇 가지 작업 컨테이너의)을 통해 앰비언트 속성의 값이 변경 된 `OnAmbientPropertyChanged` 컨트롤의 멤버 함수를 호출 합니다. 이러한 알림 메시지를 처리 하려면이 멤버 함수를 재정의 합니다. 매개 변수가 `OnAmbientPropertyChanged` 영향을 받는 앰비언트 속성의 디스패치 ID입니다. 이 디스패치 ID의 값 DISPID_UNKNOWN 하나 이상의 앰비언트 속성이 변경 되었음을 나타냅니다.에 될 수 있지만 영향을 받은 속성에 대 한 정보를 사용할 수 없습니다.

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)
