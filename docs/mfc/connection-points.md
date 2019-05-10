---
title: 연결 지점
ms.date: 11/19/2018
f1_keywords:
- IConnectionPoint
helpviewer_keywords:
- IConnectionPoint interface
- connections, connection points
- OLE COM connection points
- MFC COM, connection points
- COM, connection points
- interfaces, IConnectionPoint
- MFC, COM support
- connection points [MFC]
- CCmdTarget class [MFC], and connection points
- sinks, connection points
ms.assetid: bc9fd7c7-8df6-4752-ac8c-0b177442c88d
ms.openlocfilehash: 6f934c4a5a24c5d54805a60e81cb0afdcdc2c14a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62153315"
---
# <a name="connection-points"></a>연결 지점

이 문서 (이전의 OLE 연결 지점)는 연결 지점을 구현 하는 방법에 설명 된 MFC 클래스를 사용 하 여 `CCmdTarget` 및 `CConnectionPoint`합니다.

이전에 구성 요소 개체 모델 (COM) 정의 하는 일반 메커니즘 (`IUnknown::QueryInterface`*) 사용할 수 있는 개체를 구현 하 고 인터페이스의 기능을 제공 합니다. 그러나 특정 인터페이스를 호출 하는 해당 기능을 노출 하는 개체를 허용 하는 해당 메커니즘을 정의 되지 않았습니다. COM 개체를 수신 하는 방법 대 한 포인터를 정의 하는, (해당 개체의 인터페이스에 대 한 포인터)를 처리 하지만 나가는 인터페이스 (다른 개체의 인터페이스에 개체를 보유 하는 포인터)에 대 한 명시적 모델과 되지 않았습니다. COM 이제 하는 모델, 연결 지점 이라는이 기능을 지원 합니다.

연결에는 두 부분이 있습니다: 원본 및 인터페이스를 구현 하는 개체를 호출 하는 인터페이스를 호출 하는 개체 싱크를 호출 합니다. 연결 지점에는 원본에 의해 노출 된 인터페이스입니다. 원본은 연결점을 노출 하 여 자체 (원본)에 대 한 연결을 설정 하는 싱크를 허용 합니다. 연결을 통해 지점 메커니즘 (의 `IConnectionPoint` 인터페이스)를 싱크 인터페이스에 대 한 포인터는 원본 개체에 전달 됩니다. 이 포인터는 멤버 함수 집합이 싱크 구현에 대 한 액세스를 사용 하 여 소스를 제공합니다. 예를 들어, 싱크에 의해 구현 된 이벤트를 발생 원본 싱크 구현의 적절 한 메서드를 호출할 수 있습니다. 다음 그림에는 연결 방법을 보여 줍니다. 위에서 설명한 지점입니다.

![연결 지점 구현](../mfc/media/vc37lh1.gif "연결 지점 구현") <br/>
구현된 연결 지점

MFC에서이 모델을 구현 하는 [CConnectionPoint](../mfc/reference/cconnectionpoint-class.md) 하 고 [CCmdTarget](../mfc/reference/ccmdtarget-class.md) 클래스입니다. 파생 된 클래스 `CConnectionPoint` 구현 된 `IConnectionPoint` 인터페이스를 다른 개체에 연결 지점을 노출 하는 데 사용 합니다. 클래스에서 파생 된 `CCmdTarget` 구현 된 `IConnectionPointContainer` 인터페이스를 사용 가능한 연결 지점 개체의 모든 열거 하거나 특정 연결 지점을 찾을 수 있습니다.

클래스에서 구현 된 각 연결 지점에 대해 연결 지점을 구현 하는 연결 부분을 선언 해야 합니다. 하나 이상의 연결점을 구현 하는 경우 클래스에서 단일 연결 맵을 선언 해야 합니다. 연결 맵을 ActiveX 컨트롤에서 지 원하는 연결 지점의 테이블입니다.

다음 예제에서는 하나의 연결점을 간단한 연결 맵을 보여 줍니다. 첫 번째 예제에서는 연결 지도 및 지점 선언 두 번째 예제는 맵과 연결 지점을 구현합니다. 사실은 `CMyClass` 이어야 합니다는 `CCmdTarget`-클래스를 파생 합니다. 첫 번째 예에서 코드를 삽입 클래스 선언에서 아래 합니다 **보호** 섹션:

[!code-cpp[NVC_MFCConnectionPoints#1](../mfc/codesnippet/cpp/connection-points_1.h)]

**BEGIN_CONNECTION_PART** 및 **END_CONNECTION_PART** 포함된 된 클래스를 선언 하는 매크로 `XSampleConnPt` (에서 파생 된 `CConnectionPoint`),이 특정 연결 지점 구현 합니다. 재정의 하려는 경우 `CConnectionPoint` 멤버 함수 또는 자신만의 멤버 함수를 추가, 이러한 두 매크로 선언 합니다. 예를 들어 합니다 `CONNECTION_IID` 매크로 재정의 `CConnectionPoint::GetIID` 이러한 두 매크로 사이 배치 하는 경우 멤버 함수입니다.

두 번째 예제에서는 코드는 컨트롤의 구현 파일 (.cpp)에 삽입 됩니다. 이 코드는 연결점을 포함 하는 연결 맵을 구현 `SampleConnPt`:

[!code-cpp[NVC_MFCConnectionPoints#2](../mfc/codesnippet/cpp/connection-points_2.cpp)]

클래스에 둘 이상의 연결 지점 추가 삽입을 하는 경우 **CONNECTION_PART** 매크로 사이 **BEGIN_CONNECTION_MAP** 하 고 **END_CONNECTION_MAP** 매크로입니다.

마지막으로 호출을 추가 `EnableConnections` 클래스의 생성자입니다. 예를 들어:

[!code-cpp[NVC_MFCConnectionPoints#3](../mfc/codesnippet/cpp/connection-points_3.cpp)]

이 코드에 삽입 된 후에 `CCmdTarget`-파생된 클래스에 대 한 연결 지점을 노출 된 `ISampleSink` 인터페이스입니다. 다음 그림에서는이 예제를 보여 줍니다.

![MFC를 사용 하 여 구현 된 연결 지점](../mfc/media/vc37lh2.gif "MFC를 사용 하 여 구현 된 연결 지점") <br/>
MFC를 사용 하 여 구현 하는 연결 지점

일반적으로 연결점 지원 "멀티 캐스팅"-여러 싱크를 브로드캐스트할 수 있도록 동일한 인터페이스에 연결 합니다. 다음 예제에서는 부분을 보여 줍니다. 각 싱크에 연결 지점에서 반복 하 여 멀티 캐스트 하는 방법.

[!code-cpp[NVC_MFCConnectionPoints#4](../mfc/codesnippet/cpp/connection-points_4.cpp)]

이 예제에서 연결의 현재 집합을 검색 합니다 `SampleConnPt` 연결점에 대 한 호출을 사용 하 여 `CConnectionPoint::GetConnections`입니다. 다음 연결 및 호출을 반복 `ISampleSink::SinkFunc` 모든 활성 연결.

## <a name="see-also"></a>참고자료

[MFC COM](../mfc/mfc-com.md)
