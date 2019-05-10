---
title: MFC 클래스 추가 마법사
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.mfc.simple.overview
helpviewer_keywords:
- MFC Add Class Wizard
- wizards [MFC]
ms.assetid: ad3b0989-d307-43b2-9417-3f9a78889024
ms.openlocfilehash: fa9b947ae6fc0e48aaecde61e35a5f4152c85f27
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412737"
---
# <a name="mfc-add-class-wizard"></a>MFC 클래스 추가 마법사

이 코드 마법사를 사용 하 여 기존 MFC 프로젝트에 클래스를 추가 또는 MFC를 지 원하는 ATL 프로젝트에 클래스를 추가 합니다. 또한 MFC를 지 원하는 Win32 프로젝트에 MFC 클래스를 추가할 수 있습니다. 프로젝트를 만들 때 지정한 기능이 대화 상자에서 사용할 수 있는 옵션을 결정 합니다.

## <a name="names"></a>이름

이 페이지에서는 클래스 이름, 기본 클래스 및 새 클래스에 대 한 파일 이름을 지정 합니다.

- **클래스 이름**

  새 클래스의 이름을 지정 하 고 기본 기반 Id 및이 페이지에 있는 파일의 이름을 제공 합니다. C++일반적으로 클래스 예를 들어 "CMyClass"가 "MyClass.h", "C"로 시작 합니다.

- **기본 클래스**

  새 클래스에 대 한 기본 클래스의 이름을 지정합니다. 기본 클래스는 기본적으로 [CWnd](../../mfc/reference/cwnd-class.md)합니다. 선택한 기본 클래스는이 페이지의 다른 상자 active 지 확인 합니다.

  기본 클래스를 클래스에는 대화 ID 또는 리소스 ID가 있는지 여부를 결정 하는 대로 설정한 클래스의 형식 클래스의 일반 형식은 아래와 같습니다.

  - 와 같은 클래스 [CButton](../../mfc/reference/cbutton-class.md)를 [CWnd](../../mfc/reference/cwnd-class.md), 또는 [CDocument](../../mfc/reference/cdocument-class.md), 대화 상자를이 필요 하지 않은 ID 또는 리소스 id입니다. 이러한 클래스는 대화 상자 또는 리소스 ID를 사용 하지 않습니다. 기본 클래스에 대 한 이러한 클래스 중 하나를 선택 하는 경우는 **대화 상자 ID** 상자와 **DHTML 리소스 ID** 상자 흐리게 표시 됩니다.

  - 와 같은 클래스 [CDialog](../../mfc/reference/cdialog-class.md)를 [CFormView](../../mfc/reference/cformview-class.md), 또는 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)에 대화 ID 필요

  - 클래스 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md), 대화 상자 ID, DHTML 리소스 ID, 및는 HTML 파일 이름이 필요 합니다.

  대화 ID를 필요로 하는 클래스에 대 한 것이 보다 효율적으로 사용할 합니다 [리소스 편집기](../../windows/resource-editors.md) 대화 상자 리소스를 만들려면에서 해당 ID를 할당 합니다 [속성 창](/visualstudio/ide/reference/properties-window)을 만든 다음 관련 된 클래스 리소스 ID를 사용 하 여 참조 [새 대화 상자 만들기](../../windows/creating-a-new-dialog-box.md) 표준 Windows 대화 상자 만들기에 대 한 자세한 내용은 합니다.

  > [!NOTE]
  > 대화 상자 리소스를 먼저 만들고 경우에서 새 클래스를 파생 `CDHtmlDialog`, 표준 Windows 삭제 **확인** 하 고 **취소** 기본 대화 상자에 나타나는 단추입니다. 표준 Windows 대화 상자 호스트 자체를 포함 하는 DHTML 양식의 **확인** 하 고 **취소** 단추입니다.

  대화 상자는 Windows 컨트롤 및 DHTML 컨트롤 모두를 포함할 수 있지만 권장 되지 않습니다.

- **대화 상자 ID**

  선택한 경우 대화의 ID를 지정 `CDialog`, `CFormView`를 `CPropertyPage`, 또는 `CDHtmlDialog` 으로 **기본 클래스**합니다.

- **.h 파일**

  새 개체 클래스에 대한 헤더 파일의 이름을 설정합니다. 기본적으로 이 이름은 **클래스 이름**에 지정한 이름을 기반으로 합니다. 파일 이름을 선택한 위치에 저장하거나 클래스 선언을 기존 파일에 추가하려면 줄임표 단추를 클릭합니다. 기존 파일을 선택하면 마법사에서 **마침**을 클릭해야 해당 파일이 선택한 위치에 저장됩니다.

  마법사는 파일을 덮어쓰지 않습니다. 기존 파일의 이름을 선택하면 마법사에서 **마침**을 클릭할 때 클래스 선언을 파일의 내용에 추가해야 하는지 여부를 나타내는 메시지가 표시됩니다. **예**를 클릭하여 파일을 추가하거나, **아니요**를 클릭하여 마법사로 돌아가서 다른 파일 이름을 지정합니다.

- **.cpp 파일**

  새 개체의 클래스에 대한 구현 파일의 이름을 설정합니다. 기본적으로 이 이름은 **클래스 이름**에 지정한 이름을 기반으로 합니다. 파일 이름을 선택한 위치에 저장하려면 줄임표 단추를 클릭합니다. 마법사에서 **마침**을 클릭해야 해당 파일이 선택한 위치에 저장됩니다.

  마법사는 파일을 덮어쓰지 않습니다. 기존 파일의 이름을 선택하면 마법사에서 **마침**을 클릭할 때 클래스 구현을 파일의 내용에 추가해야 하는지 여부를 나타내는 메시지가 표시됩니다. **예**를 클릭하여 파일을 추가하거나, **아니요**를 클릭하여 마법사로 돌아가서 다른 파일 이름을 지정합니다.

- **Active accessibility**

  호출 하 여 Active Accessibility에 대 한 MFC의 지 [EnableActiveAccessibility](../../mfc/reference/cwnd-class.md#enableactiveaccessibility) 생성자에서. 파생 된 클래스에서이 옵션은 사용할 수 있습니다 [CWnd](../../mfc/reference/cwnd-class.md)합니다.

- **DHTML 리소스 ID**

  파생 된 클래스에 적용 됩니다 `CDHtmlDialog` 만 합니다. DHTML 대화 상자를의 리소스 ID를 지정합니다. 리소스 ID는 HTML 대화 상자 파일 이름과 함께 프로젝트의.rc 파일의 HTML 섹션에 표시 됩니다. 로 식별 되는 대화 상자에이 ID로 식별 되는 DHTML 리소스는 호스팅됩니다 **대화 상자 ID**합니다.

- **. HTM 파일**

  파생 된 클래스에 적용 됩니다 `CDHtmlDialog` 만 합니다. DHTML 대화 상자에 대 한 HTML 파일의 이름을 설정합니다. 기본적으로이 파일 이름은 클래스 이름을 기반으로 합니다. 파일 이름을 DHTML 대화 상자 리소스 ID와 함께 프로젝트의.rc 파일의 HTML 섹션에 표시 됩니다.

- **자동화**

  수준을 설정 합니다. 클래스에 대 한 지원이 [Automation](../../mfc/automation.md)합니다. 클래스 수준에서 자동화는 자동화를 지 원하는 모든 클래스에 대해 사용할 수 있습니다. Automation에 대 한 지원을 사용 하 여 만든 프로젝트에 사용할 수 이기도 합니다. 중 하나는 MFC 프로젝트 즉, [ATL 지원](../../atl/reference/mfc-support-in-atl-projects.md), 또는 선택 된 MFC 프로젝트를 **Automation** 확인란을 [고급 기능](../../mfc/reference/advanced-features-mfc-application-wizard.md) MFC의 페이지 응용 프로그램 마법사입니다.

  |옵션|설명|
  |------------|-----------------|
  |**없음**|클래스가 자동화를 지원 하지에 있음을 나타냅니다.|
  |**자동화**|클래스가 자동화를 지원함을 나타냅니다. 이 옵션을 선택 하면 새로 생성된 된 클래스는 Microsoft Visual Basic 및 Microsoft Excel과 같은 자동화 클라이언트 응용 프로그램에서 프로그래밍 가능한 개체로 사용할 수 있습니다. 이 옵션을이 테이블 다음에 나열 되는 기본 클래스에 사용할 수 없는 경우|
  |**Creatable 형식 ID로**|클래스 및 프로젝트 모두에서 다른 응용 프로그램 자동화를 사용 하 여이 클래스의 개체를 만드는 지 나타냅니다. 이 옵션을 사용 하 여 자동화 클라이언트 자동화 개체를 직접 만들 수 있습니다. 만들려는; 개체를 지정 클라이언트 응용 프로그램에서 유형 ID 텍스트 상자에는 시스템 전반에 걸쳐 이며 고유 해야 합니다. 이 옵션을이 테이블 다음에 나열 되는 기본 클래스에 사용할 수 없는 경우|

  다음 기본 클래스에 대 한 automation 지원 하지 않습니다.

  - `CAsyncMonitorFile`

  - `CAsyncSocket`

  - `CCachedDataPathProperty`

  - `CConnectionPoint`

  - `CDatabase`

  - `CDataPathProperty`

  - `CHttpFilter`

  - `CHttpServer`

  - `CInternetSession`

  - `CObject`

  - `CSocket`

- **유형 ID**

  클래스의 형식 ID를 설정 합니다. **유형 ID** 상자 프로젝트 이름 및 새 클래스 이름을 연결 다음과 같습니다. *MFCProj.MFCClass*. 이 ID를 선택한 경우에 변경할 수는 **Automation** 옵션 **Creatable 형식 ID로**합니다.

- **DocTemplate 리소스를 생성 합니다.**

  문서 템플릿 리소스가 응용 프로그램에서 만든 문서 했음을 나타냅니다. 이 확인란을 활성화 하려면 프로젝트에는 MFC 문서/뷰 아키텍처를 지원 해야 하며이 클래스의 기본 클래스 여야 [CFormView](../../mfc/reference/cformview-class.md)합니다.

  참조 [문서 템플릿 및 문서/뷰 만들기 프로세스](../../mfc/document-templates-and-the-document-view-creation-process.md) 자세한 내용은 합니다.

## <a name="see-also"></a>참고자료

[MFC 클래스](../../mfc/reference/adding-an-mfc-class.md)<br/>
[클래스 추가](../../ide/adding-a-class-visual-cpp.md)
