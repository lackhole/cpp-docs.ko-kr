---
title: OLE 백그라운드
ms.date: 11/04/2016
helpviewer_keywords:
- OLE, about OLE
ms.assetid: 5f654eb5-66b1-40c9-9215-bb85356a67f8
ms.openlocfilehash: 2501373c2ff5904343a6522e4fb18663f5de3843
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62186591"
---
# <a name="ole-background"></a>OLE 백그라운드

OLE를 만들고 항목 또는 "개체"를 포함 하는 문서를 편집할 수 있는 메커니즘으로 만들어집니다 여러 응용 프로그램.

> [!NOTE]
>  OLE 개체 연결 및 포함에 대 한 머리글자어 원래 합니다. 그러나 이제 라고 OLE로 합니다. 연결과 관련이 없는 OLE 부분 액티브 기술 포함이 됩니다.

OLE 문서, 복합 문서 라고 다양 한 유형의 데이터 또는 구성 요소를 원활 하 게 통합 합니다. 사운드 클립, 스프레드시트 및 비트맵은 일반적인 예제 OLE 문서에 있는 구성 요소입니다. OLE 응용 프로그램에서 지 원하는 OLE 문서는 다른 응용 프로그램 간에 전환 하는 방법에 대 한 걱정 없이 사용 하 여 사용자가 수 있습니다. OLE를 전환 하는 수행 하지 않습니다.

복합 문서를 만들고 컨테이너 응용 프로그램 및 서버 응용 프로그램 또는 컨테이너 문서 내에서 항목을 만드는 구성 요소 응용 프로그램을 사용 합니다. 컨테이너, 서버 또는 둘 다 모든 응용 프로그램을 작성할 수 있습니다.

OLE 모두 작동 하는 응용 프로그램 간의 원활한 상호 작용의 목표는 여러 다른 개념을 통합 합니다. 다양 한이 분야는 다음과 같습니다.

- Linking and Embedding

   연결 및 포함 된 다른 응용 프로그램에서 만들어진 OLE 문서 내에서 만든 항목을 저장 하는 두 가지 방법 이며 둘 사이의 차이점에 대 한 일반적인 내용은 문서를 참조 하세요. [OLE 백그라운드: Linking and Embedding](../mfc/ole-background-linking-and-embedding.md)합니다. 자세한 내용은 문서를 참조 하세요 [컨테이너](../mfc/containers.md) 하 고 [서버](../mfc/servers.md)합니다.

- 내부 활성화 (비주얼 편집)

   컨텍스트에서 컨테이너 문서의 포함 된 항목을 활성화 한 위치에서 활성화 또는 비주얼 편집 라고 합니다. 컨테이너 응용 프로그램의 인터페이스는 포함 된 항목을 만든 구성 요소 응용 프로그램의 기능을 통합 하도록 변경 합니다. 실제 데이터 항목에 대 한 링크를 포함 하는 응용 프로그램의 컨텍스트 외부에서 별도 파일에 포함 되어 있으므로 연결 된 항목 위치에서 활성화 되지 않습니다. 내부 활성화에 대 한 자세한 내용은 문서 참조 [활성화](../mfc/activation-cpp.md)합니다.

   > [!NOTE]
   > 연결 및 포함 하 고 내부 활성화 OLE 비주얼 편집의 주요 기능을 제공 합니다.

- Automation 자동화는 다른 응용 프로그램을 구동 하는 하나의 응용 프로그램을 허용 합니다. 구동 응용 프로그램 자동화 클라이언트 이라고 하며 진행 되 고 응용 프로그램 자동화 서버 또는 자동화 구성 요소 라고 합니다. Automation에 대 한 자세한 내용은 문서를 참조 하세요 [자동화 클라이언트](../mfc/automation-clients.md) 하 고 [자동화 서버](../mfc/automation-servers.md)합니다.

   > [!NOTE]
   > Automation은 OLE와 액티브 기술 컨텍스트에서 작동합니다. Com 기반 개체를 자동화할 수 있습니다.

- 복합 파일

   복합 파일에는 구조적 저장 OLE 응용 프로그램에 대 한 복합 문서를 간소화 하는 표준 파일 형식을 제공 합니다. 복합 파일 내에서 저장소 디렉터리의 여러 기능 있고 스트림 파일의 다양 한 기능입니다. 이 기술은 구조적된 저장소를 라고도 합니다. 복합 파일에 대 한 자세한 내용은 문서를 참조 하세요. [컨테이너: 복합 파일](../mfc/containers-compound-files.md)합니다.

- 균일 한 데이터 전송

   균일 한 데이터 전송 (UDT)는 데이터를 보내고 받을 데이터를 전송 하기로 실제 방법에 관계 없이 표준 방식으로 사용할 수 있는 인터페이스의 집합입니다. UDT forms를 통해 전송 된 데이터에 대 한 기본 끌어서 놓습니다. UDT는 이제 클립보드 및 동적 데이터 교환 (DDE)와 같은 기존 Windows 데이터 전송에 대 한 기초로 사용 됩니다. UDT에 대 한 자세한 내용은 문서 참조 [데이터 개체 및 데이터 소스 (OLE)](../mfc/data-objects-and-data-sources-ole.md)합니다.

- 끌어서 놓기

   끌어서 놓기는 응용 프로그램을 windows 응용 프로그램 내에서 또는 응용 프로그램에 단일 창 내 에서도 데이터를 전송 하는 사용 하기 쉬운, 직접 조작 기술입니다. 전송할 데이터가 선택 되 고 필요한 대상에 놓을 합니다. 끌어서 놓기는 단일형 데이터 전송에 기반 합니다. 끌어서 놓기에 대 한 자세한 내용은 문서 참조 [끌어서 놓기](../mfc/drag-and-drop-ole.md)합니다.

- 구성 요소 개체 모델(Component Object Model)

   OLE 개체는 서로 통신할 때 사용 되는 인프라를 제공 하는 구성 요소 개체 모델 (COM). MFC OLE 클래스는 프로그래머에 대 한 COM을 간소화합니다. COM 부분 액티브 기술 이므로 COM 개체의 기반이 되 OLE와 액티브 기술 합니다. COM에 대 한 자세한 내용은 참조는 [액티브 템플릿 라이브러리 (ATL)](../atl/active-template-library-atl-concepts.md) 항목입니다.

다음 문서에서는 일부 더 중요 한 OLE 항목을 다룹니다.

- [OLE 백그라운드: 연결 및 포함](../mfc/ole-background-linking-and-embedding.md)

- [OLE 백그라운드: 컨테이너 및 서버](../mfc/ole-background-containers-and-servers.md)

- [OLE 백그라운드: 구현 전략](../mfc/ole-background-implementation-strategies.md)

- [OLE 백그라운드: MFC 구현](../mfc/ole-background-mfc-implementation.md)

일반 OLE 내용은 위의 문서에서 찾을 수 없습니다 OLE MSDN에서 검색 합니다.

## <a name="see-also"></a>참고자료

[OLE](../mfc/ole-in-mfc.md)
