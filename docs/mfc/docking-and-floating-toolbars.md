---
title: 도구 모음 고정 및 고정 해제
ms.date: 11/04/2016
f1_keywords:
- CBRS_SIZE_DYNAMIC
- CBRS_SIZE_FIXED
helpviewer_keywords:
- size [MFC], toolbars
- size
- frame windows [MFC], toolbar docking
- CBRS_ALIGN_ANY constant [MFC]
- palettes, floating
- toolbars [MFC], docking
- CBRS_SIZE_DYNAMIC constant [MFC]
- floating toolbars
- toolbars [MFC], size
- toolbars [MFC], floating
- fixed-size toolbars
- CBRS_SIZE_FIXED constant [MFC]
- toolbar controls [MFC], wrapping
- toolbars [MFC], wrapping
- floating palettes
ms.assetid: b7f9f9d4-f629-47d2-a3c4-2b33fa6b51e4
ms.openlocfilehash: 01450dca56ad662c8db0a35f89749c4a288109b3
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58768136"
---
# <a name="docking-and-floating-toolbars"></a>도구 모음 고정 및 고정 해제

Microsoft Foundation Class 라이브러리를 도킹 가능한 도구 모음을 지원합니다. 도킹 가능한 도구 모음을 연결 하거나, 부모 창의 모든 쪽에 도킹 된 수 또는 분리 하거나 자체 미니 프레임 창에서 이동할 수 있습니다. 이 문서에서는 응용 프로그램에서 도킹 가능한 도구 모음을 사용 하는 방법에 설명 합니다.

응용 프로그램 마법사를 사용 하 여 응용 프로그램의 기본 구조를 생성 하 도킹 가능한 도구 모음 여부를 선택 하 라는 메시지가 표시 됩니다. 기본적으로 응용 프로그램 마법사에서는 응용 프로그램에서 도킹 가능한 도구 모음을 배치 하는 데 필요한 세 가지 작업을 수행 하는 코드를 생성 합니다.

- [프레임 창의 도킹을 사용 하도록 설정](#_core_enabling_docking_in_a_frame_window)합니다.

- [도구 모음의 도킹을 사용 하도록 설정](#_core_enabling_docking_for_a_toolbar)합니다.

- [(프레임 창)에 도구 모음을 도킹](#_core_docking_the_toolbar)합니다.

다음이 단계 중 하나라도 값이 없는 경우 응용 프로그램에 표준 도구 모음이 표시 됩니다. 응용 프로그램에서 각 도킹 가능한 도구 모음에 대 한 마지막 두 단계를 수행 해야 합니다.

이 문서에서 다루는 다른 항목은 다음과 같습니다.

- [부동 도구 모음](#_core_floating_the_toolbar)

- [도구 모음을 동적으로 크기 조정](#_core_dynamically_resizing_the_toolbar)

- [고정 스타일 도구 모음에 대 한 줄 바꿈 위치 설정](#_core_setting_wrap_positions_for_a_fixed_style_toolbar)

MFC 일반 샘플을 참조 하세요 [DOCKTOOL](../overview/visual-cpp-samples.md) 예입니다.

##  <a name="_core_enabling_docking_in_a_frame_window"></a> 프레임 창의 도킹을 사용 하도록 설정

프레임 창에 도구 모음을 고정 하려면 프레임 창 (또는 대상) 도킹 수 있도록 활성화 되어야 합니다. 이렇게 사용 하 여는 [CFrameWnd::EnableDocking](../mfc/reference/cframewnd-class.md#enabledocking) 하나를 사용 하는 함수 *DWORD* 스타일의 집합에는 매개 변수가 도킹 프레임 창 중 어느 쪽을 허용할 나타내는 비트입니다. 매개 변수 전달 도구 모음을 도킹할 되려고 하 고 여러 측면에 도킹 될 수 있는에 표시 된 측면 `EnableDocking` 다음 순서 대로 사용 됩니다: 위쪽, 아래쪽, 왼쪽, 오른쪽입니다. 도킹 컨트롤 막대를 모든 수 있게 되기를 원하는 경우, 전달 **CBRS_ALIGN_ANY** 에 `EnableDocking`입니다.

##  <a name="_core_enabling_docking_for_a_toolbar"></a> 도구 모음의 도킹을 사용 하도록 설정

도킹에 대 한 대상을 준비한 후 비슷한 방식으로 도구 모음 (또는 원본)를 준비 해야 합니다. 호출 [CControlBar::EnableDocking](../mfc/reference/ccontrolbar-class.md#enabledocking) 도킹 하려면 각 도구 모음에 대 한 도구 모음 도킹 해야 면 대상을 지정 합니다. 호출에 지정 된 면 없으면 `CControlBar::EnableDocking` 프레임 창에서 도킹 가능한 면 일치, 도구 모음 도킹 없습니다-float 됩니다. 되 면 부동 도구 모음, 프레임 창으로 도킹 될 수 없습니다 유지 됩니다.

원하는 효과 영구적으로 부동 도구 모음 이면 호출 `EnableDocking` 0 매개 변수를 사용 합니다. 그런 다음 호출 [CFrameWnd::FloatControlBar](../mfc/reference/cframewnd-class.md#floatcontrolbar)합니다. 도구 모음에는 부동, 도킹 될 수 없습니다 영구적으로 유지 됩니다.

##  <a name="_core_docking_the_toolbar"></a> 도구 모음 도킹

프레임 워크 호출 [CFrameWnd::DockControlBar](../mfc/reference/cframewnd-class.md#dockcontrolbar) 사용자가 프레임 창의 도킹을 허용 하는 쪽에서 도구 모음을 삭제 하려고 할 때입니다.

또한 언제 든 지 컨트롤 막대 프레임 창으로 도킹이 함수를 호출할 수 있습니다. 일반적으로 초기화 하는 동안 수행 됩니다. 둘 이상의 도구 모음 프레임 창의 특정 쪽에 도킹 될 수 있습니다.

##  <a name="_core_floating_the_toolbar"></a> 부동 도구 모음

프레임 창에서 도킹 가능한 도구 모음을 분리 부동 도구 모음 이라고 합니다. 호출 [CFrameWnd::FloatControlBar](../mfc/reference/cframewnd-class.md#floatcontrolbar) 에이 작업을 수행 합니다. 도구 모음 놓을지,이 배치할 위치, 지점 및 부동 도구 모음에서 가로 또는 세로 인지를 결정 하는 맞춤 스타일을 지정 합니다.

프레임 워크는 사용자 도구 모음 도킹 된 위치로 해제 끌 하 고 도킹 해제 되어 없는 위치에 넣습니다.이 함수를 호출 합니다. 내부 또는 프레임 창 외부 아무 곳 이나 수 있습니다. 와 마찬가지로 `DockControlBar`를 초기화 하는 동안이 함수를 호출할 수도 있습니다.

도킹 가능한 도구 모음의 MFC 구현 도킹 가능한 도구 모음을 지 원하는 일부 응용 프로그램에 있는 확장된 기능 중 일부를 제공 하지 않습니다. 사용자 지정 가능한 도구 모음 같은 기능을 제공 되지 않습니다.

##  <a name="_core_dynamically_resizing_the_toolbar"></a> 도구 모음을 동적으로 크기 조정

시각적 개체를 기준으로 C++ 버전 4.0, 있습니다 수 있게 부동 도구 모음 크기를 동적으로 조정 하려면 응용 프로그램의 사용자에 대 한 합니다. 일반적으로 도구 모음에 가로로 표시 되 긴 막대 모양입니다. 하지만 도구 모음의 방향 및 모양을 변경할 수 있습니다. 예를 들어, 사용자 도킹 프레임 창의 세로 측면 중 하나에 대 한 도구 모음, 모양을 세로 레이아웃으로 변경 합니다. 도구 모음 단추의 여러 행을 사용 하 여 사각형에 변형 수 이기도 합니다.

다음과 같은 작업을 수행할 수 있습니다.

- 동적 크기 조정 도구 모음 특성으로 지정 합니다.

- 도구 모음 특징으로 고정된 크기를 지정 합니다.

이 지원을 제공할, 가지에 대 한 호출에서 사용 하기 위해 두 개의 새 도구 모음 스타일을 [CToolBar::Create](../mfc/reference/ctoolbar-class.md#create) 멤버 함수입니다. 다음 창이 여기에 포함됩니다.

- **CBRS_SIZE_DYNAMIC** 동적 컨트롤 막대입니다.

- **CBRS_SIZE_FIXED** 컨트롤 막대 고정 됩니다.

동적 크기 스타일 부동 창인 것은 없지만 도킹 되는 동안 하지 도구 모음 크기를 조정 하 여 사용자를 수 있습니다. 도구 모음에서 "래핑" 가장자리를 끌 때 모양을 변경 해야 하는 경우.

스타일 고정 크기의 각 열에서 단추 위치를 수정 하는 도구 모음, 줄 바꿈 상태를 유지 합니다. 응용 프로그램의 사용자는 도구 모음의 모양을 변경할 수 없습니다. 도구 모음 단추 간에 구분 기호의 위치와 같은 지정 된 위치를 래핑합니다. 도구 모음 도킹 하거나 부동 인지이 모양을 유지 합니다. 여러 열의 단추를 사용 하 여 색상표를 고정된 됩니다.

사용할 수도 있습니다 [CToolBar::GetButtonStyle](../mfc/reference/ctoolbar-class.md#getbuttonstyle) 도구 모음에서 상태 및 단추에 대 한 스타일을 반환 합니다. 단추의 스타일 단추를 표시 하는 방법 및 사용자 입력에 응답 하는 방법 결정 상태 래핑된에서 단추 인지 여부를 알려 줍니다.

##  <a name="_core_setting_wrap_positions_for_a_fixed_style_toolbar"></a> 고정 스타일 도구 모음에 대 한 줄 바꿈 위치 설정

고정 크기 스타일을 사용 하 여 도구 모음에 대 한 도구 모음을 도구 모음을 바꿈됩니다 단추 인덱스 지정 합니다. 다음 코드를 주 프레임 창에서이 작업을 수행 하는 방법을 보여 줍니다 `OnCreate` 재정의:

[!code-cpp[NVC_MFCDocViewSDI#10](../mfc/codesnippet/cpp/docking-and-floating-toolbars_1.cpp)]

MFC 일반 샘플 [DOCKTOOL](../overview/visual-cpp-samples.md) 클래스의 멤버 함수를 사용 하는 방법을 보여 줍니다 [CControlBar](../mfc/reference/ccontrolbar-class.md) 하 고 [CToolBar](../mfc/reference/ctoolbar-class.md) 동적 레이아웃 도구 모음을 관리할 수 있습니다. EDITBAR 파일을 참조 하십시오. CPP 파일을 참조 합니다.

### <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [도구 모음 기본 사항](../mfc/toolbar-fundamentals.md)

- [도구 모음 도구 설명](../mfc/toolbar-tool-tips.md)

- [이전 도구 모음 사용](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>참고자료

[MFC 도구 모음 구현](../mfc/mfc-toolbar-implementation.md)
