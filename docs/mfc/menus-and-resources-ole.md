---
title: 메뉴 및 리소스(OLE)
ms.date: 11/04/2016
helpviewer_keywords:
- OLE visual editing servers [MFC]
- status bars [MFC], OLE document applications
- visual editing [MFC], application menus and resources
- string tables [MFC], visual editing applications
- OLE containers [MFC], menus and resources
- OLE applications [MFC], menus and resources
- OLE server applications [MFC], menus and resources
- toolbars [MFC], OLE document applications
- string editing [MFC], visual editing applications
- server applications [MFC], OLE menus and resources
- applications [OLE], menus and resources
- menus [MFC], OLE document applications
- in-place activation [MFC], OLE menus and resources
- containers [MFC], OLE container applications
- OLE menus and resources [MFC]
ms.assetid: 52bfa086-7d3d-466f-94c7-c7061f3bdb3a
ms.openlocfilehash: 4e8f8c7fa8e24349a741b99822f13d5473373e17
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62225469"
---
# <a name="menus-and-resources-ole"></a>메뉴 및 리소스(OLE)

다음이 문서 메뉴와 MFC OLE 문서 응용 프로그램의 리소스 사용에 설명 합니다.

OLE 비주얼 편집으로 인해 추가 요구 사항 메뉴에 다양 한 모드는 두 컨테이너에 있기 때문에 OLE 문서 응용 프로그램에서 제공 되는 다른 리소스 및 응용 프로그램 서버 (구성 요소)를 시작 하 고 사용할 수 있습니다. 예를 들어, 전체 서버 응용 프로그램을 이러한 세 가지 모드 중 하나에서 실행할 수 있습니다.

- 독립 실행형 합니다.

- 컨테이너의 컨텍스트 내에서 항목을 편집 하는 것에 대 한 준비 합니다.

- 열기, 자주 별도 창에서에서 해당 컨테이너의 컨텍스트 외부에서 항목을 편집 하는 것에 대 한 합니다.

이 응용 프로그램의 각 모드에 대해 하나씩 세 개의 별도 메뉴 레이아웃에 필요합니다. 액셀러레이터 키 테이블은 각 새 모드에 필요한도 합니다. 컨테이너 응용 프로그램을 수 있습니다 또는 내부 활성화를 지원 하지 않을 수합니다 있습니다. 이 경우 새 메뉴 구조 하며 액셀러레이터 키 테이블을 연결 합니다.

내부 활성화는 컨테이너 및 서버 응용 프로그램을 메뉴, 도구 모음 및 상태 표시줄 영역에 대 한 협상 해야 필요 합니다. 모든 리소스에에서이 사용 하 여 디자인 되어야 합니다. 문서 [메뉴 및 리소스: 메뉴 병합](../mfc/menus-and-resources-menu-merging.md) 이 항목에에서 설명 합니다.

이러한 문제 때문에 최대 4 개의 별도 메뉴 및 액셀러레이터 키 테이블 리소스 응용 프로그램 마법사를 사용 하 여 만든 OLE 문서 응용 프로그램이 있을 수 있습니다. 이러한 작업은 다음과 같은 이유로 사용 됩니다.

|리소스 이름|사용|
|-------------------|---------|
|IDR_MAINFRAME|열려 있는 파일에 관계 없이 SDI 응용 프로그램 또는 파일이 열려 있으면 MDI 응용 프로그램에 사용 합니다. 이것이 비 OLE 응용 프로그램에 사용 되는 표준 메뉴입니다.|
|IDR_\<project>TYPE|파일이 열려 있으면 MDI 응용 프로그램에서 사용 합니다. 응용 프로그램은 독립 실행형 실행 중일 때 사용 합니다. 이것이 비 OLE 응용 프로그램에 사용 되는 표준 메뉴입니다.|
|IDR_\<project>TYPE_SRVR_IP|현재 위치에서 개체를 열 때 서버 또는 컨테이너를 사용 합니다.|
|IDR_\<project>TYPE_SRVR_EMB|내부 활성화를 사용 하지 않고 개체를 열 경우 서버 응용 프로그램에 사용 합니다.|

각 이러한 리소스 이름에는 메뉴 및 액셀러레이터 키 테이블 일반적으로 나타냅니다. 응용 프로그램 마법사를 사용 하 여 생성 되지 않은 MFC 응용 프로그램에서와 유사한 체계를 사용 해야 합니다.

다음 문서는 컨테이너, 서버 및 내부 활성화 구현 하는 데 필요한 병합 메뉴와 관련 된 항목을 설명 합니다.

- [메뉴 및 리소스: 컨테이너 추가](../mfc/menus-and-resources-container-additions.md)

- [메뉴 및 리소스: 서버 추가](../mfc/menus-and-resources-server-additions.md)

- [메뉴 및 리소스: 메뉴 병합](../mfc/menus-and-resources-menu-merging.md)

## <a name="see-also"></a>참고자료

[OLE](../mfc/ole-in-mfc.md)
