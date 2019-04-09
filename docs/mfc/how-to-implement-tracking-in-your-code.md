---
title: '방법: 코드에서 추적 구현'
ms.date: 11/04/2016
helpviewer_keywords:
- CRectTracker class [MFC], implementing trackers
ms.assetid: baaeca2c-5114-485f-bf58-8807db1bc973
ms.openlocfilehash: 0f037480e83b8ca1ba12af56904afe25a33e4d6c
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58774466"
---
# <a name="how-to-implement-tracking-in-your-code"></a>방법: 코드에서 추적 구현

OLE 항목을 추적 하려면 항목을 클릭 하거나 문서의 뷰를 업데이트 하는 등의 항목에 관련 된 특정 이벤트를 처리 해야 합니다. 모든 경우에서는 임시를 선언 하는 데 충분 [CRectTracker](../mfc/reference/crecttracker-class.md) 개체 및이 개체를 사용 하 여 항목을 조작 합니다.

사용자가 항목을 선택 하거나 메뉴 명령 사용 하 여 개체를 삽입, 추적기 OLE 항목의 상태를 나타내는 적절 한 스타일을 사용 하 여 초기화 해야 합니다. 다음 표에서 OCLIENT 샘플에서 사용 하는 규칙을 간략하게 설명 합니다. 이러한 스타일에 대 한 자세한 내용은 참조 하세요. `CRectTracker`합니다.

### <a name="container-styles-and-states-of-the-ole-item"></a>컨테이너 스타일 및 OLE 항목의 상태

|표시 되는 스타일|OLE 항목의 상태|
|---------------------|-----------------------|
|점선된 테두리|연결 된 항목|
|실선 테두리|문서에 포함 된 항목|
|크기 조정 핸들|현재 선택 된 항목이|
|빗살 무늬 테두리|항목이 현재 내부 활성화를 임|
|해칭 패턴 오버레이 항목|항목의 서버 열려 있습니다.|

OLE 항목의 상태를 확인 하 고 적절 한 스타일을 설정 하는 프로시저를 사용 하 여 쉽게이 초기화를 처리할 수 있습니다. `SetupTracker` OCLIENT 샘플 나와 함수 추적기 초기화를 보여 줍니다. 이 함수에 대 한 매개 변수는 추적기 주소의 *pTracker*; 추적기 관련 클라이언트 항목에 대 한 포인터 *pItem*; 사각형에 대 한 포인터 *pTrueRect* . 이 함수의 보다 완전 한 예제를 보려면 MFC OLE 샘플 [OCLIENT](../overview/visual-cpp-samples.md)합니다.

합니다 **SetupTracker** 설명은 함수의 기능을 사용 하 여 함수의 줄은 섞여; 코드 예제는 단일 함수를 제공 합니다.

[!code-cpp[NVC_MFCOClient#1](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_1.cpp)]

추적기 최소 크기를 설정 하는 추적기의 스타일을 선택을 취소 하 여 초기화 됩니다.

[!code-cpp[NVC_MFCOClient#2](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_2.cpp)]

다음 줄 항목이 현재 선택 되어 있는지 여부 및 항목을 문서에 연결 또는 포함 여부를 확인 합니다. 크기 조정 핸들 테두리의 내부에 있는 항목을 현재 선택 되어 있는지를 나타내는 스타일을에 추가 됩니다. 항목은 문서에 연결 하는 경우 점선된 테두리 스타일 사용 됩니다. 실선 테두리는 항목이 포함 된 경우에 사용 됩니다.

[!code-cpp[NVC_MFCOClient#3](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_3.cpp)]

다음 코드 오버레이 항목이 현재 이면 빗살 무늬로 사용 하 여 항목을 엽니다.

[!code-cpp[NVC_MFCOClient#4](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_4.cpp)]

추적기를 표시 해야 할 때마다이 함수를 호출할 수 있습니다. 예를 들어이 함수에서 호출 된 `OnDraw` 뷰 클래스의 함수입니다. 추적기의 모양이 뷰는 다시 표시 될 때마다 업데이트 됩니다. 전체 예제를 참조 하세요. 합니다 `CMainView::OnDraw` MFC OLE 샘플 함수의 [OCLIENT](../overview/visual-cpp-samples.md)합니다.

응용 프로그램에서 추적기 코드를 같은 크기 조정, 이동 또는 검색 하 고, 필요한 이벤트를 발생 합니다. 이러한 작업을 선택 하거나 항목을 이동 하는 시도가 이루어집니다 되 고 일반적으로 나타냅니다. 이러한 경우 무엇을 선택 했는지를 결정 해야 합니다: 크기 조정 핸들을 크기 조정 핸들 또는 사이의 테두리의 일부입니다. `OnLButtonDown` 메시지 처리기가 항목을 기준으로 마우스의 위치를 테스트 하는 것이 좋습니다. 호출할 `CRectTracker::HitTest`합니다. 테스트 이외의 값을 반환 하는 경우 `CRectTracker::hitOutside`, 항목 크기가 조정 되거나 이동 됩니다. 따라서 호출 해야 합니다 `Track` 멤버 함수입니다. 참조를 `CMainView::OnLButtonDown` 함수는 MFC OLE 샘플에 있는 [OCLIENT](../overview/visual-cpp-samples.md) 전체 예제입니다.

`CRectTracker` 클래스 작업이 발생 하는 이동, 크기 조정 또는 끌어 여부를 나타내는 데 사용 하는 여러 다른 커서 모양을 제공 합니다. 이 이벤트를 처리 하려면 마우스에서 현재 사용 중인 항목 선택 되어 있는지 여부를 확인 합니다. 인 경우 호출할 `CRectTracker::SetCursor`, 또는 기본 처리기를 호출 합니다. 다음 예제는 MFC OLE 샘플에서 [OCLIENT](../overview/visual-cpp-samples.md):

[!code-cpp[NVC_MFCOClient#5](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_5.cpp)]

## <a name="see-also"></a>참고자료

[추적기: OLE 응용 프로그램에서 추적기 구현](../mfc/trackers-implementing-trackers-in-your-ole-application.md)
