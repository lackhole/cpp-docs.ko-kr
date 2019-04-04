---
title: '컨테이너: 컨테이너를 구현합니다.'
ms.date: 11/04/2016
helpviewer_keywords:
- applications [OLE], OLE container
- OLE containers [MFC], implementing
ms.assetid: af1e2079-619a-4eac-9327-985ad875823a
ms.openlocfilehash: b0d737a2025ed0006db00425d42c02ebf0bdeda8
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58767888"
---
# <a name="containers-implementing-a-container"></a>컨테이너: 컨테이너를 구현합니다.

이 문서는 컨테이너를 구현 하는 절차를 요약 하 고 자세한 내용을 보려면 컨테이너를 구현 하는 방법에 대 한 설명을 제공 하는 다른 문서를 안내 합니다. 또한 일부 선택적 OLE 구현 하려는 기능과 이러한 기능을 설명 하는 문서를 나열 합니다.

#### <a name="to-prepare-your-cwinapp-derived-class"></a>CWinApp에서 파생 된 클래스를 준비 하려면

1. OLE 라이브러리를 호출 하 여 초기화 `AfxOleInit` 에 `InitInstance` 멤버 함수입니다.

1. 호출 `CDocTemplate::SetContainerInfo` 에서 `InitInstance` 메뉴 및 액셀러레이터를 할당 하는 포함 된 항목이 있을 때 사용 되는 리소스는 내부 활성화. 이 항목에 대 한 자세한 내용은 참조 하세요. [활성화](../mfc/activation-cpp.md)합니다.

이러한 기능은 MFC 응용 프로그램 마법사를 사용 하 여 컨테이너 응용 프로그램을 만드는 경우를 제공 됩니다. 참조 [MFC EXE 프로그램 만들기](../mfc/reference/mfc-application-wizard.md)합니다.

#### <a name="to-prepare-your-view-class"></a>뷰 클래스를 준비 하려면

1. 유지 되는 포인터를 유지 하 여 선택한 항목의 추적 또는 목록 선택된 된 항목에 여러 선택 영역을 지 원하는 경우 포인터입니다. 프로그램 `OnDraw` 함수에는 모든 OLE 항목도 그립니다 해야 합니다.

1. 재정의 `IsSelected` 에 전달 된 항목이 현재 선택 되어 있는지 여부를 확인 합니다.

1. 구현 하는 `OnInsertObject` 표시할 메시지 처리기는 **개체 삽입** 대화 상자.

1. 구현 된 `OnSetFocus` 메시지 처리기 보기에서 포커스를 전체 활성 OLE 전송할 항목을 포함 합니다.

1. 구현 하는 `OnSize` OLE를 알리기 위해 메시지 처리기 포함 항목 포함 하는 뷰의 크기의 변경 내용을 반영 하려면 해당 영역을 변경 해야 합니다.

다음 응용 프로그램에서 이러한 기능을 구현 천차만별 때문에 응용 프로그램 마법사만 기본 구현을 제공 합니다. 가능성이 제대로 작동 하려면 응용 프로그램에 이러한 함수를 사용자 지정 해야 합니다. 이 예제를 참조 합니다 [컨테이너](../overview/visual-cpp-samples.md) 샘플입니다.

#### <a name="to-handle-embedded-and-linked-items"></a>포함 및 연결 된 항목을 처리 하려면

1. 클래스를 파생 [COleClientItem](../mfc/reference/coleclientitem-class.md)합니다. 이 클래스의 개체에 포함 되었거나 OLE 문서에 연결 된 항목을 나타냅니다.

1. 재정의 `OnChange`하십시오 `OnChangeItemPosition`, 및 `OnGetItemPosition`합니다. 이러한 함수는 크기 조정, 위치 및 수정 포함 및 연결 된 항목을 처리 합니다.

응용 프로그램 마법사, 클래스를 파생 됩니다 있지만 재정의할 가능성이 해야 `OnChange` 이전 절차의 2 단계에서이 사용 하 여 다른 함수를 나열 합니다. 기본 구현은 이러한 함수는 다음 응용 프로그램에서 다르게 구현 되므로 대부분의 응용 프로그램에 대 한 사용자 지정 해야 합니다. 이 예제의 경우 MFC 샘플을 참조 하세요 [DRAWCLI](../overview/visual-cpp-samples.md) 하 고 [컨테이너](../overview/visual-cpp-samples.md)합니다.

항목 수가 OLE를 지원 하기 위해 컨테이너 응용 프로그램의 메뉴 구조에 추가 해야 합니다. 에 대 한 자세한 내용은 참조 하세요. [메뉴 및 리소스: 컨테이너 추가](../mfc/menus-and-resources-container-additions.md)합니다.

컨테이너 응용 프로그램에서 다음 기능 중 일부를 지원할 수도 있습니다.

- 포함 된 항목을 편집 하는 경우 내부 활성화.

   자세한 내용은 [활성화](../mfc/activation-cpp.md)합니다.

- OLE 항목 만들기는 서버 응용 프로그램에서 끌어서 선택 합니다.

   자세한 내용은 [끌어서 놓기 (OLE)](../mfc/drag-and-drop-ole.md)합니다.

- 포함 된 개체 또는 조합 컨테이너/서버 응용 프로그램에 연결 합니다.

   자세한 내용은 참조 하세요. [컨테이너: 고급 기능](../mfc/containers-advanced-features.md)합니다.

## <a name="see-also"></a>참고자료

[컨테이너](../mfc/containers.md)<br/>
[컨테이너: 클라이언트 항목](../mfc/containers-client-items.md)
