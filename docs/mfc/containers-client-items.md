---
title: '컨테이너: 클라이언트 항목'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE containers [MFC], client items
- client items and OLE containers
ms.assetid: 231528b5-0744-4f83-8897-083bf55ed087
ms.openlocfilehash: 0c7f4a63cb9a31b52be2d3574ddad29313df6a4d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62153361"
---
# <a name="containers-client-items"></a>컨테이너: 클라이언트 항목

이 문서에서는 클라이언트 항목 및 클래스가에서 응용 프로그램에 해당 클라이언트 항목이 파생 되어야 합니다.

클라이언트 항목 중 하나에 포함 되어 있거나 OLE 컨테이너 응용 프로그램의 문서에서 참조 하는 다른 응용 프로그램에 속하는 데이터 항목은입니다. 문서 내에서 해당 데이터는 포함 하는 클라이언트 항목 포함 됩니다. 데이터는 컨테이너 문서에서 참조 하는 다른 위치에 저장 된 연결 됩니다.

OLE 응용 프로그램에서 문서 클래스는 클래스에서 파생 된 [COleDocument](../mfc/reference/coledocument-class.md) 아닌 `CDocument`합니다. 합니다 `COleDocument` 클래스에서 상속 `CDocument` 는 MFC 응용 프로그램 기반 문서/뷰 아키텍처를 사용 하는 데 필요한 모든 기능입니다. `COleDocument` 또한 문서 컬렉션으로 처리 하는 인터페이스를 정의 `CDocItem` 개체입니다. 여러 `COleDocument` 추가, 검색 및 해당 컬렉션의 요소를 삭제 하는 것에 대 한 멤버 함수가 제공 됩니다.

모든 컨테이너 응용 프로그램에서 하나 이상의 클래스를 파생 해야 `COleClientItem`합니다. 이 클래스의 개체 포함 되거나 OLE 문서에 연결 된 항목을 나타냅니다. 문서에서 삭제 되지 않는 이러한 개체를 포함 하는 문서의 수명 동안 존재 합니다.

`CDocItem` 에 대 한 기본 클래스인 `COleClientItem` 고 `COleServerItem`입니다. 이러한 두에서 파생 된 클래스의 개체는 각각 OLE 항목 및 클라이언트와 서버 응용 프로그램 간의 중개자 역할입니다. 새 OLE 항목을 문서에 추가 될 때마다 MFC 프레임 워크의 클라이언트 응용 프로그램의 새 개체를 추가 합니다 `COleClientItem`-파생 클래스의 문서 컬렉션 `CDocItem` 개체입니다.

## <a name="see-also"></a>참고자료

[컨테이너](../mfc/containers.md)<br/>
[컨테이너: 복합 파일](../mfc/containers-compound-files.md)<br/>
[컨테이너: 사용자 인터페이스 문제](../mfc/containers-user-interface-issues.md)<br/>
[컨테이너: 고급 기능](../mfc/containers-advanced-features.md)<br/>
[COleClientItem 클래스](../mfc/reference/coleclientitem-class.md)<br/>
[COleServerItem 클래스](../mfc/reference/coleserveritem-class.md)
