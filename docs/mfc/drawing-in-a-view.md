---
title: 뷰에 그리기
ms.date: 11/04/2016
helpviewer_keywords:
- drawing [MFC], in views
- views [MFC], printing
- views [MFC], updating
- printing [MFC], views
- views [MFC], rendering
- printing views [MFC]
- paint messages in view class [MFC]
- device contexts, screen drawings
ms.assetid: e3761db6-0f19-4482-a4cd-ac38ef7c4d3a
ms.openlocfilehash: bc461347b56379976cdf62014507e3a15529f081
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58772555"
---
# <a name="drawing-in-a-view"></a>뷰에 그리기

뷰의 나타나는 응용 프로그램에서 거의 모든 그리기 `OnDraw` 뷰 클래스에서 재정의 해야 하는 멤버 함수입니다. (예외는 그리기, 나오는 마우스 [는 보기를 통해 사용자 입력 해석](../mfc/interpreting-user-input-through-a-view.md).) 프로그램 `OnDraw` 재정의:

1. 문서 수를 제공 하는 멤버 함수를 호출 하 여 데이터를 가져옵니다.

1. 프레임 워크를 전달 하는 장치 컨텍스트 개체의 멤버 함수를 호출 하 여 데이터 표시 `OnDraw`합니다.

어떤 방식으로든에서 문서의 데이터가 변경 되 면 변경 내용을 반영 하도록 뷰를 다시 그려야 합니다. 일반적으로이 사용자가 문서에 뷰를 통해 변경할 때 발생 합니다. 뷰 문서를 호출 하는 예에서 [UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews) 자체적으로 업데이트 하려면 같은 문서에 대해 모든 보기에 알리기 위해 멤버 함수입니다. `UpdateAllViews` 각 뷰의 호출 [OnUpdate](../mfc/reference/cview-class.md#onupdate) 멤버 함수입니다. 기본 구현을 `OnUpdate` 뷰의 전체 클라이언트 영역을 무효화 합니다. 문서의 수정된 부분에 매핑되는 클라이언트 영역 지역에만 무효화 하도록 재정의할 수 있습니다.

합니다 `UpdateAllViews` 클래스의 멤버 함수 `CDocument` 하며 `OnUpdate` 클래스의 멤버 함수 `CView` 사용 수정 된 문서의 부분을 설명 하는 정보를 전달할 수 있습니다. 이 "힌트" 메커니즘을 통해 뷰가 다시 그려야 하는 영역을 제한할 수 있습니다. `OnUpdate` 두 "힌트" 인수를 사용 합니다. 첫 번째 *lHint*, 형식의 **LPARAM**를 두 번째에 있지만 원하는 모든 데이터를 전달할 수 있습니다 *pHint*, 형식의 `CObject`*, 파생 된 개체에 대 한 포인터를 전달할 수 있습니다 `CObject`합니다.

뷰를 잘못 되 면 Windows 보냅니다를 **WM_PAINT** 메시지입니다. 뷰의 [OnPaint](../mfc/reference/cwnd-class.md#onpaint) 클래스의 장치 컨텍스트 개체를 만들어 메시지에 응답 하는 처리기 함수 [CPaintDC](../mfc/reference/cpaintdc-class.md) 보기의 호출 및 `OnDraw` 멤버 함수입니다. 일반적으로 재정의 작성할 필요가 없습니다 `OnPaint` 처리기 함수입니다.

A [디바이스 컨텍스트](../mfc/device-contexts.md) 디스플레이 또는 프린터와 같은 장치의 그리기 특성에 대 한 정보를 포함 하는 Windows 데이터 구조입니다. 모든 그리기 호출은 디바이스 컨텍스트 개체를 통해 수행 됩니다. 화면에 그리는 `OnDraw` 전달 되는 `CPaintDC` 개체입니다. 프린터에서 그리기, 전달 되는 [CDC](../mfc/reference/cdc-class.md) 개체가 현재 프린터에 대 한 설정입니다.

뷰에 그리기에 대 한 코드는 먼저 문서에 대 한 포인터를 검색 합니다. 다음 장치 컨텍스트를 통해 그리기 호출 합니다. 다음 간단한 `OnDraw` 프로세스 예제를 보여 줍니다.

[!code-cpp[NVC_MFCDocView#1](../mfc/codesnippet/cpp/drawing-in-a-view_1.cpp)]

이 예에서 정의 `GetData` 문서 파생된 클래스의 구성원으로 작동 합니다.

뷰에서 중심 문서에서 가져온 문자열을 출력 합니다. 경우는 `OnDraw` 화면 그리기에 대 한 호출 되는 `CDC` 개체가 전달 되었습니다 *pDC* 는 `CPaintDC` 의 생성자가 이미 호출 `BeginPaint`합니다. 함수를 그리기 호출은 장치 컨텍스트 포인터를 통해 이루어집니다. 장치 컨텍스트 및 그리기 호출에 대 한 내용은 클래스를 참조 하세요. [CDC](../mfc/reference/cdc-class.md) 에 *MFC 참조* 하 고 [창 개체 작업](../mfc/working-with-window-objects.md)합니다.

작성 하는 방법의 예 `OnDraw`를 참조 합니다 [MFC 샘플](../overview/visual-cpp-samples.md)합니다.

## <a name="see-also"></a>참고자료

[뷰 사용](../mfc/using-views.md)
