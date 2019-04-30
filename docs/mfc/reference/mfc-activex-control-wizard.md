---
title: MFC ActiveX 컨트롤 마법사
ms.date: 09/12/2018
f1_keywords:
- vc.appwiz.mfc.ctl.overview
helpviewer_keywords:
- ActiveX controls [MFC], MFC
- MFC ActiveX controls [MFC], wizards
- OLE controls [MFC], creating
- MFC ActiveX Control Wizard
- OLE controls [MFC]
ms.assetid: f19d698c-bdc3-4c74-af97-3d6ccb441b75
ms.openlocfilehash: cec4c3aa6aedfa7a1f8234c6cc2355970d453f56
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412776"
---
# <a name="mfc-activex-control-wizard"></a>MFC ActiveX 컨트롤 마법사

ActiveX 컨트롤은 특정 유형의 [자동화 서버](../../mfc/automation-servers.md);는 재사용 가능한 구성 요소입니다. ActiveX 컨트롤을 호스팅하는 응용 프로그램은는 [자동화 클라이언트](../../mfc/automation-clients.md) 해당 컨트롤입니다. 이러한 재사용 가능한 구성 요소를 만드는 것이 목표 라면 컨트롤을 만드는이 마법사를 사용 합니다. 참조 [MFC ActiveX 컨트롤](../../mfc/mfc-activex-controls.md) 자세한 내용은 합니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용 되지 해야 하는 레거시 기술입니다. ActiveX를 대체 하는 최신 기술에 대 한 자세한 내용은 참조 하세요. [ActiveX 컨트롤](../activex-controls.md)합니다.

자동화 서버 MFC를 통해 응용 프로그램을 만들 수는 또는 [MFC 응용 프로그램 마법사](../../mfc/reference/mfc-application-wizard.md)합니다.

이 마법사를 사용 하 여 만든 ActiveX 컨트롤의 사용자 인터페이스를 가질 수 있습니다 또는 표시 되지 않을 수도 있습니다. 이 옵션을 지정할 수 있습니다 합니다 [제어 설정을](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) 마법사의 페이지입니다. 타이머 컨트롤은 표시 되지 않도록 하려면 원하는 ActiveX 컨트롤의 예입니다.

ActiveX 컨트롤에는 복잡 한 사용자 인터페이스를 사용할 수 있습니다. 캡슐화 된 폼과 같은 일부 컨트롤 수 있습니다: 다를 포함 하는 단일 컨트롤 필드를 각각 그 자체로 Windows 컨트롤입니다. 예를 들어, MFC ActiveX 컨트롤로 구현 자동차 부품 개체 폼 형태의 사용자 인터페이스는 사용자 수 읽기 및 편집 부품 번호, 파트 이름 및 기타 정보를 발생할 수 있습니다. 참조 [MFC ActiveX 컨트롤](../../mfc/mfc-activex-controls.md) 자세한 내용은 합니다.

ActiveX 개체에 대 한 컨테이너를 만들어야 하는 경우 참조 [ActiveX 컨트롤 컨테이너를 만들려면](../../mfc/reference/creating-an-mfc-activex-control-container.md)합니다.

MFC 스타터 프로그램에 포함 된 C++ 소스 파일 (.cpp), 리소스 (.rc) 파일 및 프로젝트 (.vcxproj) 파일입니다. 이 기초 파일에서 생성 된 코드는 MFC를 기반으로 합니다.

다음 샘플은 태스크 및 ActiveX 컨트롤에 대 한 향상 된 기능 유형을 보여 줍니다.

- [ActiveX 컨트롤 최적화](../../mfc/mfc-activex-controls-optimization.md)

- [ActiveX 컨트롤에 스톡 이벤트 추가](../../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)

- [사용자 지정 이벤트 추가](../../mfc/mfc-activex-controls-adding-custom-events.md)

- [스톡 메서드 추가](../../mfc/mfc-activex-controls-adding-stock-methods.md)

- [사용자 지정 메서드 추가](../../mfc/mfc-activex-controls-adding-custom-methods.md)

- [스톡 속성 추가](../../mfc/mfc-activex-controls-adding-stock-properties.md)

- [사용자 지정 속성 추가](../../mfc/mfc-activex-controls-adding-custom-properties.md)

- [ActiveX 컨트롤 컨테이너에서 ActiveX 컨트롤 프로그래밍](../../mfc/programming-activex-controls-in-a-activex-control-container.md)

## <a name="overview"></a>개요

이 마법사 페이지에는 만들려는 MFC ActiveX 컨트롤 프로젝트에 대 한 현재 응용 프로그램 설정을 설명 합니다. 기본적으로 마법사를 다음과 같이 프로젝트를 만듭니다.

- 기본 프로젝트 없는 런타임 라이선스 또는 도움말 파일을 생성합니다. 이러한 기본 설정을 변경할 수 있습니다 합니다 [응용 프로그램 설정](../../mfc/reference/application-settings-mfc-activex-control-wizard.md) 페이지입니다. ActiveX 컨트롤 마법사의이 페이지에서 선택한 내용만 반영 합니다 **개요** 페이지입니다.

- 프로젝트에는 컨트롤 클래스 및 프로젝트의 이름을 기반으로 하는 속성 페이지 클래스를 포함 합니다. 프로젝트 및 파일 이름의 이름을 편집할 수는 [컨트롤 이름](../../mfc/reference/control-names-mfc-activex-control-wizard.md) 페이지입니다.

- 컨트롤 없는 기존 Windows 컨트롤을 기반으로, 표시 되 고, 사용자 인터페이스가 하 고 포함 하는 경우 활성화 되는 **에 대 한** 대화 상자. 이러한 기본 설정을 변경할 수 있습니다 합니다 [제어 설정을](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) 페이지입니다.

## <a name="see-also"></a>참고자료

[Visual C++ 프로젝트 만들기 및 관리](../../build/creating-and-managing-visual-cpp-projects.md)<br/>
[Visual C++ 프로젝트 형식](../../build/reference/visual-cpp-project-types.md)<br/>
[개념](../../atl/active-template-library-atl-concepts.md)
