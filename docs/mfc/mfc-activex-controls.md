---
title: MFC ActiveX 컨트롤
ms.date: 11/19/2018
f1_keywords:
- MFC ActiveX Controls (MFC)
helpviewer_keywords:
- COleControl class [MFC], MFC ActiveX controls
- ActiveX controls [MFC], MFC
- containers [MFC], MFC ActiveX controls
- MFC ActiveX controls [MFC], serializing
- MFC ActiveX controls [MFC], containers
- serialization [MFC], MFC ActiveX controls
- dispatch maps [MFC], for MFC ActiveX controls
- MFC ActiveX controls [MFC], active/inactive state
- events [MFC], ActiveX controls
- MFC ActiveX controls [MFC]
ms.assetid: c911fb74-3afc-4bf3-a0f5-7922b14d9a1b
ms.openlocfilehash: d10aad92088a02a1cab0977ea174abdf919a05e9
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58769214"
---
# <a name="mfc-activex-controls"></a>MFC ActiveX 컨트롤

ActiveX 컨트롤은 다양한 OLE 기능을 지원하고 많은 소프트웨어 요구 사항에 맞게 사용자 지정할 수 있는 COM(구성 요소 개체 모델)을 기반으로 재사용 가능한 소프트웨어 구성 요소입니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용 되지 해야 하는 레거시 기술입니다. 자세한 내용은 [ActiveX 컨트롤](activex-controls.md)합니다.

ActiveX 컨트롤은 일반적인 ActiveX 컨트롤 컨테이너와 인터넷의 World Wide Web 웹 페이지 모두에 사용할 수 있도록 디자인되었습니다. ActiveX 컨트롤 또는 여기에서 사용 하 여 설명 된 MFC를 사용 하 여 만들 수는 [액티브 템플릿 라이브러리 (ATL)](../atl/active-template-library-atl-concepts.md)합니다.

고유한 창에서 ActiveX 컨트롤을 그리고, 이벤트(예: 마우스 클릭)에 응답하고, 자동화 개체와 유사한 속성과 메서드를 포함한 인터페이스를 통해 관리할 수 있습니다.

이러한 컨트롤은 데이터베이스 액세스, 데이터 모니터링 또는 그래프 작성 등의 여러 용도로 개발될 수 있습니다. ActiveX 컨트롤은 이식성 외에도 기존 OLE 컨테이너와의 호환성과 해당 메뉴를 기존 OLE 컨테이너 메뉴와 통합하는 기능 등 이전에는 ActiveX 컨트롤에서 가능하지 않았던 기능을 지원합니다. 또한 ActiveX 컨트롤은 컨트롤이 읽기/쓰기 속성 및 컨트롤 사용자가 호출할 수 있는 메서드 집합을 노출하도록 허용하는 자동화를 완벽하게 지원합니다.

창 없는 ActiveX 컨트롤과 활성화될 때만 창을 만드는 컨트롤을 만들 수 있습니다. 창 없는 컨트롤은 응용 프로그램의 표시 속도를 높이며 이를 통해 투명하고 사각형 모양이 아닌 컨트롤을 만들 수 있습니다. ActiveX 컨트롤 속성을 비동기적으로 로드할 수도 있습니다.

ActiveX 컨트롤은 OLE 컨테이너에서 사용할 수 있는 In-process 서버(일반적으로 작은 개체)로 구현됩니다. ActiveX 컨트롤의 전체 기능은 ActiveX 컨트롤을 인식하도록 디자인된 OLE 컨테이너 내에서 사용하는 경우에만 사용할 수 있습니다. 참조 [포트 ActiveX 컨트롤을 다른 응용 프로그램](../mfc/containers-for-activex-controls.md) ActiveX 컨트롤을 지 원하는 컨테이너의 목록은 합니다. 이 컨테이너 형식("컨트롤 컨테이너")은 컨트롤의 속성 및 메서드를 사용하여 ActiveX 컨트롤을 작동할 수 있으며 이벤트의 형식으로 ActiveX 컨트롤에서 알림을 받습니다. 다음 그림에서는 이 상호 작용을 보여 줍니다.

![ActiveX 컨트롤 컨테이너와 컨트롤의 상호 작용](../mfc/media/vc37221.gif "컨트롤과 상호 작용의 ActiveX 컨트롤 컨테이너") <br/>
ActiveX 컨트롤 컨테이너와 창 있는 ActiveX 컨트롤 간의 상호 작용

ActiveX 컨트롤 최적화에 최신 정보를 참조 하세요. [MFC ActiveX 컨트롤: 최적화](../mfc/mfc-activex-controls-optimization.md)합니다.

MFC ActiveX 컨트롤을 참조 하세요 [ActiveX 컨트롤 프로젝트를 만들고](../mfc/reference/mfc-activex-control-wizard.md)합니다.

자세한 내용은 다음을 참조하세요.

- [ActiveX 컨트롤 컨테이너](../mfc/activex-control-containers.md)

- [활성 문서](../mfc/active-documents.md)

- [ActiveX 컨트롤 이해](/windows/desktop/com/activex-controls)

- [인터넷에서 사용할 기존 ActiveX 컨트롤 업그레이드](../mfc/upgrading-an-existing-activex-control.md)

##  <a name="_core_basic_components_of_an_activex_control"></a> ActiveX 컨트롤의 기본 구성 요소

ActiveX 컨트롤은 컨트롤 컨테이너와 사용자 간의 효율적인 상호 작용을 위해 몇 가지 프로그래밍 요소를 사용합니다. 클래스는 이러한 [COleControl](../mfc/reference/colecontrol-class.md), 일련의 이벤트 발생 함수 및 디스패치 맵.

개발되는 모든 ActiveX 컨트롤 개체는 MFC 기본 클래스인 `COleControl`에서 강력한 기능 집합을 상속받습니다. 이러한 기능에는 내부 활성화 및 자동화 논리가 포함됩니다. `COleControl`은 컨트롤 개체에 MFC 창 개체와 동일한 기능과 이벤트를 발생시키는 기능을 제공합니다. `COleControl` 제공할 수도 있습니다 [창 없는 컨트롤](../mfc/providing-windowless-activation.md)를 사용 하는 해당 컨테이너에 대 한 일부의 기능을 사용 하 여 도움말 창을 제공 (마우스 캡처, 키보드 포커스, 스크롤), 훨씬 빠르게 표시 하지만 합니다.

`COleControl`에서 파생되는 컨트롤 클래스이므로 특정한 조건이 충족될 경우 컨트롤 컨테이너에 이벤트를 호출하는 메시지를 보내거나 "발생"시키는 기능을 상속합니다. 이러한 이벤트는 컨트롤에서 중요한 사항이 발생하는 경우 컨트롤 컨테이너에 알리는 데 사용됩니다. 매개 변수를 이벤트에 연결하여 이벤트에 대한 추가 정보를 컨트롤 컨테이너에 전송할 수 있습니다. ActiveX 컨트롤의 이벤트에 대 한 자세한 내용은 문서를 참조 하세요. [MFC ActiveX 컨트롤: 이벤트](../mfc/mfc-activex-controls-events.md)합니다.

마지막 요소인 디스패치 맵은 함수(메서드)와 특성(속성)의 집합을 컨트롤 사용자에게 보여주는 데 사용됩니다. 속성을 통해 컨트롤 컨테이너 또는 컨트롤 사용자는 다양한 방법으로 컨트롤을 조작할 수 있습니다. 사용자는 컨트롤의 모양과 특정 값을 변경할 수 있으며, 컨트롤이 유지하는 데이터의 특정 부분에 액세스하도록 하는 컨트롤을 요청할 수 있습니다. 이 인터페이스는 컨트롤 개발자가 결정 되며 사용 하 여 정의 됩니다 **클래스 뷰**합니다. ActiveX 컨트롤의 메서드 및 속성에 대 한 자세한 내용은 문서를 참조 하세요. [MFC ActiveX 컨트롤: 메서드](../mfc/mfc-activex-controls-methods.md) 하 고 [속성](../mfc/mfc-activex-controls-properties.md)합니다.

##  <a name="_core_interaction_between_controls_with_windows_and_activex_control_containers"></a> Windows 사용 하 여 컨트롤 및 ActiveX 컨트롤 컨테이너 간의 상호 작용

컨트롤 컨테이너 내에서 컨트롤을 사용하는 경우 통신을 위해 속성 및 메서드를 노출하고 이벤트를 발생시키는 두 가지 메커니즘을 사용합니다. 다음 그림에서는 이러한 두 가지 메커니즘이 구현되는 방법에 대해 보여 줍니다.

![ActiveX 컨트롤 컨테이너와 통신](../mfc/media/vc37222.gif "ActiveX 컨트롤 컨테이너와 통신") <br/>
ActiveX 컨트롤 컨테이너와 ActiveX 컨트롤 간의 통신

이전 그림은 다른 OLE 인터페이스(자동화 및 이벤트의 경우)가 컨트롤을 통해 처리되는 방법도 보여 줍니다.

컨테이너를 사용하는 모든 컨트롤의 통신은 `COleControl`에 의해 수행됩니다. 컨테이너의 요청을 처리 하기 위한 `COleControl` 컨트롤 클래스에서 구현 되는 함수 멤버를 호출 합니다. 모든 메서드와 일부 속성은 이러한 방식으로 처리됩니다. 컨트롤 클래스는 `COleControl`의 멤버 함수를 호출하여 컨테이너와 통신을 시작할 수도 있습니다. 이러한 방식으로 이벤트가 발생합니다.

##  <a name="_core_active_and_inactive_states_of_an_activex_control"></a> ActiveX 컨트롤의 활성 및 비활성 상태

컨트롤은 활성 및 비활성의 두 가지 기본 상태를 가집니다. 일반적으로 이러한 상태는 컨트롤에 창이 있는지 여부에 따라 구분됩니다. 활성 컨트롤에는 창이 있지만 비활성 컨트롤에는 창이 없습니다. 창 없는 활성화의 도입으로 이러한 구분은 더 이상 일반적이지 않지만 여전히 많은 컨트롤에 적용됩니다.

경우는 [창 없는 컨트롤](../mfc/providing-windowless-activation.md) 활성화 마우스 캡처, 키보드 포커스, 스크롤링 및 해당 컨테이너의 다른 창 서비스를 호출 합니다. 할 수도 있습니다 [비활성 컨트롤에 마우스 상호 작용 제공](../mfc/providing-mouse-interaction-while-inactive.md)컨트롤을 만들 뿐 [창을 만들기 위해 활성화 될 때까지 기다립니다](../mfc/turning-off-the-activate-when-visible-option.md)합니다.

창이 있는 컨트롤이 활성화되면 해당 컨트롤은 컨트롤 컨테이너, 사용자 및 Windows와 완전히 상호 작용할 수 있습니다. 아래 그림에서는 ActiveX 컨트롤, 컨트롤 컨테이너 및 운영 체제 간의 통신 경로를 보여 줍니다.

![활성 창 있는 ActiveX 컨트롤에서 msg 처리](../mfc/media/vc37223.gif "활성 창 있는 ActiveX 컨트롤에서 Msg 처리") <br/>
창 있는 ActiveX 컨트롤의 Windows 메시지 처리(활성화된 경우)

##  <a name="_core_serializing_activex_elements"></a> Serialization

영구성이라고도 하는 데이터를 serialize 기능을 통해 컨트롤은 영구 저장소에 해당 속성 값을 작성할 수 있습니다. 그런 다음 저장소에서 개체의 상태를 읽어들여서 컨트롤을 다시 만들 수 있습니다.

컨트롤에서는 저장소 매체에 대한 액세스를 얻지 않습니다. 대신 컨트롤의 컨테이너가 적절한 때에 사용하기 위해 컨트롤에 저장소 매체를 제공합니다. Serialization에 대 한 자세한 내용은 문서를 참조 하세요. [MFC ActiveX 컨트롤: 직렬화](../mfc/mfc-activex-controls-serializing.md)합니다. Serialization 최적화에 대 한 정보를 참조 하세요 [영 구성 최적화 및 초기화](../mfc/optimizing-persistence-and-initialization.md) ActiveX 컨트롤에서: 최적화 합니다.

##  <a name="_core_installing_activex_control_classes_and_tools"></a> ActiveX 컨트롤 클래스 및 도구 설치

Visual C++를 설치할 때 설치에서 ActiveX 컨트롤을 선택한 경우(기본적으로 선택됨) MFC ActiveX 컨트롤 클래스와 일반 정품 및 디버그 ActiveX 컨트롤 런타임 DLL이 자동으로 설치됩니다.

기본적으로 ActiveX 컨트롤 클래스 및 도구는 Visual Studio.NET \Program Files\Microsoft 다음 하위 디렉터리에 설치 됩니다.

- **\Common7\Tools**

   테스트 컨테이너 파일(TstCon32.exe 및 해당 도움말 파일)을 포함합니다.

- **\Vc7\atlmfc\include**

   MFC로 ActiveX 컨트롤을 개발하는 데 필요한 포함 파일을 포함합니다.

- **\Vc7\atlmfc\src\mfc**

   MFC에서 특정 ActiveX 컨트롤 클래스에 대한 소스 코드를 포함합니다.

- **\Vc7\atlmfc\lib**

   MFC로 ActiveX 컨트롤을 개발하는 데 필요한 라이브러리를 포함합니다.

MFC ActiveX 컨트롤에 대한 샘플도 있습니다. 이러한 샘플에 대 한 자세한 내용은 참조 하세요. [컨트롤 샘플: MFC 기반 ActiveX 컨트롤](../overview/visual-cpp-samples.md)

## <a name="see-also"></a>참고자료

[사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)
