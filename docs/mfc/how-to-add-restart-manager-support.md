---
title: '방법: 다시 시작 관리자 지원 추가'
ms.date: 11/04/2016
helpviewer_keywords:
- Restart manager [MFC]
- C++, application crash support
ms.assetid: 7f3f5867-d4bc-4ba8-b3c9-dc1e7be93642
ms.openlocfilehash: 23f860c43c63e3153f4b87f8eaf05d61709af82f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389530"
---
# <a name="how-to-add-restart-manager-support"></a>방법: 다시 시작 관리자 지원 추가

다시 시작 관리자는 Windows Vista 용 Visual Studio 또는 이후 운영 체제에 추가 기능입니다. 다시 시작 관리자는 예기치 않게 닫히거나 다시 시작되는 경우 애플리케이션에 대한 지원을 추가합니다. 다시 시작 관리자의 동작은 애플리케이션의 유형에 따라 달라집니다. 애플리케이션이 문서 편집기인 경우 다시 시작 관리자는 예기치 않게 닫힌 후 애플리케이션에서 열려 있는 문서의 상태 및 내용을 자동으로 저장하도록 하고 애플리케이션을 다시 시작합니다. 애플리케이션이 문서 편집기가 아닌 경우 다시 시작 관리자는 애플리케이션을 다시 시작하지만 기본적으로 애플리케이션의 상태를 저장할 수 없습니다.

다시 시작한 후 애플리케이션이 유니코드이면 애플리케이션에 작업 대화 상자가 표시됩니다. ANSI 애플리케이션이면 Windows 메시지 상자가 애플리케이션에 표시됩니다. 이때 사용자는 자동으로 저장된 문서를 복원할지 여부를 선택합니다. 사용자가 자동으로 저장된 문서를 복원하지 않으면 다시 시작 관리자는 임시 파일을 삭제합니다.

> [!NOTE]
>  데이터를 저장하고 애플리케이션을 다시 시작하는 다시 시작 관리자의 기본 동작을 재정의할 수 있습니다.

기본적으로 응용 프로그램은 Windows Vista 또는 이후 운영 체제를 컴퓨터에서 실행 될 때 Visual Studio에서 프로젝트 마법사를 사용 하 여 만든 MFC 응용 프로그램 다시 시작 관리자를 지원 합니다. 애플리케이션에서 다시 시작 관리자를 지원하지 않도록 하려면 새 프로젝트 마법사에서 다시 시작 관리자를 사용하지 않도록 설정할 수 있습니다.

### <a name="to-add-support-for-the-restart-manager-to-an-existing-application"></a>기존 애플리케이션에 다시 시작 관리자에 대한 지원을 추가하려면

1. Visual Studio에서 기존 MFC 응용 프로그램을 엽니다.

1. 주 애플리케이션에 대한 원본 파일을 엽니다. 기본적으로 애플리케이션과 동일한 이름을 사용하는 .cpp 파일입니다. 예를 들어 MyProject에 대한 주 애플리케이션 원본 파일은 MyProject.cpp입니다.

1. 주 애플리케이션에 대한 생성자를 찾습니다. 예를 들어 프로젝트가 MyProject인 경우 생성자는 `CMyProjectApp::CMyProjectApp()`입니다.

1. 생성자에 다음 코드 줄을 추가합니다.

```
    m_dwRestartManagerSupportFlags = AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS;
```

1. 있는지 확인 합니다 `InitInstance` 부모를 호출 하는 응용 프로그램의 메서드에 `InitInstance` 메서드: [CWinApp::InitInstance](../mfc/reference/cwinapp-class.md#initinstance) 또는 `CWinAppEx::InitInstance`합니다. `InitInstance` 메서드는 확인 하는 일을 담당 합니다 *m_dwRestartManagerSupportFlags* 매개 변수입니다.

1. 애플리케이션을 컴파일하고 실행합니다.

## <a name="see-also"></a>참고자료

[CDataRecoveryHandler 클래스](../mfc/reference/cdatarecoveryhandler-class.md)<br/>
[CWinApp::m_dwRestartManagerSupportFlags](../mfc/reference/cwinapp-class.md#m_dwrestartmanagersupportflags)<br/>
[CWinApp 클래스](../mfc/reference/cwinapp-class.md)<br/>
[CWinApp::m_nAutosaveInterval](../mfc/reference/cwinapp-class.md#m_nautosaveinterval)<br/>
[CDocument::OnDocumentEvent](../mfc/reference/cdocument-class.md#ondocumentevent)
