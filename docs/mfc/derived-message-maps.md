---
title: 파생된 메시지 맵
ms.date: 11/19/2018
helpviewer_keywords:
- message handling [MFC], derived message handlers
- messages, routing
- message maps [MFC], derived
- derived message maps
ms.assetid: 21829556-6e64-40c3-8279-fed85d99de77
ms.openlocfilehash: fcdff67c57e932e414a2b61b28cd0498ab997c60
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173592"
---
# <a name="derived-message-maps"></a>파생된 메시지 맵

메시지 처리, 클래스의 메시지를 검사 하는 동안 맵이 메시지 맵 영역의 종료 되었습니다. 되나요 클래스 `CMyView` (에서 파생 된 `CView`)에 메시지에 대 한 일치 하는 항목이 없는

에 유의 `CView`의 기본 클래스 `CMyView`를 차례로에서 파생 된 `CWnd`합니다. 따라서 `CMyView` *는* 는 `CView` 및 *됩니다* 는 `CWnd`합니다. 이러한 클래스의 각 자신의 메시지 맵을 있습니다. "는 계층 구조 보기" 아래에 유지 되지만 클래스, 계층적 관계를 보여 줍니다. 그림을 염두에 두어야 하는 `CMyView` 개체는 세 클래스 모두의 특성을 가진 단일 개체입니다.

![뷰 계층 구조](../mfc/media/vc38621.gif "뷰 계층 구조") <br/>
계층 구조 보기

클래스에서 메시지를 일치 시킬 수 없습니다. 따라서 `CMyView`의 프레임 워크가 메시지 맵을 직접 기본 클래스의 메시지 맵을 검색 합니다. `BEGIN_MESSAGE_MAP` 메시지 맵에서의 시작 부분에 매크로 인수로 두 클래스 이름을 지정 합니다.

[!code-cpp[NVC_MFCMessageHandling#2](../mfc/codesnippet/cpp/derived-message-maps_1.cpp)]

첫 번째 인수는 메시지 맵을 속해 있는 클래스를 이름을 지정 합니다. 두 번째 인수는 직접 기본 클래스를 사용 하 여 연결을 제공- `CView` 여기-프레임 워크는 너무 자신의 메시지 맵을 검색할 수 있도록 합니다.

따라서 기본 클래스에서 제공 하는 메시지 처리기는 파생된 클래스에 의해 상속 됩니다. 이 모든 처리기 멤버 함수를 가상으로 만들려면 필요 없이 일반 가상 멤버 함수와 매우 비슷합니다.

처리기의 기본 클래스 메시지 맵 중 하나에 있으면 기본 메시지의 처리 됩니다. 메시지는 명령인 경우 프레임 워크는 다음 명령 대상으로 라우팅합니다. 표준 Windows 메시지 인 경우 메시지를 해당 하는 기본 창 프로시저로 전달 됩니다.

메시지 맵 일치 하는 속도 프레임 워크는 받습니다 동일한 메시지가 다시 가능성에 최근의 일치 항목을 캐시 합니다. 이는 프레임 워크 프로세스 메시지를 매우 효율적으로 처리 됩니다. 메시지 맵 공간-보다 더 효율적 가상 함수를 사용 하는 구현 됩니다.

## <a name="see-also"></a>참고자료

[프레임워크가 메시지 맵을 검색하는 방법](../mfc/how-the-framework-searches-message-maps.md)
