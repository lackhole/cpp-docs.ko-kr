---
title: 데이터 개체 및 데이터 소스(OLE)
ms.date: 11/04/2016
helpviewer_keywords:
- data objects [MFC], definition
- data transfer [MFC]
- OLE [MFC], data transfer
- data sources [MFC], definition
- data transfer [MFC], definition
- OLE [MFC], data objects
- OLE [MFC], data sources
ms.assetid: 8f68eed8-0ce8-4489-a4cc-f95554f89090
ms.openlocfilehash: 485fa5c62aafa4c116a76547238325d2979bfdc4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62241212"
---
# <a name="data-objects-and-data-sources-ole"></a>데이터 개체 및 데이터 소스(OLE)

클립보드 또는 끌어서 놓기를 사용 하 여 데이터 전송을 수행할 때 데이터에는 원본과 대상입니다. 복사에 대 한 데이터를 제공 하는 응용 프로그램 및 다른 응용 프로그램 붙여 넣도록 허용 합니다. 전송의 양쪽에서 성공 하려면 전송에 대 한 동일한 데이터에서 다른 작업을 수행 해야 합니다. Microsoft Foundation 클래스 (MFC) 라이브러리는이 전송의 양쪽을 나타내는 두 개의 클래스를 제공 합니다.

- 데이터 원본 (구현한 대로 `COleDataSource` 개체) 데이터 전송의 원본 쪽을 나타냅니다. 끌어서 놓기 작업에 대 한 데이터를 제공 하는 경우 또는 데이터를 클립보드에 복사할 때 원본 응용 프로그램에 의해 만들어집니다.

- 데이터 개체 (구현한 대로 `COleDataObject` 개체) 데이터 전송의 대상 쪽을 나타냅니다. 대상 응용 프로그램에 데이터를 또는 클립보드에서 붙여넣기 작업을 수행 하 라는 메시지가 표시 되 고 삭제 하는 경우 생성 됩니다.

다음 문서를 데이터 개체 및 응용 프로그램에서 데이터 소스를 사용 하는 방법에 설명 합니다. 이 정보는 모두 데이터 복사 및 붙여넣기 하 되 면 호출 될 수 있으므로 컨테이너와 서버 응용 프로그램에 적용 됩니다.

- [데이터 개체 및 데이터 소스: 생성 및 소멸](../mfc/data-objects-and-data-sources-creation-and-destruction.md)

- [데이터 개체 및 데이터 소스: 조작](../mfc/data-objects-and-data-sources-manipulation.md)

## <a name="in-this-section"></a>섹션 내용

[끌어서 놓기](../mfc/drag-and-drop-ole.md)

[클립보드](../mfc/clipboard.md)

## <a name="see-also"></a>참고자료

[OLE](../mfc/ole-in-mfc.md)<br/>
[COleDataObject 클래스](../mfc/reference/coledataobject-class.md)<br/>
[COleDataSource 클래스](../mfc/reference/coledatasource-class.md)
