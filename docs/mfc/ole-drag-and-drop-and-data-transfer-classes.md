---
title: OLE 끌어서 놓기 및 데이터 전송 클래스
ms.date: 11/04/2016
f1_keywords:
- vc.classes.ole
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE drag and drop [MFC], and data transfer classes
- drag and drop [MFC], classes
- data transfer [MFC], OLE
- data transfer classes [MFC]
ms.assetid: c8ab2825-ed69-4b88-8ae6-f368b94726b8
ms.openlocfilehash: e30a358da55b29f9519bc1ab8ee5c93ada308d98
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62186064"
---
# <a name="ole-drag-and-drop-and-data-transfer-classes"></a>OLE 끌어서 놓기 및 데이터 전송 클래스

이러한 클래스는 OLE 데이터 전송에 사용 됩니다. 끌기 또는 클립보드를 사용 하 여 응용 프로그램 및 drop 간에 전송 될 데이터를 수 있습니다.

[COleDropSource](../mfc/reference/coledropsource-class.md)<br/>
처음부터 끝까지 끌어서 놓기 작업을 제어 합니다. 이 클래스는 끌기 작업을 시작 및 종료 될 때를 결정 합니다. 또한 끌어서 놓기 작업 중 커서 피드백을 표시합니다.

[COleDataSource](../mfc/reference/coledatasource-class.md)<br/>
응용 프로그램 데이터 전송에 대 한 데이터를 제공 하는 경우 사용 합니다. `COleDataSource` 개체 지향 클립보드 개체로 볼 수 없습니다.

[COleDropTarget](../mfc/reference/coledroptarget-class.md)<br/>
끌어서 놓기 작업의 대상을 나타냅니다. `COleDropTarget` 화면의 창에 해당 하는 개체입니다. 끌어 놓은 데이터를 수락 하 실제 삭제 작업을 구현 하는 지 여부를 결정 합니다.

[COleDataObject](../mfc/reference/coledataobject-class.md)<br/>
수신자 쪽으로 사용할 `COleDataSource`합니다. `COleDataObject` 저장 된 데이터에 대 한 액세스를 제공 하는 개체를 `COleDataSource` 개체입니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../mfc/class-library-overview.md)
