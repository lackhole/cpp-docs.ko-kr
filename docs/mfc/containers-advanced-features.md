---
title: '컨테이너: 고급 기능'
ms.date: 11/04/2016
helpviewer_keywords:
- links [MFC], to embedded OLE objects
- containers [MFC], links to embedded OLE objects
- containers [MFC], advanced features
- container/server applications [MFC]
- embedded objects [MFC]
- OLE controls [MFC], containers
- OLE containers [MFC], advanced features
- server/container applications [MFC]
- containers [MFC], container applications
ms.assetid: 221fd99c-b138-40fa-ad6a-974e3b3ad1f8
ms.openlocfilehash: 350431975a4335fc06e436237b7e0d3388faab64
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152932"
---
# <a name="containers-advanced-features"></a>컨테이너: 고급 기능

이 문서에서는 기존 컨테이너 응용 프로그램에 선택적 고급 기능을 통합 하는 데 필요한 단계를 설명 합니다. 이러한 기능은 다음과 같습니다.

- [컨테이너와 서버 응용 프로그램](#_core_creating_a_container_server_application)

- [포함된 된 개체에 대 한 OLE 링크](#_core_links_to_embedded_objects)

##  <a name="_core_creating_a_container_server_application"></a> 컨테이너/서버 응용 프로그램 만들기

컨테이너/서버 응용 프로그램은 컨테이너 및 서버를 모두 사용 되는 응용 프로그램. Windows 용 Microsoft Word는이 예시입니다. 다른 응용 프로그램의 Windows에 대 한 Word 문서를 포함할 수 있습니다 하 고 Windows에 대 한 Word 문서에서 항목을 포함할 수도 있습니다. 컨테이너 응용 프로그램에 컨테이너와 전체 서버 (조합 컨테이너/미니 서버 응용 프로그램을 만들 수 없습니다)를 수정 하기 위한 프로세스는 전체 서버를 만드는 프로세스와 비슷합니다.

문서 [서버: 서버 구현](../mfc/servers-implementing-a-server.md) 서버 응용 프로그램을 구현 하는 데 필요한 작업의 수를 나열 합니다. 컨테이너/서버 응용 프로그램에 컨테이너 응용 프로그램으로 변환 하면 다음 수행 해야 이러한 동일한 작업의 일부 코드 컨테이너를 추가 합니다. 다음은 고려해 야 할 중요 한 사항에 대 한 목록입니다.

- 이미 응용 프로그램 마법사에서 만든 컨테이너 코드 OLE 하위 시스템을 초기화 합니다. 지원 하기 위해 아무 것도 추가 하거나 변경 하려면 않아도 됩니다.

- 문서 클래스의 기본 클래스는 아무 곳에 나 `COleDocument`, 기본 클래스를 변경 `COleServerDoc`합니다.

- 재정의 `COleClientItem::CanActivate` 자리에서 편집 하는 서버 자체를 사용 하는 동안 현재 위치에서 항목을 편집 하지 않아도 됩니다.

   예를 들어, MFC OLE 샘플 [OCLIENT](../overview/visual-cpp-samples.md) 더 컨테이너/서버 응용 프로그램에서 만든 항목을 포함 합니다. OCLIENT 응용 프로그램을 열면 및 전체 컨테이너/서버 응용 프로그램에서 만든 항목을 편집 합니다. MFC OLE 샘플에서 만든 항목을 포함 하려는 하려는 응용 프로그램의 항목을 편집 하는 동안 [HIERSVR](../overview/visual-cpp-samples.md)합니다. 이 위해 내부 활성화를 사용할 수 없습니다. 이 항목을 활성화 하는 HIERSVR 완전히 열어야 합니다. Microsoft Foundation Class 라이브러리는이 OLE 기능을 지원 하지 않으므로, 재정의 `COleClientItem::CanActivate` 이 이런 확인 하 고 응용 프로그램에서 가능한 런타임 오류를 방지할 수 있습니다.

새 응용 프로그램을 만드는 경우 컨테이너/서버 응용 프로그램으로 작동 시키려면 응용 프로그램 마법사에서이 지원은 OLE 옵션 대화 상자에서 옵션 자동으로 만들 수는 선택 합니다. 자세한 내용은 문서를 참조 하세요. [개요: ActiveX 컨트롤 컨테이너 만들기](../mfc/reference/creating-an-mfc-activex-control-container.md)합니다. MFC 샘플에 대 한 내용은 MFC 샘플을 참조 하세요.

참고 MDI 응용 프로그램 자체에 삽입할 수 있습니다. SDI 응용 프로그램 아닌 컨테이너/서버 응용 프로그램 자체에 삽입할 수 없습니다.

##  <a name="_core_links_to_embedded_objects"></a> 포함 된 개체에 대 한 링크

포함 된 개체 기능에 대 한 연결 사용자를 문서 컨테이너 응용 프로그램 내에서 포함된 된 개체에 대 한 OLE 링크를 사용 하 여 만들 수 있습니다. 예를 들어 포함 된 스프레드시트를 포함 하는 워드 프로세서에서 문서를 만듭니다. 응용 프로그램에 포함 된 개체에 대 한 링크를 지 원하는 경우는 워드 프로세서 문서에 포함 된 스프레드시트에 대 한 링크를 붙여넣을 수 있습니다. 이 기능은 여기서 워드 프로세서 원래 하셨나요 알지 못해도 스프레드시트에 포함 된 정보를 사용 하도록 응용 프로그램입니다.

#### <a name="to-link-to-embedded-objects-in-your-application"></a>응용 프로그램에 포함 된 개체에 연결 하려면

1. 문서 클래스 파생 `COleLinkingDoc` 대신 `COleDocument`합니다.

1. OLE 클래스 ID를 만듭니다 (**CLSID**) OLE 개발 도구에 포함 된 클래스 ID 생성기를 사용 하 여 응용 프로그램에 대 한 합니다.

1. OLE를 사용 하 여 응용 프로그램을 등록 합니다.

1. 만들기는 `COleTemplateServer` 응용 프로그램 클래스의 멤버인 개체입니다.

1. 응용 프로그램 클래스의 `InitInstance` 멤버 함수에 다음을 수행 합니다.

   - 연결 프로그램 `COleTemplateServer` 개체를 호출 하 여 문서 템플릿 개체 `ConnectTemplate` 멤버 함수입니다.

   - 호출 된 `COleTemplateServer::RegisterAll` OLE 시스템을 사용 하 여 모든 클래스 개체를 등록 하는 멤버 함수입니다.

   - `COleTemplateServer::UpdateRegistry`를 호출합니다. 유일한 매개 변수를 `UpdateRegistry` 있어야 *OAT_CONTAINER* 경우 응용 프로그램 "/ 포함 된" 스위치를 사용 하 여 시작 되지 않습니다. 이 포함 된 개체에 대 한 링크를 지원할 수 있는 컨테이너로 응용 프로그램을 등록 합니다.

         If the application is launched with the "/Embedded" switch, it should not show its main window, similar to a server application.

MFC OLE 샘플 [OCLIENT](../overview/visual-cpp-samples.md) 이 기능을 구현 합니다. 이렇게 하는 방법의 예제를 참조 하세요. 합니다 `InitInstance` 함수는 *OCLIENT 합니다. CPP* 이 샘플 응용 프로그램의 파일입니다.

## <a name="see-also"></a>참고자료

[컨테이너](../mfc/containers.md)<br/>
[서버](../mfc/servers.md)
