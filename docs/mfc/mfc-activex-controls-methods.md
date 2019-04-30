---
title: 'MFC ActiveX 컨트롤: 메서드'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], methods
ms.assetid: e20271de-6ffa-4ba0-848b-bafe6c9e510c
ms.openlocfilehash: 71c4cdd5ea07b3468b7878a221129a0de5eb4974
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386371"
---
# <a name="mfc-activex-controls-methods"></a>MFC ActiveX 컨트롤: 메서드

ActiveX 컨트롤 자체와 해당 컨트롤 컨테이너 간에 통신 하는 이벤트를 발생 시킵니다. 컨테이너도 메서드 및 속성을 사용 하 여 컨트롤과 통신할 수 있습니다. 메서드는 함수 라고도 합니다.

메서드 및 속성은 자동화 클라이언트 및 ActiveX 컨트롤 컨테이너와 같은 다른 응용 프로그램에서 사용할 내보낸된 인터페이스를 제공 합니다. ActiveX 컨트롤 속성에 대 한 자세한 내용은 문서를 참조 하세요. [MFC ActiveX 컨트롤: 속성](../mfc/mfc-activex-controls-properties.md)합니다.

메서드는 유사한 용도가 멤버 함수는 C++ 클래스입니다. 컨트롤을 구현할 수는 메서드의 두 가지가: 스톡 및 사용자 지정 합니다. 이러한 메서드는을 스톡 이벤트, 메서드 주식 비슷합니다 [COleControl](../mfc/reference/colecontrol-class.md) 구현을 제공 합니다. 주식 메서드에 대 한 자세한 내용은 문서를 참조 하세요. [MFC ActiveX 컨트롤: 스톡 메서드 추가](../mfc/mfc-activex-controls-adding-stock-methods.md)합니다. 개발자가 정의한 사용자 지정 메서드는 컨트롤의 추가 사용자 지정을 허용 합니다. 자세한 내용은 문서를 참조 하세요. [MFC ActiveX 컨트롤: 사용자 지정 메서드 추가](../mfc/mfc-activex-controls-adding-custom-methods.md)합니다.

주식형 및 사용자 지정 메서드를 지원 하기 위해 컨트롤 수 있는 메커니즘을 구현 하는 Microsoft Foundation 클래스 라이브러리 (MFC). 첫 번째 부분은 클래스 `COleControl`합니다. 파생 된 `CWnd`, `COleControl` 멤버 함수는 모든 ActiveX 컨트롤에 공통 된 스톡 메서드를 지원 합니다. 이 메커니즘의 두 번째 부분은 디스패치 맵입니다. 디스패치 맵은 메시지 맵;에 대해 비슷합니다. 그러나 Windows 메시지 ID를 함수에 매핑할 대신 디스패치 맵은 가상 멤버 함수에 매핑됩니다 IDispatch ID.

다양 한 메서드를 제대로 지원 하기 위해 컨트롤의 경우 해당 클래스에는 디스패치 맵은 선언 해야 합니다. 이 컨트롤 클래스 헤더에 있는 코드의 다음 줄을 통해 이루어집니다 (합니다. H) 파일:

[!code-cpp[NVC_MFC_AxUI#13](../mfc/codesnippet/cpp/mfc-activex-controls-methods_1.h)]

디스패치 맵의 주요 목적은 외부 호출자 (예: 컨테이너) 및 메서드를 구현 하는 컨트롤의 클래스의 멤버 함수에서 사용 하는 메서드 이름 간의 관계를 설정 하는 것입니다. 컨트롤의 구현에서 정의 해야 디스패치 맵을 선언한 후 (합니다. Cpp) 합니다. 다음 코드 줄은 디스패치 맵을 정의합니다.

[!code-cpp[NVC_MFC_AxUI#14](../mfc/codesnippet/cpp/mfc-activex-controls-methods_2.cpp)]
[!code-cpp[NVC_MFC_AxUI#15](../mfc/codesnippet/cpp/mfc-activex-controls-methods_3.cpp)]

사용 하는 경우는 [MFC ActiveX 컨트롤 마법사](../mfc/reference/mfc-activex-control-wizard.md) 프로젝트를 만들려면 이러한 줄 된 자동으로 추가 합니다. MFC ActiveX 컨트롤 마법사, 사용 되지 않은 경우이 줄을 수동으로 추가 해야 합니다.

다음 문서에는 메서드를 자세히 설명합니다.

- [MFC ActiveX 컨트롤: 스톡 메서드 추가](../mfc/mfc-activex-controls-adding-stock-methods.md)

- [MFC ActiveX 컨트롤: 사용자 지정 메서드 추가](../mfc/mfc-activex-controls-adding-custom-methods.md)

- [MFC ActiveX 컨트롤: 메서드에서 오류 코드 반환](../mfc/mfc-activex-controls-returning-error-codes-from-a-method.md)

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)
