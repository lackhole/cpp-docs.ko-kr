---
title: 액티브 문서 컨테이너
ms.date: 11/19/2018
helpviewer_keywords:
- active documents [MFC], containers
- active document containers [MFC]
- containers [MFC], active document
- MFC COM, active document containment
ms.assetid: ba20183a-8b4c-440f-9031-e5fcc41d391b
ms.openlocfilehash: 6e4defaf347f0d539ef023ee9c0e1e85dd2390db
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395032"
---
# <a name="active-document-containers"></a>액티브 문서 컨테이너

Microsoft Office Binder 또는 Internet Explorer와 같은 액티브 문서 컨테이너를 만들고 각각에 대 한 여러 응용 프로그램 프레임을 사용 하도록 요구 하는 것 (대신 단일 프레임 내에서 다른 응용 프로그램 유형의 여러 문서를 사용 하 여 작업할 수 있습니다. 문서 형식)입니다.

MFC에서는 활성 문서 컨테이너에 대 한 전체 지원을 제공 합니다 `COleDocObjectItem` 클래스입니다. MFC 응용 프로그램 마법사를 사용 하 여 선택 하 여 활성 문서 컨테이너를 만들 수는 **액티브 문서 컨테이너** 확인란 합니다 **복합 문서 지원** MFC 응용 프로그램 마법사의 페이지입니다. 자세한 내용은 [활성 문서 컨테이너 응용 프로그램을 만드는](../mfc/creating-an-active-document-container-application.md)합니다.

액티브 문서 컨테이너에 대 한 자세한 내용은 다음을 참조 하세요.

- [컨테이너 요구 사항](#container_requirements)

- [문서 사이트 개체](#document_site_objects)

- [사이트 개체 보기](#view_site_objects)

- [프레임 개체](#frame_object)

- [도움말 메뉴 병합](../mfc/help-menu-merging.md)

- [프로그래밍 방식 인쇄](../mfc/programmatic-printing.md)

- [명령 대상](../mfc/message-handling-and-command-targets.md)

##  <a name="container_requirements"></a> 컨테이너 요구 사항

액티브 문서 컨테이너에 활성 문서 지원 의미 이상의 인터페이스 구현: 포함 된 개체의 인터페이스를 사용 하 여 기술도 필요 합니다. 확장 활성 문서 컨테이너 액티브 문서 자체에서 해당 확장 프로그램 인터페이스를 사용 하는 방법을 알고 수도 있어야 경우도 마찬가지입니다.

액티브 문서를 통합 하는 액티브 문서 컨테이너 수행 해야 합니다.

- 개체를 통해 저장소를 처리할 수는 `IPersistStorage` 인터페이스, 즉, 제공 해야 합니다는 `IStorage` 각 활성 문서 인스턴스입니다.

- "사이트" 개체 (문서 또는 포함 당 하나씩 1 개) 필요 OLE 문서의 기본 포함 기능을 지원 구현 하는 `IOleClientSite` 고 `IAdviseSink`입니다.

- 액티브 문서 포함 된 개체의 내부 활성화를 지원 합니다. 컨테이너의 사이트 개체를 구현 해야 합니다 `IOleInPlaceSite` 컨테이너의 프레임 개체를 제공 해야 하 고 `IOleInPlaceFrame`입니다.

- 액티브 문서는 확장을 구현 하 여 지원 `IOleDocumentSite` 문서에 게 컨테이너에 대 한 메커니즘을 제공 합니다. 필요에 따라 컨테이너는 액티브 문서 인터페이스를 구현할 수도 `IOleCommandTarget` 및 `IContinueCallback` 인쇄 또는 저장과 같이 간단한 명령을 선택 하도록 합니다.

프레임 개체, 뷰 개체 및 컨테이너 개체를 구현할 수도 `IOleCommandTarget` 에 설명 된 대로 특정 명령에 대 한 디스패치를 지원 하기 위해 [명령 대상](../mfc/message-handling-and-command-targets.md)합니다. 뷰와 컨테이너 개체를 구현할 수도 수 있습니다 `IPrint` 하 고 `IContinueCallback`에 설명 된 대로 프로그래밍 방식 인쇄를 지원 하기 위해 [프로그래밍 방식 인쇄](../mfc/programmatic-printing.md)합니다.

다음 그림 컨테이너 및 해당 구성 요소 (왼쪽)에 및 활성 문서 (오른쪽)에서 해당 뷰 간의 개념적 관계를 보여 줍니다. 활성 문서 저장소 및 데이터를 관리 하 고 뷰를 표시 하거나 필요에 따라 해당 데이터를 출력 합니다. 굵게 표시 된 인터페이스는 활성 문서 참여; 필요 이러한 굵게 및 기울임꼴는 선택적입니다. 다른 모든 인터페이스는 필수입니다.

![액티브 문서 컨테이너 인터페이스](../mfc/media/vc37gj1.gif "액티브 문서 컨테이너 인터페이스")

하나의 구체적 클래스에는 하나의 뷰만 지 원하는 문서 보기 및 문서 구성 요소 (즉, 해당 인터페이스)를 구현할 수 있습니다. 또한 한 번에 하나의 보기에만 지 원하는 컨테이너 사이트 구체적인 사이트를 단일 클래스로 문서 사이트 및 사이트 보기 결합할 수 있습니다. 컨테이너의 문서 구성 요소는 단순히 여기에 포함 된 아키텍처의 완전 한 설명을 제공 하 고 컨테이너의 프레임 개체 있지만 별도로 존재 해야 합니다. 액티브 문서 포함 아키텍처에는 영향을 받지 않습니다.

##  <a name="document_site_objects"></a> 문서 사이트 개체

액티브 문서 포함 아키텍처 문서 사이트의 추가 OLE 문서에는 클라이언트 사이트 개체와 동일 합니다 `IOleDocument` 인터페이스:

```cpp
interface IOleDocumentSite : IUnknown
{
    HRESULT ActivateMe(IOleDocumentView *pViewToActivate);
}
```

문서 사이트는 개념적으로 하나 이상의 "뷰 site" 개체에 대 한 컨테이너입니다. 각 뷰 site 개체 문서 사이트에서 관리 되는 문서의 개별 뷰 개체와 연결 됩니다. 컨테이너 문서 사이트 마다 하나의 뷰만 지 원하는 경우에 하나의 구체적 클래스를 사용 하 여 사이트 보기 및 문서 사이트 구현할 수 있습니다.

##  <a name="view_site_objects"></a> 사이트 개체 보기

컨테이너의 뷰 site 개체는 문서의 특정 보기에 표시 공간을 관리합니다. 표준 지원 외에도 `IOleInPlaceSite` 인터페이스를 구현도 일반적으로 뷰 site `IContinueCallback` 프로그래밍 방식 인쇄 컨트롤에 대 한 합니다. (뷰 개체에 대 한 되지 쿼리는 `IContinueCallback` 에 실제로 구현할 수 있습니다 있도록 컨테이너 원하는 모든 개체입니다.)

여러 뷰를 지 원하는 컨테이너 개체를 만드는 여러 뷰 site 문서 사이트 내에서 수 있어야 합니다. 통해 제공 된 별도 활성화 및 비활성화 서비스를 사용 하 여 각 뷰에 제공 `IOleInPlaceSite`합니다.

##  <a name="frame_object"></a> 프레임 개체

컨테이너의 프레임 개체는 대부분의 경우는 OLE 문서에서 내부 활성화에 사용 되는 동일한 프레임, 메뉴 및 도구 모음 협상을 처리 하는 것입니다. 뷰 개체를 통해이 프레임 개체에 액세스할 수 있습니다 `IOleInPlaceSite::GetWindowContext`, 컨테이너 문서 (도구 모음 창 수준 협상 및 포함 된 개체 열거형을 처리할 수)를 나타내는 컨테이너 개체에 대 한 액세스도 제공 하는 합니다.

액티브 문서 컨테이너를 추가 하 여 프레임을 보강할 수 `IOleCommandTarget`입니다. 이 인터페이스는 동일한 명령을 보내는 데 컨테이너를 허용할 수 같은 방법으로 활성 문서의 사용자 인터페이스에서 생성 된 명령을 받을 수 있도록 (같은 **새 파일**를 **오픈**를  **다른 이름으로 저장**하십시오 **인쇄**; **복사본 편집**, **붙여넣기**, **취소**, 등)는 현재 문서에 합니다. 자세한 내용은 [명령 대상](../mfc/message-handling-and-command-targets.md)합니다.

## <a name="see-also"></a>참고자료

[활성 문서 포함](../mfc/active-document-containment.md)
