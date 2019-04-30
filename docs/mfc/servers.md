---
title: 서버
ms.date: 11/04/2016
helpviewer_keywords:
- OLE server applications [MFC]
- OLE server applications [MFC], activation
- full-server
- servers
- mini-server
- OLE server applications [MFC], server types
- server applications [MFC]
ms.assetid: e45172e8-eae3-400a-8139-0fa009a42fdc
ms.openlocfilehash: 7b1eb0df439bcfde3aa295f23a90291e865df3a9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307837"
---
# <a name="servers"></a>서버

서버 응용 프로그램 (또는 구성 요소 응용 프로그램) 컨테이너 응용 프로그램에서 사용 하기 위해 OLE 항목 (또는 구성 요소)을 만듭니다. 비주얼 편집 서버 응용 프로그램 비주얼 편집 또는 내부 활성화에도 지원합니다. 다른 형태의 OLE 서버는 [자동화 서버](../mfc/automation-servers.md)합니다. 일부 서버 응용 프로그램을 만들 때에 포함 된 항목에 대 한 지원 다른 포함 및 연결 된 항목의 생성을 지원 합니다. 일부 지원 링크에이 드물지만 합니다. 사용자가 항목을 편집 하려고 할 때 모든 서버 응용 프로그램 컨테이너 응용 프로그램에서 활성화를 지원 해야 합니다. 응용 프로그램 컨테이너와 서버 둘 다를 수 있습니다. 즉, 수 모두 해당 문서에 데이터를 통합 하 고 다른 응용 프로그램의 문서에 항목으로 통합할 수 있는 데이터를 만듭니다.

미니 서버에는 컨테이너에서 시작 될 수 있는 서버 응용 프로그램의 특별 한 형식입니다. Microsoft 그리기 및 Microsoft Graph은 미니의 예입니다. 미니 서버 디스크에서 파일로 문서를 저장 하지 않습니다. 대신, 해당 문서를 읽고 문서의 컨테이너에 속하는 항목에에서 기록 합니다. 결과적으로, 미니 서버 지원만 포함 연결 되지 않습니다.

전체 서버는 독립 실행형 응용 프로그램으로 실행 하거나 또는 컨테이너 응용 프로그램을 시작할 수 있습니다. 전체 서버 디스크에서 파일로 문서를 저장할 수 있습니다. 모두 포함만 포함 하 고 연결 하거나만 연결 지원할 수 있습니다. 컨테이너 응용 프로그램의 사용자는 서버 및 컨테이너에 붙여넣기 명령을 잘라내기 또는 복사 명령을 선택 하 여 포함 된 항목을 만들 수 있습니다. 연결 된 항목을 컨테이너에서 서버에 복사 명령과 연결 하 여 붙여넣기 명령을 선택 하 여 만들어집니다. 또는 사용자 개체 삽입 대화 상자를 사용 하 여 포함 또는 연결 된 항목을 만들 수 있습니다.

다음 표에서 다양 한 서버 유형의 특성을 보여 줍니다.

### <a name="server-characteristics"></a>서버 특성

|서버 유형|여러 인스턴스를 지원|문서 항목|문서 / 인스턴스|
|--------------------|---------------------------------|------------------------|----------------------------|
|미니 서버|예|1|1|
|SDI 전체 서버|예|1 (연결 지원 되는 경우 하나 이상의)|1|
|MDI 전체 서버|아니요 (필요 없음)|1 (연결 지원 되는 경우 하나 이상의)|0 개 이상|

서버 응용 프로그램에서 하나 이상의 컨테이너가 포함 되거나 연결 된 항목을 편집 하는 동시에 여러 컨테이너를 지원 해야 합니다. SDI 응용 프로그램 (또는 대화 상자 인터페이스를 사용 하 여 미니 서버) 서버 이면 서버의 여러 인스턴스에 동시에 실행할 수 있어야 합니다. 이렇게 하면 각 컨테이너 요청을 처리 하도록 응용 프로그램의 개별 인스턴스.

서버는 MDI 응용 프로그램인 경우 컨테이너 항목을 편집 해야 할 때마다 새 MDI 자식 창을 만들 있습니다. 이러한 방식으로 응용 프로그램의 단일 인스턴스를 여러 컨테이너를 지원할 수 있습니다.

서버 응용 프로그램에 알려야 OLE 시스템 Dll을 한 서버 인스턴스의 다른 컨테이너 서비스를 요청 하는 경우 이미 실행 중인 경우 수행할 작업: 서버의 새 인스턴스를 시작 하 또는 모든 컨테이너의 요청을 직접 인스턴스를 서버입니다.

서버에 대 한 자세한 내용은 다음을 참조 하세요.

- [서버: 서버 구현](../mfc/servers-implementing-a-server.md)

- [서버: 서버 문서 구현](../mfc/servers-implementing-server-documents.md)

- [서버: 내부 프레임 창 구현](../mfc/servers-implementing-in-place-frame-windows.md)

- [서버: 서버 항목](../mfc/servers-server-items.md)

- [서버: 사용자 인터페이스 문제](../mfc/servers-user-interface-issues.md)

## <a name="see-also"></a>참고자료

[OLE](../mfc/ole-in-mfc.md)<br/>
[컨테이너](../mfc/containers.md)<br/>
[컨테이너: 고급 기능](../mfc/containers-advanced-features.md)<br/>
[메뉴 및 리소스(OLE)](../mfc/menus-and-resources-ole.md)<br/>
[등록](../mfc/registration.md)<br/>
[자동화 서버](../mfc/automation-servers.md)
