---
title: '연습: 새 MFC 셸 컨트롤 사용'
ms.date: 09/20/2018
helpviewer_keywords:
- shell controls (MFC)
ms.assetid: f0015caa-199d-4aaf-9501-5a239fce9095
ms.openlocfilehash: ef0e4856a844503f8d13b7b6ed37318b76b6af69
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58772152"
---
# <a name="walkthrough-using-the-new-mfc-shell-controls"></a>연습: 새 MFC 셸 컨트롤 사용

이 연습에서는 파일 탐색기와 비슷한 응용 프로그램을 만들어야 합니다. 두 개의 창이 있는 창을 만듭니다. 왼쪽된 창 보유할를 [CMFCShellTreeCtrl](../mfc/reference/cmfcshelltreectrl-class.md) 계층 뷰에서 바탕 화면을 표시 하는 개체입니다. 오른쪽 창 보유할를 [CMFCShellListCtrl](../mfc/reference/cmfcshelllistctrl-class.md) 왼쪽된 창에서 선택한 폴더에 파일을 보여 주는 합니다.

## <a name="prerequisites"></a>전제 조건

이 연습에서는 설정한 후 Visual Studio를 사용 하 여 가정 **일반 개발 설정**합니다. 다른 개발 설정을 사용 하는 경우이 연습에서 사용 하는 몇 가지 Visual Studio windows 기본적으로 표시 되지 않을 수 있습니다.

### <a name="to-create-a-new-mfc-application-by-using-the-mfc-application-wizard"></a>MFC 응용 프로그램 마법사를 사용 하 여 새 MFC 응용 프로그램을 만들려면

1. 사용 된 **MFC 응용 프로그램 마법사** 새 MFC 응용 프로그램을 만드는 합니다. 마법사를 실행 하는 **파일** 메뉴 선택 **새로 만들기**를 선택한 후 **프로젝트**합니다. 합니다 **새 프로젝트** 대화 상자가 표시 됩니다.

1. 에 **새 프로젝트** 대화 상자에서 **Visual C++**  에 노드를 **프로젝트 형식** 창과 선택 **MFC**. 그런 다음 합니다 **템플릿을** 창 **MFC 응용 프로그램**합니다. 같은 프로젝트의 이름을 입력 `MFCShellControls` 누릅니다 **확인**합니다. 이후에 **MFC 응용 프로그램 마법사** 표시는 다음 옵션을 사용 합니다.

    1. 에 **응용 프로그램 유형** 창 아래에 있는 **응용 프로그램 유형**의 선택을 취소 합니다 **탭 문서** 옵션. 다음으로, 선택 **단일 문서로** 선택한 **문서/뷰 아키텍처 지원**합니다. 아래 **스타일 프로젝트**를 선택 **Visual Studio**, 및를 **비주얼 스타일 및 색** 목록 드롭다운 **Office 2007 (파랑 테마)**.

    1. 에 **복합 문서 지원** 창 **None**합니다.

    1. 변경 하지 않도록 합니다 **문서 템플릿 문자열** 창입니다.

    1. 에 **데이터베이스 지원** 창 (Visual Studio 2015 및 이전 버전), 선택 **None** 응용 프로그램 데이터베이스를 사용 하지 않으므로 합니다.

    1. 에 **사용자 인터페이스 기능** 창 있는지 확인 합니다 **메뉴 및 도구 모음을 사용 하 여** 옵션을 선택 합니다. 다른 옵션은 모두 그대로 둡니다.

    1. 에 **고급 기능** 창 아래에 있는 **고급 기능**에 선택 **ActiveX 컨트롤** 및 **공용 컨트롤 매니페스트**합니다. 아래 **고급 프레임 창**만 선택 합니다 **탐색 창** 옵션입니다. 만드는 마법사를 사용 하 여 창의 왼쪽 창 하면를 `CMFCShellTreeCtrl` 이미 포함 합니다.

    1. 아무 것도 변경 않겠습니다 합니다 **생성 된 클래스** 창, 클릭 **마침** 새 MFC 프로젝트를 만드는 합니다.

1. 응용 프로그램을 빌드하고 실행 하 여 만들어졌는지 확인 합니다. 응용 프로그램을 작성 하는 **빌드합니다** 메뉴 선택 **솔루션 빌드**합니다. 응용 프로그램이 성공적으로 빌드되면를 선택 하 여 응용 프로그램을 실행 **디버깅 시작** 에서 합니다 **디버그** 메뉴.

   마법사를 사용 하 여 창의 왼쪽에 표준 메뉴 모음, 표준 도구 모음, 표준 상태 표시줄 및 Outlook 표시줄에 있는 응용 프로그램을 자동으로 만듭니다는 **폴더** 보기 및 **달력** 보기 .

### <a name="to-add-the-shell-list-control-to-the-document-view"></a>문서 보기로 셸 목록 컨트롤을 추가 하려면

1. 이 섹션에서는 인스턴스의 추가 `CMFCShellListCtrl` 마법사에서 만든 보기에 있습니다. 두 번 클릭 하 여 뷰 헤더 파일을 엽니다 **MFCShellControlsView.h** 에 **솔루션 탐색기**합니다.

   찾을 `#pragma once` 헤더 파일의 위쪽 지시문입니다. 에 대 한 헤더 파일을 포함 하도록이 코드를 추가 하는 아래 즉시 `CMFCShellListCtrl`:

   ```cpp
   #include <afxShellListCtrl.h>
   ```

   이제 형식의 멤버 변수를 추가할 `CMFCShellListCtrl`합니다. 첫째, 헤더 파일에 다음 주석을 찾습니다.

   ```cpp
   // Generated message map functions
   ```

   즉시 해당 주석에 위에이 코드를 추가 합니다.

   ```cpp
   private:
   CMFCShellListCtrl m_wndList;
   ```

1. 합니다 **MFC 응용 프로그램 마법사** 이미 만든를 `CMFCShellTreeCtrl` 개체는 `CMainFrame` 하지만 보호 된 멤버의 합니다. 개체를 나중에 액세스, 따라서 이제에 대 한 접근자를 만듭니다 됩니다 했습니다. MainFrm.h 헤더 파일에서 두 번 클릭 하 여 합니다 **솔루션 탐색기**합니다. 다음 주석을 찾습니다.

   ```cpp
   // Attributes
   ```

   바로 아래에 다음 메서드 선언을 추가 합니다.

   ```cpp
   public:
       CMFCShellTreeCtrl& GetShellTreeCtrl();
   ```

   두 번 클릭 하 여 MainFrm.cpp 소스 파일을 엽니다는 **솔루션 탐색기**합니다. 해당 파일의 맨 아래에 다음 메서드 정의 추가 합니다.

   ```cpp
   CMFCShellTreeCtrl& CMainFrame::GetShellTreeCtrl()
   {
        return m_wndTree;
   }
   ```

1. 업데이트에서는 이제는 `CMFCShellControlsView` 처리 하는 클래스는 `WM_CREATE` windows 메시지입니다. 엽니다는 **클래스 뷰** 창과 선택은 `CMFCShellControlsView` 클래스입니다. 마우스 오른쪽 단추로 클릭 **속성**합니다.

    다음으로 **속성** 창에서 클릭 합니다 **메시지** 아이콘. 찾을 때까지 아래로 스크롤하여는 `WM_CREATE` 메시지입니다. 드롭다운 목록에서 옆 `WM_CREATE`을 선택  **\<추가 > OnCreate**합니다. 명령에 메시지 처리기를 만들고 MFC 메시지 맵을 자동으로 업데이트 합니다.

   에 `OnCreate` 메서드를 이제 만들겠습니다 우리의 `CMFCShellListCtrl` 개체. 찾기는 `OnCreate` 메서드 정의 MFCShellControlsView.cpp에서 원본 파일, 및 해당 구현을 다음 코드로 바꿉니다.

    ```cpp
    int CMFCShellControlsView::OnCreate(LPCREATESTRUCT lpCreateStruct)
    {
        if (CView::OnCreate(lpCreateStruct) == -1)
            return -1;

        CRect rectDummy (0, 0, 0, 0);

        m_wndList.Create(WS_CHILD | WS_VISIBLE | LVS_REPORT,
            rectDummy, this, 1);

        return 0;
    }
    ```

1. 이전 단계를 반복 하지만 `WM_SIZE` 메시지입니다. 응용 프로그램 보기를 사용자 응용 프로그램 창의 크기가 변경 될 때마다 다시 그리도록 발생 합니다. 에 대 한 정의 대체 합니다 `OnSize` 메서드를 다음 코드로:

    ```cpp
    void CMFCShellControlsView::OnSize(UINT nType, int cx, int cy)
    {
        CView::OnSize(nType, cx, cy);

        m_wndList.SetWindowPos(NULL, -1, -1, cx, cy,
            SWP_NOMOVE | SWP_NOZORDER | SWP_NOACTIVATE);
    }
    ```

1. 마지막 단계는 연결 합니다 `CMFCShellTreeCtrl` 및 `CMFCShellListCtrl` 사용 하 여 개체를 [CMFCShellTreeCtrl::SetRelatedList](../mfc/reference/cmfcshelltreectrl-class.md#setrelatedlist) 메서드. 호출한 후 `CMFCShellTreeCtrl::SetRelatedList`서 `CMFCShellListCtrl` 에서 선택한 항목의 콘텐츠를 자동으로 표시 됩니다는 `CMFCShellTreeCtrl`합니다. 개체에 연결 합니다 `OnActivateView` 에서 재정의 되는 메서드를 [CView::OnActivateView](../mfc/reference/cview-class.md#onactivateview)합니다.

   MFCShellControlsView.h 헤더 파일에서 내부는 `CMFCShellControlsView` 선언을 클래스에 다음 메서드 선언을 추가 합니다.

    ```cpp
    protected:
    virtual void OnActivateView(BOOL bActivate,
        CView* pActivateView,
        CView* pDeactiveView);
    ```

   다음, MFCShellControlsView.cpp 소스 파일에는 메서드에 대 한 정의 추가 합니다.

    ```cpp
    void CMFCShellControlsView::OnActivateView(BOOL bActivate,
        CView* pActivateView,
        CView* pDeactiveView)
    {
        if (bActivate&& AfxGetMainWnd() != NULL)
        {
            ((CMainFrame*)AfxGetMainWnd())->GetShellTreeCtrl().SetRelatedList(&m_wndList);
        }

        CView::OnActivateView(bActivate,
            pActivateView,
            pDeactiveView);
    }
    ```

   메서드를 호출 하는 것 때문에 합니다 `CMainFrame` 추가 해야 합니다 클래스는 `#include` MFCShellControlsView.cpp 소스 파일의 맨 위에 있는 지시문:

    ```cpp
    #include "MainFrm.h"
    ```

1. 응용 프로그램을 빌드하고 실행 하 여 만들어졌는지 확인 합니다. 응용 프로그램을 작성 하는 **빌드합니다** 메뉴 선택 **솔루션 빌드**합니다. 응용 프로그램이 성공적으로 빌드되면를 선택 하 여 실행할 **디버깅 시작** 에서 합니다 **디버그** 메뉴.

   선택한 항목에 대 한 세부 정보 표시 됩니다는 `CMFCShellTreeCtrl` 뷰 창에서. 노드를 클릭 하는 경우는 `CMFCShellTreeCtrl`, `CMFCShellListCtrl` 자동 업데이트 됩니다. 마찬가지로, 폴더를 두 번 클릭 합니다 `CMFCShellListCtrl`, `CMFCShellTreeCtrl` 자동으로 업데이트 해야 합니다.

   트리 컨트롤에서 또는 목록 컨트롤에서 모든 항목을 마우스 오른쪽 단추로 클릭 합니다. 실제 사용할 때 처럼 동일한 상황에 맞는 메뉴를 얻게 **파일 탐색기**합니다.

## <a name="next-steps"></a>다음 단계

- 마법사를 둘 다를 사용 하 여 Outlook 표시줄 만든를 **폴더** 창 및 **달력** 창입니다. 것은 적합 하지 않습니다 할를 **달력** 창에는 **탐색기** 창 이제 해당 창 제거 합니다.

- 합니다 `CMFCShellListCtrl` 와 같은 다른 모드에서 파일을 볼 수 **큰 아이콘**를 **작은 아이콘**를 **목록**, 및 **세부 정보**합니다. 이 기능을 구현 하는 응용 프로그램을 업데이트 합니다. 힌트: 참조 [시각적 C++ 샘플](../overview/visual-cpp-samples.md)합니다.

## <a name="see-also"></a>참고자료

[연습](../mfc/walkthroughs-mfc.md)
