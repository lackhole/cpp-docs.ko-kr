---
title: 'MFC ActiveX 컨트롤: 최적화'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], windowless
- flicker-free ActiveX controls
- MFC ActiveX controls [MFC], mouse interaction
- device contexts, unclipped for MFC ActiveX controls
- MFC ActiveX controls [MFC], optimizing
- performance, ActiveX controls
- optimization, ActiveX controls
- MFC ActiveX controls [MFC], flicker-free
- windowless MFC ActiveX controls
- MFC ActiveX controls [MFC], active/inactive state
- optimizing performance, ActiveX controls
ms.assetid: 8b11f26a-190d-469b-b594-5336094a0109
ms.openlocfilehash: 08cbb5ab0ff9b8c165e549bc2b250daebc1ce177
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62186894"
---
# <a name="mfc-activex-controls-optimization"></a>MFC ActiveX 컨트롤: 최적화

이 문서에는 성능 향상을 위해 ActiveX 컨트롤을 최적화 하 여 기술을 설명 합니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용 되지 해야 하는 레거시 기술입니다. ActiveX를 대체 하는 최신 기술에 대 한 자세한 내용은 참조 하세요. [ActiveX 컨트롤](activex-controls.md)합니다.

항목 [설정 Off the 활성화 되었을 때 표시 옵션](../mfc/turning-off-the-activate-when-visible-option.md) 하 고 [제공 마우스 상호 작용 하는 동안 비활성](../mfc/providing-mouse-interaction-while-inactive.md) 활성화 될 때까지 창을 만들지는 컨트롤에 설명 합니다. 항목 [창 없는 활성화 제공](../mfc/providing-windowless-activation.md) 활성화 되는 경우에 창을 만들지는 컨트롤에 설명 합니다.

Windows가 OLE 개체에 대 한 두 가지 주요 단점이: 개체에서 활성 상태인 경우 방지 및 인스턴스화 및 컨트롤의 표시에 큰 오버 헤드를 추가 합니다. 일반적으로 창을 만드는 컨트롤을 만들 때의 60%가 됩니다. 단일 공유 창 (일반적으로 컨테이너의) 및 디스패치 일부 코드를 사용 하 여 컨트롤을 성능 손실 없이 일반적으로 동일한 창 서비스를 받습니다. 창 것 대부분 불필요 한 오버 헤드는 개체에 대 한 합니다.

일부 최적화 수행 성능이 반드시 향상 되지 컨트롤 특정 컨테이너에서 사용 되는 경우. 예를 들어 컨테이너 1996 이전에 릴리스된이 기능을 구현에서 오래 된 컨테이너의 혜택을 제공 하지 않습니다 있도록 창 없는 활성화를 지원 하지 않았습니다. 그러나 거의 모든 컨테이너 컨트롤의 지 속성 코드 최적화 모든 컨테이너의 성능이 개선 될 가능성이 높습니다 하므로 지 속성을 지원 합니다. 컨트롤은 특정 유형의 컨테이너를 사용 하 여 사용할 데 특히 경우 조사 하려면 해당 컨테이너에서 사용할 수 있는 이러한 최적화. 그러나 일반적으로 하려고 해야 다양 한 컨테이너의에서 컨트롤 잘 작동할 수 있도록 특정 컨트롤에 적용할 수는 이러한 기술 대부분와 구현 합니다.

이러한 최적화를 통해 많은 구현할 수 있습니다는 [MFC ActiveX 컨트롤 마법사](../mfc/reference/mfc-activex-control-wizard.md)의 합니다 [제어 설정을](../mfc/reference/control-settings-mfc-activex-control-wizard.md) 페이지.

### <a name="mfc-activex-control-wizard-ole-optimization-options"></a>MFC ActiveX 컨트롤 마법사 OLE 최적화 옵션

|MFC ActiveX 컨트롤 마법사에서 컨트롤 설정|작업|추가 정보|
|-------------------------------------------------------|------------|----------------------|
|**표시 되었을 때 활성화** 확인란|지우기|[해제를 활성화 하는 경우 표시 옵션](../mfc/turning-off-the-activate-when-visible-option.md)|
|**창 없는 활성화** 확인란|선택|[창 없는 활성화 제공](../mfc/providing-windowless-activation.md)|
|**잘리지 않는 장치 컨텍스트** 확인란|선택|[잘리지 않는 디바이스 컨텍스트 사용](../mfc/using-an-unclipped-device-context.md)|
|**깜빡임 없는 활성화** 확인란|선택|[깜빡임 없는 활성화 제공](../mfc/providing-flicker-free-activation.md)|
|**마우스 포인터 알림 비활성 상태일 때** 확인란|선택|[비활성 상태 중 마우스 상호 작용 제공](../mfc/providing-mouse-interaction-while-inactive.md)|
|**그리기 코드 최적화** 확인란|선택|[컨트롤 그리기 최적화](../mfc/optimizing-control-drawing.md)|

이러한 최적화를 구현 하는 멤버 함수에 대 한 자세한 내용은 [COleControl](../mfc/reference/colecontrol-class.md)합니다.

자세한 내용은 다음을 참조하세요.

- [지속성 및 초기화 최적화](../mfc/optimizing-persistence-and-initialization.md)

- [창 없는 활성화 제공](../mfc/providing-windowless-activation.md)

- [해제를 활성화 하는 경우 표시 옵션](../mfc/turning-off-the-activate-when-visible-option.md)

- [비활성 상태 중 마우스 상호 작용 제공](../mfc/providing-mouse-interaction-while-inactive.md)

- [깜빡임 없는 활성화 제공](../mfc/providing-flicker-free-activation.md)

- [잘리지 않는 디바이스 컨텍스트 사용](../mfc/using-an-unclipped-device-context.md)

- [컨트롤 그리기 최적화](../mfc/optimizing-control-drawing.md)

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)
