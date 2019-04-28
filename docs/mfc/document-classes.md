---
title: 문서 클래스
ms.date: 11/04/2016
f1_keywords:
- vc.classes.document
helpviewer_keywords:
- document classes [MFC]
ms.assetid: 4bf19b02-0a4f-4319-b68e-cddcba2705cb
ms.openlocfilehash: a7034a99bfefe8f4c11cdf8f99dc4b0c31fac10a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62219797"
---
# <a name="document-classes"></a>문서 클래스

문서 클래스 개체, 문서 템플릿 개체를 만들어 응용 프로그램의 데이터를 관리 합니다. 이러한 클래스 중 하나에서 문서에 대 한 클래스를 파생 됩니다.

문서 클래스 개체가 뷰 개체를 사용 하 여 상호 작용 합니다. 뷰 개체 창의 클라이언트 영역을 나타내는 문서의 데이터를 표시 하며 사용자가 상호 작용할 수 있도록 합니다. 문서 및 뷰는 문서 템플릿 개체에 의해 생성 됩니다.

[CDocument](../mfc/reference/cdocument-class.md)<br/>
응용 프로그램 관련 문서에 대 한 기본 클래스입니다. 문서 클래스 또는 클래스에서 파생 `CDocument`합니다.

[COleDocument](../mfc/reference/coledocument-class.md)<br/>
기본 컨테이너 지원 뿐만 아니라 복합 문서 구현을 사용 합니다. 파생 된 클래스에 대 한 컨테이너 역할 [CDocItem](../mfc/reference/cdocitem-class.md)합니다. 컨테이너 문서에 대 한 기본 클래스에 대 한 기본 클래스로이 클래스를 사용할 수 있습니다 `COleServerDoc`합니다.

[COleLinkingDoc](../mfc/reference/colelinkingdoc-class.md)<br/>
파생 된 클래스 `COleDocument` 연결에 대 한 인프라를 제공 하는 합니다. 대신이 클래스에서 컨테이너 응용 프로그램에 대 한 문서 클래스를 파생 해야 `COleDocument` 포함 된 개체에 대 한 링크를 지원 하도록 하려는 경우.

[CRichEditDoc](../mfc/reference/cricheditdoc-class.md)<br/>
Rich edit 컨트롤에 있는 OLE 클라이언트 항목 목록을 유지 관리 합니다. 사용한 [CRichEditView](../mfc/reference/cricheditview-class.md) 하 고 [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)합니다.

[COleServerDoc](../mfc/reference/coleserverdoc-class.md)<br/>
응용 프로그램 서버 문서 클래스에 대 한 기본 클래스로 사용 합니다. `COleServerDoc` 개체와 상호 작용을 통해 server 지원의 제공 [COleServerItem](../mfc/reference/coleserveritem-class.md) 개체입니다. 비주얼 편집 기능은 클래스 라이브러리의 문서/뷰 아키텍처를 사용 하 여 제공 됩니다.

[CHtmlEditDoc](../mfc/reference/chtmleditdoc-class.md)<br/>
에서 제공 된 [CHtmlEditView](../mfc/reference/chtmleditview-class.md), MFC 문서 뷰 아키텍처 컨텍스트 내에서 HTML WebBrowser 편집 플랫폼의 기능입니다.

## <a name="related-classes"></a>관련된 클래스

문서 클래스 개체를 영구 수-즉, 해당 상태 저장 매체에 쓸 수 있습니다 및 읽습니다. Mfc는 `CArchive` 문서의 데이터를 저장 매체에 전송할 수 있도록 하는 클래스입니다.

[CArchive](../mfc/reference/carchive-class.md)<br/>
협력 하 여는 [CFile](../mfc/reference/cfile-class.md) serialization 통해 개체에 대 한 영구 저장소를 구현 하는 개체 (참조 [cobject:: Serialize](../mfc/reference/cobject-class.md#serialize)).

문서는 OLE 개체를 포함할 수도 있습니다. `CDocItem` 서버 및 클라이언트 항목의 기본 클래스가입니다.

[CDocItem](../mfc/reference/cdocitem-class.md)<br/>
기본 클래스의 추상 [COleClientItem](../mfc/reference/coleclientitem-class.md) 하 고 [COleServerItem](../mfc/reference/coleserveritem-class.md)합니다. 파생 된 클래스의 개체 `CDocItem` 문서 부분을 나타냅니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../mfc/class-library-overview.md)
