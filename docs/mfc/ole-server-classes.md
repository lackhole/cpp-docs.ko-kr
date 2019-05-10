---
title: OLE 서버 클래스
ms.date: 11/04/2016
f1_keywords:
- vc.classes.ole
helpviewer_keywords:
- OLE server applications [MFC], server classes
- OLE server documents
- COM components, classes [MFC]
- component classes [MFC]
ms.assetid: 8e9b67a2-c0ff-479c-a8d6-19b36c5e6fc6
ms.openlocfilehash: 99dd7f58b862fadc86ee2515bb8ef2008bc538fa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385325"
---
# <a name="ole-server-classes"></a>OLE 서버 클래스

이러한 클래스는 서버 응용 프로그램에서 사용 됩니다. 서버 문서에서 파생 됩니다 `COleServerDoc` 아닌 `CDocument`합니다. 되므로 `COleServerDoc` 에서 파생 된 `COleLinkingDoc`, 서버 문서 링크를 지 원하는 컨테이너를 수도 있습니다.

`COleServerItem` 문서나 다른 문서에 포함 하거나 연결할 수 있는 문서의 부분 클래스를 나타냅니다.

`COleIPFrameWnd` 및 `COleResizeBar` 컨테이너의 개체는 내부 편집을 지원 하 고 `COleTemplateServer` 다른 응용 프로그램에서 OLE 개체를 편집할 수 있도록 문서/뷰 쌍 만들기를 지원 합니다.

[COleServerDoc](../mfc/reference/coleserverdoc-class.md)<br/>
응용 프로그램 서버 문서 클래스에 대 한 기본 클래스로 사용 합니다. `COleServerDoc` 개체와 상호 작용을 통해 server 지원의 제공 `COleServerItem` 개체입니다. 비주얼 편집 기능은 클래스 라이브러리의 문서/뷰 아키텍처를 사용 하 여 제공 됩니다.

[CDocItem](../mfc/reference/cdocitem-class.md)<br/>
기본 클래스의 추상 `COleClientItem` 고 `COleServerItem`입니다. 파생 된 클래스의 개체 `CDocItem` 문서 부분을 나타냅니다.

[COleServerItem](../mfc/reference/coleserveritem-class.md)<br/>
OLE 인터페이스를 나타내는 데 `COleServerDoc` 항목입니다. 일반적으로 하나씩 있기 `COleServerDoc` 문서의 포함 된 부분을 나타내는 개체입니다. 문서의 일부에 대 한 링크를 지 원하는 서버에 있을 수 있습니다 여러 `COleServerItem` 각각 링크 문서의 부분을 나타내는 개체입니다.

[클래스에서 파생하는 대신](../mfc/reference/coleipframewnd-class.md)<br/>
준비에서 서버 문서를 편집 하는 경우 프레임 창 보기를 제공 합니다.

[COleResizeBar](../mfc/reference/coleresizebar-class.md)<br/>
전체 크기를 조정 하는 표준 사용자 인터페이스를 제공합니다. 이 클래스의 개체와 함께에서 항상 사용 됩니다 `COleIPFrameWnd` 개체입니다.

[COleTemplateServer](../mfc/reference/coletemplateserver-class.md)<br/>
프레임 워크의 문서/뷰 아키텍처를 사용 하 여 문서를 작성 하는 데 사용 합니다. A `COleTemplateServer` 대부분의 작업을 연결 된 개체에 위임 `CDocTemplate` 개체입니다.

[COleException](../mfc/reference/coleexception-class.md)<br/>
OLE 처리 중 오류로 인해 발생하는 예외입니다. 이 클래스는 컨테이너 및 서버에서 모두 사용됩니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../mfc/class-library-overview.md)
