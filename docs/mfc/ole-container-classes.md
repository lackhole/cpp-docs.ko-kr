---
title: OLE 컨테이너 클래스
ms.date: 11/04/2016
f1_keywords:
- vc.classes.ole
helpviewer_keywords:
- ActiveX classes [MFC]
- container classes [MFC]
- OLE classes [MFC]
- visual editing [MFC], classes
- OLE [MFC], classes
- containers [MFC], OLE container applications
ms.assetid: 1e27e1ab-4c22-41eb-8547-6915c72668ae
ms.openlocfilehash: 87db824e5ab4daec15870b245ea8341be7442109
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62186012"
---
# <a name="ole-container-classes"></a>OLE 컨테이너 클래스

이러한 클래스는 컨테이너 응용 프로그램에서 사용 됩니다. 둘 다 `COleLinkingDoc` 하 고 `COleDocument` 의 컬렉션을 관리 `COleClientItem` 개체입니다. 문서 클래스를 파생 하는 대신 `CDocument`에서 파생 됩니다 `COleLinkingDoc` 또는 `COleDocument`문서에 포함 된 개체에 대 한 링크에 대 한 지원 것인지에 따라 합니다.

사용 하 여를 `COleClientItem` 다른 문서에 대 한 링크 또는 다른 문서에서 포함 된 문서에서 각 OLE 항목을 나타내는 개체입니다.

[COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md)<br/>
액티브 문서 포함을 지원합니다.

[COleDocument](../mfc/reference/coledocument-class.md)<br/>
기본 컨테이너 지원 뿐만 아니라 복합 문서 구현을 사용 합니다. 파생 된 클래스에 대 한 컨테이너 역할 `CDocItem`입니다. 컨테이너 문서에 대 한 기본 클래스에 대 한 기본 클래스로이 클래스를 사용할 수 있습니다 `COleServerDoc`합니다.

[COleLinkingDoc](../mfc/reference/colelinkingdoc-class.md)<br/>
파생 된 클래스 `COleDocument` 연결에 대 한 인프라를 제공 하는 합니다. 대신이 클래스에서 컨테이너 응용 프로그램에 대 한 문서 클래스를 파생 해야 `COleDocument` 포함 된 개체에 대 한 링크를 지원 하도록 하려는 경우.

[CRichEditDoc](../mfc/reference/cricheditdoc-class.md)<br/>
Rich edit 컨트롤에 있는 OLE 클라이언트 항목 목록을 유지 관리 합니다. 사용한 [CRichEditView](../mfc/reference/cricheditview-class.md) 하 고 [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)합니다.

[CDocItem](../mfc/reference/cdocitem-class.md)<br/>
기본 클래스의 추상 `COleClientItem` 고 `COleServerItem`입니다. 파생 된 클래스의 개체 `CDocItem` 문서 부분을 나타냅니다.

[COleClientItem](../mfc/reference/coleclientitem-class.md)<br/>
클라이언트측 포함 또는 연결 된 OLE 항목에 대 한 연결을 나타내는 클라이언트 항목 클래스입니다. 클라이언트 항목을이 클래스에서 파생 됩니다.

[CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)<br/>
사용 하는 경우 서식 있는 편집 컨트롤에 저장 된 항목 OLE 클라이언트 쪽 액세스할 `CRichEditView` 고 `CRichEditDoc`입니다.

[COleException](../mfc/reference/coleexception-class.md)<br/>
OLE 처리 중 오류로 인해 발생하는 예외입니다. 이 클래스는 컨테이너 및 서버에서 모두 사용됩니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../mfc/class-library-overview.md)
