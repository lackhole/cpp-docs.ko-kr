---
title: 표준 컨트롤에서 컨트롤 파생시키기
ms.date: 11/04/2016
helpviewer_keywords:
- standard controls [MFC], deriving controls from
- common controls [MFC], deriving from
- derived controls
- controls [MFC], derived
- Windows common controls [MFC], deriving from
- standard controls
ms.assetid: a6f84315-7007-4e0e-8576-78be81254802
ms.openlocfilehash: 5abdcc87dba937938ffa3643d19ff69431f62af4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62206946"
---
# <a name="deriving-controls-from-a-standard-control"></a>표준 컨트롤에서 컨트롤 파생시키기

모든와 마찬가지로 [CWnd](../mfc/reference/cwnd-class.md)-파생 클래스에서 기존 컨트롤 클래스에서 새 클래스를 파생 하 여 컨트롤의 동작을 수정할 수 있습니다.

### <a name="to-create-a-derived-control-class"></a>파생된 컨트롤 클래스를 만들려면

1. 기존 컨트롤 클래스에서 클래스를 파생 하 고 선택적으로 재정의 합니다 `Create` 멤버 함수는 기본 클래스에 필요한 인수를 제공 되도록 `Create` 함수입니다.

1. 메시지 처리기 멤버 함수 및 특정 Windows 메시지에 따라에서 컨트롤의 동작을 수정 하는 메시지 맵 항목을 제공 합니다. 참조 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)합니다.

1. (선택 사항) 컨트롤의 기능을 확장 하는 새 멤버 함수를 제공 합니다.

파생된 된 컨트롤을 사용 하 여 대화 상자에서 추가 작업이 필요 합니다. 형식 및 대화 상자에서 컨트롤의 위치는 일반적으로 대화 상자 템플릿 리소스에서 지정 됩니다. 파생된 컨트롤 클래스를 만드는 경우 리소스 컴파일러를 사용 하면 파생 된 클래스에 대 한 아무런 되므로 대화 상자 템플릿에서 지정할 수 없습니다. 있습니다.

#### <a name="to-place-your-derived-control-in-a-dialog-box"></a>대화 상자에서 파생 된 컨트롤을 배치 하려면

1. 파생 된 대화 상자 클래스의 선언에서 파생 된 컨트롤 클래스의 개체를 포함 합니다.

1. 재정의 `OnInitDialog` 멤버 함수를 호출 하 여 대화 상자 클래스는 `SubclassDlgItem` 파생된 컨트롤에 대 한 멤버 함수입니다.

`SubclassDlgItem` "동적으로 서브 클래스 에서" 컨트롤을 대화 상자 템플릿에서 생성 합니다. 컨트롤은 동적 서브클래싱 되는 경우 있습니다 Windows에 연결, 사용자 고유의 응용 프로그램 내에서 일부 메시지를 처리 다음 Windows 로그온 나머지 메시지를 전달 합니다. 자세한 내용은 참조는 [SubclassDlgItem](../mfc/reference/cwnd-class.md#subclassdlgitem) 클래스의 멤버 함수 `CWnd` 에 *MFC 참조*. 다음 예제에서는 재정의 작성 하는 방법을 보여 줍니다 `OnInitDialog` 호출할 `SubclassDlgItem`:

[!code-cpp[NVC_MFCControlLadenDialog#3](../mfc/codesnippet/cpp/deriving-controls-from-a-standard-control_1.cpp)]

파생된 컨트롤 대화 상자 클래스에 포함 되므로, 대화 상자를 생성 하 고 대화 상자가 소멸 될 때 소멸 됩니다 때 생성 됩니다. 이 코드의 예제를 비교 [컨트롤 By 직접 추가](../mfc/adding-controls-by-hand.md)합니다.

## <a name="see-also"></a>참고자료

[컨트롤 만들기 및 사용](../mfc/making-and-using-controls.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
