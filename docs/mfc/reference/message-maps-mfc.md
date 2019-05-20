---
title: 메시지 맵(MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- message maps [MFC], MFC
- Windows messages [MFC], message maps
- messages [MFC], Windows
- MFC, messages
ms.assetid: 3f9855e4-9d7d-4b64-8f3f-a19ea3cf79ba
ms.openlocfilehash: 14c08a008456160fe817f066e5b22b06b9f9fa14
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65611825"
---
# <a name="message-maps-mfc"></a>메시지 맵(MFC)

모든 참조의이 섹션에서는 나열 [메시지 매핑 매크로](../../mfc/reference/message-map-macros-mfc.md) all [CWnd](../../mfc/reference/cwnd-class.md) 해당 멤버와 함께 메시지 맵 항목 함수 프로토타입:

|범주|설명|
|--------------|-----------------|
|ON\_명령 메시지 처리기|처리 `WM_COMMAND` 사용자 메뉴를 선택 하거나 메뉴 선택 키에서 생성 된 메시지입니다.|
|[자식 창 알림 메시지 처리기](../../mfc/reference/child-window-notification-message-handlers.md)|자식 창 알림 메시지를 처리 합니다.|
|[WM_ 메시지 처리기](../../mfc/reference/handlers-for-wm-messages.md)|처리할 `WM_` 메시지와 같은 `WM_PAINT`합니다.|
|[사용자 정의 메시지 처리기](../../mfc/reference/user-defined-handlers.md)|사용자 정의 메시지를 처리 합니다.|

(이 참조에 사용 된 규칙 및 용어는 설명은 참조 하세요. [메시지 맵 상호 참조를 사용 하는 방법을](../../mfc/reference/how-to-use-the-message-map-cross-reference.md).)

Windows 메시지 지향 운영 체제를 이므로 Windows 환경에 대 한 프로그래밍의 많은 부분을 메시지 처리를 포함 합니다. 다음 이벤트를 처리 해야 하는 응용 프로그램에 메시지를 보내는 예: 키 입력 또는 마우스 이벤트 클릭 될 때마다 발생 합니다.

Microsoft Foundation Class 라이브러리는 메시지 기반 프로그래밍에 대 한 액세스에 최적화 된 프로그래밍 모델을 제공 합니다. 이 모델에서 "메시지 맵" 함수는 특정 클래스에 대 한 다양 한 메시지를 처리 하는 지정 하는 데 사용 됩니다. 메시지 맵은 메시지는 함수에 의해 처리 되는 지정 하는 하나 이상의 매크로 포함 합니다. 예를 들어, 맵을 포함 하는 메시지는 `ON_COMMAND` 매크로 다음과 같이 표시 될 수 있습니다.

[!code-cpp[NVC_MFCMessageMaps#16](../../mfc/reference/codesnippet/cpp/message-maps-mfc_1.cpp)]

`ON_COMMAND` 매크로 메뉴, 단추 및 액셀러레이터 키에서 생성 된 명령 메시지를 처리 하는 데 사용 됩니다. [매크로](../../mfc/reference/message-map-macros-mfc.md) 다음 매핑할 수 있습니다.

## <a name="windows-messages"></a>Windows 메시지

- 컨트롤 알림

- 사용자 정의 메시지

## <a name="command-messages"></a>명령 메시지

- 사용자 정의 메시지를 등록합니다.

- 사용자 인터페이스 업데이트 메시지

## <a name="ranges-of-messages"></a>메시지의 범위

- 명령

- 업데이트 메시지 처리기

- 컨트롤 알림

메시지 맵 매크로 중요 하지만, 일반적으로 않아도 직접 사용 합니다. 즉, 속성 창 메시지를 사용 하 여 메시지 처리 함수를 연결 하려면 사용 하는 경우 소스 파일에서 메시지 맵 항목 자동으로 만듭니다. 메시지 맵 항목을 추가 하거나 편집 하려면 언제 든 지 속성 창을 사용할 수 있습니다.

> [!NOTE]
>  속성 창에서 메시지 맵 범위를 지원 하지 않습니다. 이러한 메시지 맵 항목을 직접 작성 해야 합니다.

그러나 메시지 맵 Microsoft Foundation Class 라이브러리의 중요 한 부분이 됩니다. 용도 이해 해야 하 고 설명서에 제공 됩니다.

## <a name="see-also"></a>참고자료

[구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)
