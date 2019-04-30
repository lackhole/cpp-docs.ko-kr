---
title: 등록
ms.date: 11/04/2016
helpviewer_keywords:
- servers [MFC], initializing
- initializing servers [MFC]
- OLE, registration
- installing servers [MFC]
- registry [MFC], OLE item database
- registration databases [MFC]
- servers [MFC], installing
- OLE server applications [MFC], registering servers
ms.assetid: 991d5684-72c1-4f9e-a09a-9184ed12bbb9
ms.openlocfilehash: 0bc606acfba26d27d0ab36045e4772593e760e98
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62309100"
---
# <a name="registration"></a>등록

사용자가 응용 프로그램에 OLE 항목을 삽입 하려고 하는 경우 OLE에서 선택할 수 있는 개체 유형 목록을 표시 합니다. OLE 모든 서버 응용 프로그램에서 제공 되는 정보를 포함 하는 시스템 등록 데이터베이스에서이 목록을 가져옵니다. 서버 자체를 등록 하는 경우 시스템 등록 데이터베이스 (레지스트리)에 배치 하는 항목을 제공 하는 개체의 각 유형 설명, 파일 확장명 및 기타 정보 중에서 자체에 대 한 경로.

프레임 워크 및 OLE 시스템 동적 연결 라이브러리 (DLL) 시스템에서 사용할 수 있는 OLE 항목의 형식을 결정 하려면이 레지스트리를 사용 합니다. OLE 시스템 Dll도이 레지스트리 사용 하 여이 연결 되거나 포함 된 개체가 활성화 될 때 서버 응용 프로그램을 시작 하는 방법을 결정 합니다.

이 문서에서는 설치 될 때 수행 해야 하는 각 서버 응용 프로그램을 설명 하 고 실행 됩니다 될 때마다 키를 누릅니다.

시스템 등록 데이터베이스 및 업데이트 하는 데.reg 파일 형식에 대 한 자세한 내용은 참조는 *참조 OLE Programmer's Reference*합니다.

##  <a name="_core_server_installation"></a> 서버 설치

서버 응용 프로그램을 처음 설치할 때 지원 되는 OLE 항목의 모든 형식을 등록 해야 합니다. 독립 실행형 응용 프로그램으로 실행 될 때마다 시스템 등록 데이터베이스를 업데이트 하는 서버를 할 수도 있습니다. 이렇게 하면 등록 데이터베이스 최신 서버 실행 파일을 이동 하는 경우.

> [!NOTE]
>  응용 프로그램 마법사가 자동으로 생성 하는 MFC 응용 프로그램은 독립 실행형 응용 프로그램으로 실행 될 때 자신을 등록 합니다.

를 설치 하는 동안 응용 프로그램을 등록 하려면 RegEdit.exe 프로그램을 사용 합니다. 응용 프로그램을 사용 하 여 설치 프로그램을 포함 하는 경우 설치 프로그램 실행에 있는 "RegEdit /S *appname*.reg"입니다. (/S 플래그 자동 작업을 나타냅니다. 즉, 명령의 완료를 알리는 대화 상자를 표시 하지 않습니다.) 이 고, 그렇지 RegEdit를 수동으로 실행 하도록을 지시 합니다.

> [!NOTE]
>  응용 프로그램 마법사로 만든.reg 파일 실행 파일에 대 한 전체 경로 포함 되지 않습니다. 설치 프로그램 실행 파일에 전체 경로 포함 하거나 설치 디렉터리를 포함 하도록 PATH 환경 변수를 수정 하려면.reg 파일을 수정 하거나 해야 합니다.

RegEdit 등록 데이터베이스에.reg 텍스트 파일의 내용을 병합합니다. 데이터베이스를 확인 또는 복구 하려면 레지스트리 편집기를 사용 합니다. 필수 OLE 항목을 삭제 하지 않도록 주의 해야 합니다.

##  <a name="_core_server_initialization"></a> 서버 초기화

응용 프로그램 마법사를 사용 하 여 서버 응용 프로그램을 만들 때 마법사 모든 작업을 완료할 초기화를 자동으로 합니다. 이 섹션에서는 수행 해야 수동으로 서버 응용 프로그램을 작성 하는 경우를 설명 합니다.

서버 응용 프로그램 컨테이너 응용 프로그램에 의해 시작 되 면 OLE 시스템 Dll 서버의 명령줄에 "/ 포함" 옵션을 추가 합니다. 서버 응용 프로그램의 동작에 따라 여부 시작한 컨테이너에서 응용 프로그램 실행을 시작 하는 경우 수행 해야 할 것을 확인 하므로 달라는 "/ 포함" 또는 "-포함" 명령줄 옵션입니다. 이 스위치가 있으면 다른 어느 곳에서 활성으로 서버를 표시 하는 리소스 집합을 로드 또는 완전히 엽니다. 자세한 내용은 참조 하세요. [메뉴 및 리소스: 서버 추가](../mfc/menus-and-resources-server-additions.md)합니다.

서버 응용 프로그램을 호출 해야 해당 `CWinApp::RunEmbedded` 명령줄을 구문 분석 하는 함수입니다. 0이 아닌 값을 반환 하는 경우 독립 실행형 응용 프로그램 아니라 컨테이너 응용 프로그램에서 실행 되므로 응용 프로그램의 창을 표시 되지 않아야 합니다. 이 함수 호출 시스템 등록 데이터베이스에 서버 항목을 업데이트 합니다 `RegisterAll` 멤버 함수 인스턴스 등록을 수행 합니다.

서버 응용 프로그램을 시작할 때 인스턴스 등록을 수행할 수 있는지 확인 해야 합니다. 인스턴스 등록 서버는 활성 및 컨테이너에서 요청을 받을 준비가 OLE 시스템 Dll에 알립니다. 등록 데이터베이스에 항목을 추가 하지 않습니다. 호출 하 여 서버 인스턴스 등록을 수행 합니다 `ConnectTemplate` 멤버 함수를 정의한 `COleTemplateServer`합니다. 이 연결 된 `CDocTemplate` 개체는 `COleTemplateServer` 개체.

`ConnectTemplate` 함수는 세 개의 매개 변수: 서버의 *CLSID*에 대 한 포인터를 `CDocTemplate` 개체 및 서버의 여러 인스턴스를 지원 하는지 여부를 나타내는 플래그입니다. 미니 서버는 여러 인스턴스를 지원할 수 있어야 합니다., 즉, 각 컨테이너에 대 한 동시에 실행 서버의 여러 인스턴스에 대 한 가능한 여야 합니다. 따라서 전달 **TRUE** 미니 서버를 시작할 때이 플래그에 대 한 합니다.

미니 서버를 작성 하는 경우 정의 의해 항상 시작 됩니다 컨테이너에서. 여전히 "/ 포함" 옵션을 확인 하려면 명령줄을 구문 분석 해야 있습니다. 명령줄에이 옵션이 없으면 사용자가 독립 실행형 응용 프로그램으로 미니 서버를 시작 하려고 했음을 의미 합니다. 이 경우 시스템 등록 데이터베이스를 사용 하 여 서버를 등록 하 고 응용 프로그램을 컨테이너에서 미니 서버를 시작 하려면 사용자에 게 알리는 메시지 상자를 표시 합니다.

## <a name="see-also"></a>참고자료

[OLE](../mfc/ole-in-mfc.md)<br/>
[서버](../mfc/servers.md)<br/>
[CWinApp::RunAutomated](../mfc/reference/cwinapp-class.md#runautomated)<br/>
[CWinApp::RunEmbedded](../mfc/reference/cwinapp-class.md#runembedded)<br/>
[COleTemplateServer 클래스](../mfc/reference/coletemplateserver-class.md)
