---
title: 활성화(C++)
ms.date: 11/04/2016
helpviewer_keywords:
- OLE server applications [MFC], activation
- OLE items [MFC], visual editing
- activation [MFC]
- OLE [MFC], in-place activation
- OLE [MFC], activation
- in-place activation, embedded and linked items
- activating objects
- visual editing, activation
- visual editing
- documents [MFC], OLE
- embedded objects [MFC]
- OLE [MFC], editing
- in-place activation
- activation [MFC], embedded OLE items
- OLE activation [MFC]
ms.assetid: ed8357d9-e487-4aaa-aa6b-2edc4de25dfa
ms.openlocfilehash: a6009e5209ce71c6eed28faff2f55792a64de408
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392936"
---
# <a name="activation-c"></a>활성화(C++)

이 문서는 OLE 항목의 비주얼 편집 활성화의 역할을 설명 합니다. OLE 항목 컨테이너 문서의 포함 된, 후 사용할 필요할 수 있습니다. 이렇게 하려면 사용자가 해당 항목을 활성화 하는 항목을 두 번 클릭 합니다. 활성화에 대 한 자주 활동 편집 중입니다. 많은 현재 OLE 항목 편집을 위해 활성화 될 때 항목을 만든 서버 응용 프로그램에 속한를 반영 하도록 변경 하려면 현재 프레임 창에서 메뉴 및 도구 모음을 발생 합니다. 이 이와 같이 내부 활성화를 알려진 컨테이너 문서 창과 종료 하지 않고 복합 문서에 포함 된 모든 항목을 편집할 수 있습니다.

도 별도 창에 포함 된 OLE 항목을 편집 하는 것이 가능 합니다. 컨테이너 또는 서버 응용 프로그램 내부 활성화를 지원 하지 않는 경우 발생 합니다. 이 경우 포함 된 항목을 클릭할 때 별도 창에서 서버 응용 프로그램이 시작 되 고 포함된 된 항목 자체 문서로 나타납니다. 사용자가이 창의 항목을 편집 합니다. 편집이 완료 되 면 사용자 서버 응용 프로그램을 닫고 컨테이너 응용 프로그램에 반환 합니다.

대신 선택할 수 있으며 "편집을 열려면"와  **\<개체 > 열기** 명령을 합니다 **편집** 메뉴. 이 별도의 창 개체를 엽니다.

> [!NOTE]
>  별도 창에 포함 된 항목을 편집 하면 OLE의 버전 1의에서 표준 동작 했으며 일부 OLE 응용 프로그램에만이 스타일 편집 지원 될 수 있습니다.

내부 활성화를 문서 중심의 접근 방식을 문서 작성을 승격합니다. 사용자 응용 프로그램 간에 전환 하지 않고 작업할 복합 문서를 단일 엔터티로 처리할 수 있습니다. 그러나 내부 활성화 연결 항목 포함 된 항목에 대해서만 사용 됩니다: 별도 창에서 편집 해야 합니다. 연결 된 항목을 다른 위치에 실제로 저장 되는 때문입니다. 연결 된 항목의 편집 이루어집니다 즉, 데이터의 실제 컨텍스트 내에서 데이터가 저장 됩니다. 별도 창에서 연결 된 항목을 편집 합니다. 데이터를 다른 문서에 속하는 사용자를 게 알립니다.

MFC는 중첩 된 위치에서 활성화를 지원 하지 않습니다. 컨테이너/서버 응용 프로그램을 작성 하는 경우 및 다른 컨테이너 및 내부 활성화에 포함 된 컨테이너/서버를 해당 수 없습니다. 전체 그 안에 포함 된 개체를 활성화 합니다.

사용자가 포함 된 항목에 발생 하는 작업은 항목에 대해 정의 된 동사에 따라 다릅니다. 내용은 [활성화 합니다. 동사](../mfc/activation-verbs.md)합니다.

## <a name="see-also"></a>참고자료

[OLE](../mfc/ole-in-mfc.md)<br/>
[컨테이너](../mfc/containers.md)<br/>
[서버](../mfc/servers.md)
