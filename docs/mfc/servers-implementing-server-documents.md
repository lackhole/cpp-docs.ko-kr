---
title: '서버: 서버 문서 구현'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE server applications [MFC], managing server documents
- OLE server applications [MFC], implementing OLE servers
- servers, server documents
- server documents [MFC], implementing
ms.assetid: cca1451a-ad09-47ed-b56e-bccd78fc86d1
ms.openlocfilehash: 17ced1cdb0b40b13fbda68150030efde5735ba7b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307915"
---
# <a name="servers-implementing-server-documents"></a>서버: 서버 문서 구현

이 문서에서는 응용 프로그램 마법사에서 OLE 서버 옵션을 지정 하지 않은 경우 서버 문서를 성공적으로 구현 하기 위해 취해야 하는 단계를 설명 합니다.

#### <a name="to-define-a-server-document-class"></a>서버 문서 클래스를 정의 하려면

1. 문서 클래스 파생 `COleServerDoc` 대신 `CDocument`합니다.

1. 파생 된 서버 항목 클래스 만들기 `COleServerItem`합니다.

1. 구현 된 `OnGetEmbeddedItem` 서버 문서 클래스의 멤버 함수입니다.

   `OnGetEmbeddedItem` 컨테이너 응용 프로그램의 사용자가 만들거나 포함 된 항목을 편집할 때 호출 됩니다. 전체 문서를 나타내는 항목을 반환 합니다. 개체 이어야 합니다 하 `COleServerItem`-클래스를 파생 합니다.

1. 재정의 `Serialize` 문서의 내용을 serialize 할 멤버 함수입니다. 사용 하지 않으면 해당 데이터를 나타내는 기본 문서에서 server 항목 목록을 serialize 할 필요가 없습니다. 자세한 내용은 *서버 항목 구현* 문서의 [서버: 서버 항목](../mfc/servers-server-items.md)합니다.

서버 문서를 만든 경우 프레임 워크 OLE 시스템 Dll 사용 하 여 문서를 자동으로 등록 합니다. 따라서 서버 문서를 식별 하는 Dll입니다.

자세한 내용은 참조 하세요. [COleServerItem](../mfc/reference/coleserveritem-class.md) 하 고 [COleServerDoc](../mfc/reference/coleserverdoc-class.md) 에 *클래스 라이브러리 참조*합니다.

## <a name="see-also"></a>참고자료

[서버](../mfc/servers.md)<br/>
[서버: 서버 항목](../mfc/servers-server-items.md)<br/>
[서버: 서버 구현](../mfc/servers-implementing-a-server.md)<br/>
[서버: 내부 프레임 창 구현](../mfc/servers-implementing-in-place-frame-windows.md)
