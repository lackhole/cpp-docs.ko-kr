---
title: 클래스를 사용하여 Windows 응용 프로그램 작성
ms.date: 11/04/2016
helpviewer_keywords:
- Windows applications [MFC], MFC application framework
- MFC, application development
- applications [OLE], MFC application framework
- MFC ActiveX controls [MFC], creating
- OLE applications [MFC], MFC application framework
- database applications [MFC], creating
ms.assetid: 73f63470-857d-43dd-9a54-b38b7be0f1b7
ms.openlocfilehash: c8b3d7061c0ef06063d9c6993f24d23fc2e1f92e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411476"
---
# <a name="using-the-classes-to-write-applications-for-windows"></a>클래스를 사용하여 Windows 응용 프로그램 작성

Microsoft Foundation 클래스 (MFC) 라이브러리의 클래스를 전체적으로 볼 때, "응용 프로그램 프레임 워크," Windows 운영 체제에 대 한 응용 프로그램을 빌드하면 구성 합니다. 매우 일반적인 수준에서 프레임 워크는 응용 프로그램의 기본 구조를 정의 하 고 구조를 지정할 수 있는 표준 사용자 인터페이스를 구현을 제공 합니다. 프로그래머로 서 작업은 나머지 구조를 작성 하는 응용 프로그램에 관련 된 것입니다. 먼저 매우 자세 시작 응용 프로그램 파일을 만들려면 MFC 응용 프로그램 마법사를 사용 하 여 가져올 수 있습니다. Microsoft Visual을 사용 하 여 C++ 코드 및 응용 프로그램별 논리를 구현 하는 클래스 라이브러리에 해당 요소를 연결할 명령 클래스 뷰 사용자 인터페이스 요소를 시각적으로 디자인 하려면 리소스 편집기입니다.

버전 3.0 이상 MFC 프레임 워크에는 Win32 플랫폼을 비롯 하 여 Microsoft Windows 95 및 나중에 대 한 프로그래밍 및 Windows NT 버전 3.51 이상 지원합니다. 다중 스레드 MFC Win32 지원이 포함 되어 있습니다. 사용 하 여 버전 1.5*x* 16 비트 프로그래밍을 수행 해야 할 경우.

문서이에서는 응용 프로그램 프레임 워크의 개요를 제공합니다. 또한 응용 프로그램 및를 만드는 방법을 구성 하는 주요 개체를 탐색 합니다. 이 문서에서 다루는 항목은 다음과 같습니다.

- [프레임 워크](../mfc/framework-mfc.md)합니다.

- 프레임 워크 및 코드에 설명 된 대로 간의 분업 [프레임 워크를 토대로](../mfc/building-on-the-framework.md)합니다.

- [응용 프로그램 클래스](../mfc/cwinapp-the-application-class.md)를 캡슐화 하는 응용 프로그램 수준 기능입니다.

- 어떻게 [문서 템플릿](../mfc/document-templates-and-the-document-view-creation-process.md) 만들기 문서와 연결 된 뷰를 관리 하 고 windows 프레임입니다.

- 클래스 [CWnd](../mfc/window-objects.md), 모든 창의 루트 기본 클래스입니다.

- [그래픽 개체](../mfc/graphic-objects.md), 펜 및 브러시와 같은 합니다.

프레임 워크의 다른 부분에는 다음이 포함 됩니다.

- [창 개체: 개요](../mfc/window-objects.md)

- [메시지 처리 및 매핑](../mfc/message-handling-and-mapping.md)

- [CObject, MFC의 기본 루트 클래스](../mfc/using-cobject.md)

- [문서/뷰 아키텍처](../mfc/document-view-architecture.md)

- [대화 상자](../mfc/dialog-boxes.md)

- [컨트롤](../mfc/controls-mfc.md)

- [컨트롤 막대](../mfc/control-bars.md)

- [OLE](../mfc/ole-in-mfc.md)

- [메모리 관리](../mfc/memory-management.md)

   Windows 운영 체제에 대 한 응용 프로그램 작성이 점으로 손꼽을 수 있도록 하는 것 외에도 MFC 하기가 특히 연결 및 기술을 포함 하는 OLE를 사용 하는 응용 프로그램을 작성 하기가 훨씬 쉽습니다. 가능 응용 프로그램 OLE 비주얼 편집 컨테이너, OLE 비주얼 편집 서버, 또는 둘 다 및 다른 응용 프로그램 응용 프로그램에서 개체를 사용 하거나 원격으로 수 있도록 자동화를 추가할 수 있습니다.

- [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)

   OLE 컨트롤 개발 키트 (CDK) 프레임 워크를 사용 하 여 완전히 통합 되었습니다. 이 문서에서는 MFC로 ActiveX 컨트롤 개발의 개요를 제공합니다. (ActiveX 컨트롤 된 이전의 OLE 컨트롤입니다.)

- [데이터베이스 프로그래밍](../data/data-access-programming-mfc-atl.md)

   MFC는 또한 쓰기 데이터 액세스를 간소화 하는 database 클래스의 두 집합 제공 응용 프로그램입니다. ODBC 데이터베이스 클래스를 사용 하는 데이터베이스 연결 ODBC (Open) 드라이버를 통해 데이터베이스 연결, 테이블의 레코드를 선택 하 고 표시할 수에서 정보를 기록는 화면의 폼입니다. 데이터 액세스 개체 (DAO) 클래스를 사용 하 여, Microsoft Jet 데이터베이스 엔진 또는 외부 (비 Jet) 데이터 원본, ODBC 데이터 원본을 포함 하 여을 통해 데이터베이스를 사용 하 여 작업할 수 있습니다.

   또한 MFC가 완전히 유니코드를 사용 하는 응용 프로그램을 작성 하는 것에 대 한 설정 및 멀티 바이트 문자 집합 (MBCS), 특히 더블 바이트 문자 집합 (DBCS).

MFC 설명서에 대 한 일반 지침을 참조 하세요 [일반 MFC 항목](../mfc/general-mfc-topics.md)합니다.

## <a name="see-also"></a>참고자료

[일반 MFC 항목](../mfc/general-mfc-topics.md)
