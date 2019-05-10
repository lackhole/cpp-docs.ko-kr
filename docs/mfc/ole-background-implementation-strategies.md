---
title: 'OLE 백그라운드: Implementation Strategies'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE [MFC], development strategy
- OLE applications [MFC], implementing OLE
- applications [OLE], implementing OLE
ms.assetid: 0875ddae-99df-488c-82c6-164074a81058
ms.openlocfilehash: 83a1089ecaaaa9bd0dd1d928cd3d1869e5017a4a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62186867"
---
# <a name="ole-background-implementation-strategies"></a>OLE 백그라운드: Implementation Strategies

응용 프로그램에 따라 OLE 지원 추가를 위해서는 다음 네 가지 구현 전략을 사용할 수 있습니다.

- 새 응용 프로그램을 작성합니다.

   이 경우에는 일반적으로 필요한 작업이 가장 적습니다. MFC 응용 프로그램 마법사를 실행하고 고급 기능 또는 복합 문서 지원을 선택해서 기초 응용 프로그램을 만듭니다. 이러한 옵션 및 용도에 대 한 내용은 문서 참조 [MFC EXE 프로그램 만들기](../mfc/reference/mfc-application-wizard.md)합니다.

- 프로그램이 Microsoft Foundation Class 라이브러리 버전 2.0 이상으로 작성되어 OLE를 지원하지 않습니다.

   앞에서 설명한 것처럼 MFC 응용 프로그램 마법사를 사용해서 새 응용 프로그램을 만든 후 새 응용 프로그램에서 기존 응용 프로그램으로 코드를 복사하고 붙여넣습니다. 이 방식은 서버, 컨테이너 또는 자동화된 응용 프로그램에서 작동합니다. MFC 참조 [SCRIBBLE](../overview/visual-cpp-samples.md) 이 전략의 예에 대 한 샘플.

- OLE 버전 1.0 지원을 구현하는 Microsoft Foundation Class 라이브러리 프로그램이 있습니다.

   참조 [MFC Technical Note 41](../mfc/tn041-mfc-ole1-migration-to-mfc-ole-2.md) 이 변환 전략에 대 한 합니다.

- 응용 프로그램이 Microsoft Foundation Classes를 사용하여 작성되지 않았고 OLE 지원이 구현되거나 구현되지 않았을 수 있습니다.

   이 경우에는 가장 많은 작업이 필요합니다. 한 가지 방법은 첫 번째 전략에서와 같이 새 응용 프로그램을 만들고 기존 코드를 여기에 복사해서 붙여넣는 방법입니다. 기존 코드가 C로 작성된 경우 C++ 코드로 컴파일될 수 있도록 수정해야 할 수 있습니다. C 코드가 Windows API를 호출하는 경우 Microsoft Foundation Class를 사용하도록 변경할 필요가 없습니다. 이 접근 방법에서는 Microsoft Foundation Class 버전 2.0 이상에서 사용되는 문서/뷰 아키텍처를 지원하기 위해 프로그램을 일부 재구성해야 합니다. 이 아키텍처에 대 한 자세한 내용은 참조 하세요. [Technical Note 25](../mfc/tn025-document-view-and-frame-creation.md)합니다.

읽거나 전략 했으면 해야 합니다 [컨테이너](../mfc/containers.md) 또는 [서버](../mfc/servers.md) (형식에 따라 응용 프로그램을 작성 하는) 문서 또는 샘플 프로그램 중 하나 또는 둘 다 검사 합니다. MFC OLE 샘플 [OCLIENT](../overview/visual-cpp-samples.md) 하 고 [HIERSVR](../overview/visual-cpp-samples.md) 각각 컨테이너 및 서버를 다양 한 측면을 구현 하는 방법을 보여 줍니다. 이러한 문서 전체의 여러 지점에서는 설명 중인 기술의 예제로 이러한 샘플에 포함된 일부 함수가 참조될 수 있습니다.

## <a name="see-also"></a>참고자료

[OLE 백그라운드](../mfc/ole-background.md)<br/>
[컨테이너: 컨테이너 구현](../mfc/containers-implementing-a-container.md)<br/>
[서버: 서버 구현](../mfc/servers-implementing-a-server.md)<br/>
[MFC 응용 프로그램 마법사](../mfc/reference/mfc-application-wizard.md)
