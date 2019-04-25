---
title: '방법: 속성 및 Windows Forms의 메서드 호출 제어'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- method calls, Windows Forms
- calling methods, Windows Forms control
- calling properties, Windows Forms control
- Windows Forms controls [C++], methods
- calling properties
- Windows Forms controls [C++], properties
ms.assetid: 6e647d8a-fdaa-4aa1-b3fe-04f15cff8eb3
ms.openlocfilehash: 61b565839b3f3c24670819fdcf2dde558e3461ac
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152815"
---
# <a name="how-to-call-properties-and-methods-of-the-windows-forms-control"></a>방법: 속성 및 Windows Forms의 메서드 호출 제어

때문에 [CWinFormsView::GetControl](../mfc/reference/cwinformsview-class.md#getcontrol) 에 대 한 포인터를 반환 <xref:System.Windows.Forms.Control?displayProperty=fullName>, 및에 대 한 포인터가 아닌 `WindowsControlLibrary1::UserControl1`, 사용자 컨트롤 형식의 멤버를 추가 하 고에서 초기화 하는 것이 좋습니다 [IView::OnInitialUpdate ](../mfc/reference/iview-interface.md#oninitialupdate). 사용 하 여 속성과 메서드를 호출할 수 있습니다 이제 `m_ViewControl`합니다.

이 항목에서는 이전에 완료 했다고 가정 [방법: 대화 상자에서 사용자 정의 컨트롤 및 호스트 만들기](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) 고 [방법: 사용자 정의 컨트롤 및 호스트 MDI 뷰 만들기](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)합니다.

### <a name="to-create-the-mfc-host-application"></a>MFC 호스트 응용 프로그램을 만들려면

1. 만든 MFC 응용 프로그램을 열고 [방법: 사용자 정의 컨트롤 및 호스트 MDI 뷰 만들기](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)합니다.

1. 공용 재정의 섹션에 다음 줄을 추가 합니다 `CMFC02View` 클래스 MFC02View.h에서 선언 합니다.

   `gcroot<WindowsFormsControlLibrary1::UserControl1 ^> m_ViewControl;`

1. OnInitialupdate에 대 한 재정의 추가 합니다.

   표시 된 **속성** 창 (F4). **클래스 뷰** (CTRL + SHIFT + C) CMFC02View 클래스를 선택 합니다. 에 **속성** 창, 재정의 대 한 아이콘을 선택 합니다. OnInitialUpdate 목록 아래로 Scoll 합니다. 드롭다운 목록 및 선택 목록에서 클릭 \<추가 >. MFC02View.cpp에서. OnInitialUpdate 함수 본문은 다음과 같이 해야 합니다.

    ```
    CWinFormsView::OnInitialUpdate();
    m_ViewControl = safe_cast<WindowsFormsControlLibrary1::UserControl1 ^>(this->GetControl());
    m_ViewControl->textBox1->Text = gcnew System::String("hi");
    ```

1. 프로젝트를 빌드하고 실행합니다.

   **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.

   에 **디버그** 메뉴에서 클릭 **디버깅 하지 않고 시작**합니다.

   텍스트 상자 초기화를 확인 합니다.

## <a name="see-also"></a>참고자료

[Windows Forms 사용자 정의 컨트롤을 MFC 뷰로 호스팅](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)
