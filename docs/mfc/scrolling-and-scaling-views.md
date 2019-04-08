---
title: 뷰 스크롤 및 크기 조정
ms.date: 11/04/2016
helpviewer_keywords:
- message handlers [MFC]
- scaling views [MFC]
- message handling [MFC], scroll bars in view class [MFC]
- scroll bars [MFC], messages
- scrolling views [MFC]
ms.assetid: f98a3421-c336-407e-97ee-dbb2ffd76fbd
ms.openlocfilehash: 7d26bc656dec3fdcbb8fc5ea4918ec7d59bc5afc
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58777584"
---
# <a name="scrolling-and-scaling-views"></a>뷰 스크롤 및 크기 조정

MFC 표시 하는 프레임 창의 크기를 자동으로 확장 되는 스크롤 및 뷰는 뷰를 지원 합니다. 클래스 `CScrollView` 두 종류의 보기를 지원 합니다.

스크롤 및 크기 조정에 대 한 자세한 내용은 클래스를 참조 하세요 [CScrollView](../mfc/reference/cscrollview-class.md) 에 *MFC 참조*합니다. 스크롤 예제를 참조 합니다 [Scribble 샘플](../overview/visual-cpp-samples.md)합니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- 뷰 스크롤

- 뷰의 크기 조정

- [뷰 좌표](/windows/desktop/gdi/window-coordinate-system)

##  <a name="_core_scrolling_a_view"></a> 뷰 스크롤

자주 문서의 크기 해당 보기를 표시할 수 있습니다 크기 보다 큽니다. 이 문서의 데이터를 증가 또는 사용자가 보기의 프레임이 되는 창 축소 하기 때문에 발생할 수 있습니다. 이러한 경우 스크롤 뷰를 지원 해야 합니다.

모든 보기에서 스크롤 막대 메시지를 처리할 수 해당 `OnHScroll` 및 `OnVScroll` 멤버 함수입니다. 이러한 함수의 구현 스크롤 막대 메시지 처리 중 사용자가 직접 모든 작업을 수행 하거나 사용할 수는 `CScrollView` 스크롤를 처리 하는 클래스입니다.

`CScrollView` 다음을 수행합니다.

- 창과 뷰포트 크기 및 매핑 모드 관리

- 자동 스크롤 막대 메시지에 대 한 응답으로 스크롤

(사용자가 스크롤 화살표를 클릭) 하는 경우 (사용자가 스크롤 막대 손잡이 클릭) 하는 경우를 "페이지" 및 "line"에 대 한 스크롤 얼마나 지정할 수 있습니다. 보기의 특성에 맞게 이러한 값을 계획 합니다. 예를 들어 다음 그래픽 보기에 대 한 1 픽셀씩 있지만 텍스트 문서의 줄 높이 기준으로 하는 단위로 스크롤 하는 것이 좋습니다.

##  <a name="_core_scaling_a_view"></a> 뷰의 크기 조정

프레임 창의 크기를 자동으로 맞게 보기를 원하는 경우 사용할 수 있습니다 `CScrollView` 스크롤 대신 크기를 조정 합니다. 논리 뷰 늘어나거나 창의 클라이언트 영역에 맞게 정확 하 게 합니다. 확장 된 보기에 스크롤 막대가 없습니다.

## <a name="see-also"></a>참고자료

[뷰 사용](../mfc/using-views.md)
