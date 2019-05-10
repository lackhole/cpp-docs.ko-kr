---
title: '연습: MFC 프로젝트에 D2D 개체 추가'
ms.date: 04/25/2019
helpviewer_keywords:
- MFC, D2D
- D2D [MFC]
ms.assetid: dda36c33-c231-4da6-a62f-72d69a12b6dd
ms.openlocfilehash: 5710add59c0e5d27b2969ae22087533cae901ca9
ms.sourcegitcommit: 283cb64fd7958a6b7fbf0cd8534de99ac8d408eb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64558178"
---
# <a name="walkthrough-adding-a-d2d-object-to-an-mfc-project"></a>연습: MFC 프로젝트에 D2D 개체 추가

이 연습에서는 기본 Direct2D를 추가 하는 방법에 설명 (D2D) 시각적 개체 C++, Microsoft Foundation 클래스 라이브러리 (MFC) 프로젝트 및 다음 빌드할 프로젝트 출력 하는 응용 프로그램에 "Hello, world" 배경에 그라데이션 효과에 있습니다.

이 연습에서는 이러한 작업을 수행 하는 방법을 보여 줍니다.

- MFC 응용 프로그램을 만듭니다.

- 단색 브러시 및 선형 그라데이션 브러시를 만듭니다.

- 그라데이션 브러시를 수정 하는 창 크기를 조정할 때 적절 하 게 변경 합니다.

- D2D 그리기 처리기를 구현 합니다.

- 결과 확인 합니다.

[!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]

## <a name="prerequisites"></a>전제 조건

Visual Studio를 설치 하려면이 연습을 완료 해야 합니다 **를 사용한 데스크톱 개발 C++**  워크 로드 및 선택적 **Visual C++ x86 및 x64 용 MFC** 구성 요소입니다.

## <a name="to-create-an-mfc-application"></a>MFC 응용 프로그램을 만들려면

1. 사용 된 **MFC 응용 프로그램 마법사** MFC 응용 프로그램을 만들려면. [연습: 새 MFC 셸 컨트롤을 사용 하 여](walkthrough-using-the-new-mfc-shell-controls.md) 방법은 Visual Studio의 버전에 대 한 마법사를 엽니다.

1. 에 **이름을** 상자에 입력 *MFCD2DWalkthrough*합니다. **확인**을 선택합니다.

1. 에 **MFC 응용 프로그램 마법사**, 선택 **마침** 설정을 변경 하지 않고 있습니다.

## <a name="to-create-a-solid-color-brush-and-a-linear-gradient-brush"></a>단색 브러시 및 선형 그라데이션 브러시를 만들려면

1. **솔루션 탐색기**를 **MFCD2DWalkthrough** 프로젝트를 합니다 **헤더 파일** 폴더를 열고 MFCD2DWalkthroughView.h 합니다. 이 코드를 추가 합니다 `CMFCD2DWalkthroughView` 세 개의 데이터 변수를 만들려면 클래스:

   ```cpp
   CD2DTextFormat* m_pTextFormat;
   CD2DSolidColorBrush* m_pBlackBrush;
   CD2DLinearGradientBrush* m_pLinearGradientBrush;
   ```

   파일을 저장 하 고 닫습니다.

1. 에 **소스 파일** 폴더를 열고 MFCD2DWalkthroughView.cpp 합니다. 생성자에는 `CMFCD2DWalkthroughView` 클래스에이 코드를 추가 합니다.

   ```cpp
   // Enable D2D support for this window:
   EnableD2DSupport();

   // Initialize D2D resources:
   m_pBlackBrush = new CD2DSolidColorBrush(
       GetRenderTarget(),
       D2D1::ColorF(D2D1::ColorF::Black));

   m_pTextFormat = new CD2DTextFormat(
       GetRenderTarget(),
       _T("Verdana"),
       50);

   m_pTextFormat->Get()->SetTextAlignment(
       DWRITE_TEXT_ALIGNMENT_CENTER);

   m_pTextFormat->Get()->SetParagraphAlignment(
       DWRITE_PARAGRAPH_ALIGNMENT_CENTER);

   D2D1_GRADIENT_STOP gradientStops[2];

   gradientStops[0].color =
       D2D1::ColorF(D2D1::ColorF::White);

   gradientStops[0].position = 0.f;
   gradientStops[1].color =
       D2D1::ColorF(D2D1::ColorF::Indigo);

   gradientStops[1].position = 1.f;

   m_pLinearGradientBrush = new CD2DLinearGradientBrush(
       GetRenderTarget(),
       gradientStops,
       ARRAYSIZE(gradientStops),
       D2D1::LinearGradientBrushProperties(
           D2D1::Point2F(0,0),
           D2D1::Point2F(0,0)));
   ```

   파일을 저장 하 고 닫습니다.

## <a name="to-modify-the-gradient-brush-so-that-it-will-change-appropriately-when-the-window-is-resized"></a>창 크기를 조정할 때 적절히 변경 되도록 그라데이션 브러시를 수정 하려면

1. 에 **프로젝트** 메뉴 선택 **클래스 마법사**합니다.

1. 에 **MFC 클래스 마법사**아래에 있는 **클래스 이름을**를 선택 `CMFCD2DWalkthroughView`합니다.

1. 에 **메시지** 탭의 **메시지** 상자에서 `WM_SIZE` 선택한 후 **처리기 추가**합니다. 이 작업을 추가 합니다 `OnSize` 메시지 처리기를 `CMFCD2DWalkthroughView` 클래스.

1. 에 **기존 처리기** 상자에서 `OnSize`합니다. 선택할 **코드 편집** 표시할는 `CMFCD2DWalkthroughView::OnSize` 메서드. 메서드 끝에 다음 코드를 추가 합니다.

   ```cpp
   m_pLinearGradientBrush->SetEndPoint(CPoint(cx, cy));
   ```

   파일을 저장 하 고 닫습니다.

## <a name="to-implement-a-d2d-drawing-handler"></a>D2D 그리기 처리기를 구현 하려면

1. 에 **프로젝트** 메뉴 선택 **클래스 마법사**합니다.

1. 에 **MFC 클래스 마법사**아래에 있는 **클래스 이름을**를 선택 `CMFCD2DWalkthroughView`합니다.

1. 에 **메시지** 탭에서 **사용자 지정 메시지 추가**합니다.

1. 에 **사용자 지정 메시지 추가** 대화 상자의 합니다 **사용자 지정 Windows 메시지** 상자에 입력 *AFX_WM_DRAW2D*합니다. 에 **메시지 처리기 이름은** 상자에 입력 *OnDraw2D*합니다. 선택 된 **등록 된 메시지** 옵션을 선택한 **확인**합니다. 이 작업은 AFX_WM_DRAW2D 메시지에 대 한 메시지 처리기를 추가 합니다 `CMFCD2DWalkthroughView` 클래스입니다.

1. 에 **기존 처리기** 상자에서 `OnDraw2D`합니다. 선택할 **코드 편집** 표시할는 `CMFCD2DWalkthroughView::OnDraw2D` 메서드. 이 코드를 사용 하 여 `CMFCD2DWalkthroughView::OnDrawD2D` 메서드:

   ```cpp
   afx_msg LRESULT CMFCD2DWalkthroughView::OnDraw2D(
       WPARAM wParam,
       LPARAM lParam)
   {
       CHwndRenderTarget* pRenderTarget = (CHwndRenderTarget*)lParam;
       ASSERT_VALID(pRenderTarget);

       CRect rect;
       GetClientRect(rect);

       pRenderTarget->FillRectangle(rect, m_pLinearGradientBrush);

       pRenderTarget->DrawText(
           _T("Hello, World!"),
           rect,
           m_pBlackBrush,
           m_pTextFormat);

       return TRUE;
   }
   ```

   파일을 저장 하 고 닫습니다.

## <a name="to-verify-the-results"></a>결과 확인 하려면

애플리케이션을 빌드 및 실행합니다. 창 크기를 조정할 때 변경 되는 그라데이션 사각형이 있어야 합니다. "Hello World!" 사각형의 가운데에 표시 합니다.

## <a name="see-also"></a>참고자료

[연습](../mfc/walkthroughs-mfc.md)
