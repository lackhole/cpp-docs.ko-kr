---
title: MFC ActiveX 컨트롤 만들기
ms.date: 09/12/2018
f1_keywords:
- vc.appwiz.activex.project
helpviewer_keywords:
- MFC ActiveX controls [MFC], creating
- ActiveX controls [MFC], creating
ms.assetid: 8bd5a93c-d04d-414e-bb28-163fdc1c0dd5
ms.openlocfilehash: b2dc48e2568e180820f8bca008c66878af4b575e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372298"
---
# <a name="creating-an-mfc-activex-control"></a>MFC ActiveX 컨트롤 만들기

ActiveX 컨트롤 프로그램은 부모 응용 프로그램에 특정 종류의 기능을 제공 하도록 설계는 모듈식 프로그램입니다. 예를 들어 대화 상자에서 또는 웹 페이지에서 사용 하 여 도구 모음에서 사용할 단추와 같은 컨트롤을 만들면 됩니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용 되지 해야 하는 레거시 기술입니다. 자세한 내용은 [ActiveX 컨트롤](../activex-controls.md)합니다.

MFC ActiveX 컨트롤을 만드는 가장 쉬운 방법은 사용 하는 것은 [MFC ActiveX 컨트롤 마법사](../../mfc/reference/mfc-activex-control-wizard.md)합니다.

### <a name="to-create-an-mfc-activex-control-using-the-mfc-activex-control-wizard"></a>MFC ActiveX 컨트롤 마법사를 사용 하 여 MFC ActiveX 컨트롤을 만들려면

1. 도움말 항목의 지침을 따릅니다 [만들기를 C++ 콘솔 앱 프로젝트](../../get-started/tutorial-console-cpp.md)합니다.

1. 에 **새 프로젝트** 대화 상자를 선택 합니다 **MFC ActiveX 컨트롤** MFC ActiveX 컨트롤 마법사를 열려면 템플릿 창에서 아이콘입니다.

1. 정의 [응용 프로그램 설정](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)를 [컨트롤 이름](../../mfc/reference/control-names-mfc-activex-control-wizard.md), 및 [설정을 제어](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) MFC ActiveX 컨트롤 마법사를 사용 하 여 합니다.

    > [!NOTE]
    >  마법사의 기본 설정을 그대로 유지하려면 이 단계를 건너 뜁니다.

1. 클릭 **완료** 마법사를 닫고 개발 환경에서 새 프로젝트를 엽니다.

프로젝트를 만든 후에 만들어진 파일을 볼 수 있습니다 **솔루션 탐색기**합니다. 마법사에서 프로젝트용으로 만드는 파일에 대한 자세한 내용은 프로젝트 생성 파일인 ReadMe.txt를 참조하세요. 파일 형식에 대 한 자세한 내용은 참조 하세요. [시각적 개체에 대해으로 만들어지는 파일 형식 C++ 프로젝트](../../build/reference/file-types-created-for-visual-cpp-projects.md)합니다.

프로젝트를 만든 후 추가할 코드 마법사를 사용할 수 있습니다 [함수](../../ide/add-member-function-wizard.md), [변수](../../ide/add-member-variable-wizard.md), [이벤트](../../ide/add-event-wizard.md)하십시오 [속성](../../ide/names-add-property-wizard.md), 및 [메서드](../../ide/add-method-wizard.md)합니다. ActiveX 컨트롤을 사용자 지정 하는 방법에 대 한 자세한 내용은 참조 하세요. [MFC ActiveX 컨트롤](../../mfc/mfc-activex-controls.md)합니다.

## <a name="see-also"></a>참고자료

[코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[속성 페이지(Visual C++)](../../build/reference/property-pages-visual-cpp.md)

