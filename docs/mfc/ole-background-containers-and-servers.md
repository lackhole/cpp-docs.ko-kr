---
title: 'OLE 백그라운드: 컨테이너 및 서버'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE full-server applications [MFC]
- server applications [MFC], communication with containers
- full-server [MFC]
- server applications [MFC], requirements
- server applications [MFC], defined
- OLE server applications [MFC], about server applications
- server applications [MFC], full-server vs. mini-server
- OLE server applications [MFC], mini-server applications
- OLE containers [MFC], container applications
- containers [MFC], OLE container applications
- server applications [MFC]
ms.assetid: dafbb31d-096c-4654-b774-12900d832919
ms.openlocfilehash: c154562e58cf8f37d77df61556fe25b19ca54c70
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346103"
---
# <a name="ole-background-containers-and-servers"></a>OLE 백그라운드: 컨테이너 및 서버

컨테이너 응용 프로그램은 문서 자체에 포함 되거나 연결 된 항목을 통합할 수 있는 응용 프로그램. 컨테이너 응용 프로그램에 의해 관리 되는 문서를 저장 하 고 응용 프로그램 자체에서 생성 된 데이터 뿐만 아니라 OLE 문서 구성 요소를 표시할 수 있어야 합니다. 컨테이너 응용 프로그램에는 새 항목을 삽입 하거나 필요한 경우 서버 응용 프로그램을 활성화 하 여 기존 항목을 편집 하는 사용자도 허용 해야 합니다. 문서의 컨테이너 응용 프로그램의 사용자 인터페이스 요구 사항 나와 [컨테이너: 사용자 인터페이스 문제](../mfc/containers-user-interface-issues.md)합니다.

서버 응용 프로그램 또는 구성 요소 응용 프로그램에는 컨테이너 응용 프로그램에서 사용 하 여 OLE 문서의 구성 요소를 만들 수 있는 응용 프로그램입니다. 서버 응용 프로그램은 일반적으로 끌어서 놓기 또는 컨테이너 응용 프로그램을 포함 또는 연결 된 항목으로 데이터를 삽입할 수 있도록 해당 데이터를 클립보드에 복사를 지원 합니다. 응용 프로그램 컨테이너와 서버 둘 다를 수 있습니다.

대부분의 서버는 독립 실행형 응용 프로그램 또는 전체 서버; 독립 실행형 응용 프로그램으로 실행할 수 있습니다 하거나 또는 컨테이너 응용 프로그램을 시작할 수 있습니다. 미니 서버에는 컨테이너에 의해서만 시작 될 수 있는 서버 응용 프로그램의 특별 한 형식입니다. 독립 실행형 응용 프로그램으로 실행할 수 없습니다. Microsoft Graph 및 Microsoft 그리기 서버는 미니의 예입니다.

컨테이너 및 서버 직접 통신 하지 않습니다. 대신 OLE 시스템 동적 연결 라이브러리 (DLL)를 통해 통신합니다. 이러한 Dll 컨테이너 및 서버 호출을 하는 함수를 제공 하 고 컨테이너 및 서버 Dll을 호출 하는 콜백 함수를 제공 합니다.

이러한 통신 수단을 사용 하 여, 컨테이너 하지 않아도 서버 응용 프로그램의 구현 세부 정보를 알아야 합니다. 컨테이너를 작동할 수 있는 서버의 형식을 정의 하지 않고 모든 서버에서 만든 항목을 적용할 수 있습니다. 결과적으로, 컨테이너 응용 프로그램의 사용자 미래의 응용 프로그램 및 데이터 형식을 활용을 걸릴 수 있습니다. 이러한 새 응용 프로그램은 OLE 구성 요소를 해당 응용 프로그램에서 만든 항목을 통합할 수으로 복합 문서가 됩니다.

## <a name="see-also"></a>참고자료

[OLE 백그라운드](../mfc/ole-background.md)<br/>
[OLE 백그라운드: MFC 구현](../mfc/ole-background-mfc-implementation.md)<br/>
[컨테이너](../mfc/containers.md)<br/>
[서버](../mfc/servers.md)<br/>
[컨테이너: 클라이언트 항목](../mfc/containers-client-items.md)<br/>
[서버: 서버 항목](../mfc/servers-server-items.md)
