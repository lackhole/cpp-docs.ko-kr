---
title: 장치 컨텍스트
ms.date: 11/04/2016
helpviewer_keywords:
- OnPrepareDC method [MFC]
- windows [MFC], and device context
- drawing [MFC], device context
- CClientDC class [MFC], and GetDC method [MFC]
- drawing [MFC], in mouse and device contexts
- CDC class [MFC], objects
- device contexts [MFC]
- client areas
- CMetaFileDC class [MFC], and OnPrepareDC method [MFC]
- GDI objects [MFC], device contexts
- graphic objects [MFC], device contexts
- frame windows [MFC], device contexts
- metafiles and device contexts
- EndPaint method [MFC]
- printers [MFC], device contexts
- mouse [MFC], drawing and device contexts
- BeginPaint method, CPaintDC
- CPaintDC class [MFC], device context for painting
- windows [MFC], drawing directly into
- client areas, and device context
- device contexts [MFC], CDC class [MFC]
- user interface [MFC], device contexts
- device-independent drawing
- GetDC method and CClientDC class [MFC]
- CClientDC class [MFC], and ReleaseDC method [MFC]
- ReleaseDC method [MFC]
- device contexts [MFC], about device contexts
- drawing [MFC], directly into windows
- painting and device context
ms.assetid: d0cd51f1-f778-4c7e-bf50-d738d10433c7
ms.openlocfilehash: 7893b446c224dd84514ab63dc97cae467792750c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405978"
---
# <a name="device-contexts"></a>장치 컨텍스트

장치 컨텍스트가 화면 또는 프린터와 같은 장치 그리기 특성에 대 한 정보를 포함 하는 Windows 데이터 구조체입니다. 모든 그리기 호출은 그리기 선, 도형 및 텍스트에 대 한 Windows Api를 캡슐화 하는 장치 컨텍스트 개체를 통해 수행 됩니다. 장치 컨텍스트는 Windows에서 장치 독립적 그리기를 허용합니다. 그릴 화면, 프린터 또는 메타 파일 장치 컨텍스트를 사용할 수 있습니다.

[CPaintDC](../mfc/reference/cpaintdc-class.md) 호출을 Windows의 일반적인 관용구를 캡슐화 하는 개체를 `BeginPaint` 함수를 다음 장치 컨텍스트에서 그리기를 호출 합니다 `EndPaint` 함수입니다. 합니다 `CPaintDC` 생성자 호출 `BeginPaint` , 및 소멸자 호출에 대 한 `EndPaint`합니다. 간소화 된 프로세스를 만들 때 합니다 [CDC](../mfc/reference/cdc-class.md) 개체, 그리고 다음 삭제를 `CDC` 개체. Framework에서이 프로세스의 대부분 자동화 되어 있습니다. 특히 사용자 `OnDraw` 함수에 전달 되는 `CPaintDC` 이미 준비 (통해 `OnPrepareDC`), 단순히를 그립니다. 프레임 워크에 의해 제거 됩니다 및 Windows에 대 한 호출에서 반환 될 때 기본 장치 컨텍스트를 출시 하 `OnDraw` 함수입니다.

[CClientDC](../mfc/reference/cclientdc-class.md) 창의 클라이언트 영역을 나타내는 장치 컨텍스트를 사용 하 여 작업을 캡슐화 하는 개체입니다. `CClientDC` 생성자 호출을 `GetDC` 함수와 소멸자 호출은 `ReleaseDC` 함수입니다. [CWindowDC](../mfc/reference/cwindowdc-class.md) 개체는 해당 프레임을 포함 하 여 전체 창에 나타내는 장치 컨텍스트를 캡슐화 합니다.

[CMetaFileDC](../mfc/reference/cmetafiledc-class.md) 개체에는 Windows 메타 파일 그리기를 캡슐화 합니다. 달리 합니다 `CPaintDC` 전달할 `OnDraw`,이 경우에 호출 해야 [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) 직접.

## <a name="mouse-drawing"></a>마우스 그리기

프레임 워크 프로그램에서 대부분의 그리기-및 따라서 대부분의 장치 컨텍스트 작업-뷰의 이루어집니다 `OnDraw` 멤버 함수입니다. 그러나 다른 용도로 디바이스 컨텍스트 개체를 계속 사용할 수 있습니다. 예를 들어 뷰에서 마우스 움직임을 추적 피드백을 제공 하려면 대기 하지 않고 보기에 직접 그리는 `OnDraw` 호출할 수 있습니다.

이러한 경우에 사용할 수는 [CClientDC](../mfc/reference/cclientdc-class.md) 뷰로 직접 그릴 디바이스 컨텍스트 개체입니다.

### <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [장치 컨텍스트 (정의)](/windows/desktop/gdi/device-contexts)

- [뷰에 그리기](../mfc/drawing-in-a-view.md)

- [뷰를 통해 사용자 입력 해석](../mfc/interpreting-user-input-through-a-view.md)

- [선 및 곡선](/windows/desktop/gdi/lines-and-curves)

- [채워진된 도형](/windows/desktop/gdi/filled-shapes)

- [글꼴 및 텍스트](/windows/desktop/gdi/fonts-and-text)

- [색](/windows/desktop/gdi/colors)

- [좌표 공간 및 변환](/windows/desktop/gdi/coordinate-spaces-and-transformations)

## <a name="see-also"></a>참고자료

[창 개체](../mfc/window-objects.md)
