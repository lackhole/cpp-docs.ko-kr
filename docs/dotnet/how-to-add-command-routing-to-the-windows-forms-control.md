---
title: '방법: 추가 명령 라우팅에 Windows Forms 컨트롤'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- command routing [C++], adding to Windows Forms controls
- Windows Forms controls [C++], command routing
ms.assetid: bf138ece-b463-442a-b0a0-de7063a760c0
ms.openlocfilehash: 8f633cf744314833409a3ffeacf8c850429e099c
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750300"
---
# <a name="how-to-add-command-routing-to-the-windows-forms-control"></a>방법: 추가 명령 라우팅에 Windows Forms 컨트롤

[CWinFormsView](../mfc/reference/cwinformsview-class.md) MFC 명령 (예: 프레임 메뉴 항목 및 도구 모음 단추)를 처리할 수 있도록 사용자 정의 컨트롤을 명령과 업데이트 명령 UI 메시지를 라우팅합니다.

사용자 컨트롤에서 사용 [ICommandTarget::Initialize](../mfc/reference/icommandtarget-interface.md#initialize) 의 명령 원본 개체에 대 한 참조를 저장할 `m_CmdSrc`다음 예제에서와 같이 합니다. 사용할 `ICommandTarget` mfcmifc80.dll에 대 한 참조를 추가 해야 합니다.

`CWinFormsView` 관리 되는 사용자 정의 컨트롤에 전달 하 여 몇 가지 공통 MFC 뷰 알림을 처리 합니다. 이러한 알림을 포함 합니다 [OnInitialUpdate](../mfc/reference/iview-interface.md#oninitialupdate)를 [OnUpdate](../mfc/reference/iview-interface.md#onupdate) 하 고 [OnActivateView](../mfc/reference/iview-interface.md#onactivateview) 메서드.

이 항목에서는 이전에 완료 했다고 가정 [방법: 대화 상자에서 사용자 정의 컨트롤 및 호스트 만들기](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) 고 [방법: 사용자 정의 컨트롤 및 호스트 MDI 뷰 만들기](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)합니다.

### <a name="to-create-the-mfc-host-application"></a>MFC 호스트 응용 프로그램을 만들려면

1. 만든 Windows Forms 컨트롤 라이브러리를 열고 [방법: 대화 상자에서 사용자 정의 컨트롤 및 호스트 만들기](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)합니다.

1. 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 여 수행할 수 있는 mfcmifc80.dll에 대 한 참조를 추가 **솔루션 탐색기**을 선택 하면 **추가**에 **참조**를 찾아 다음 Microsoft Visual Studio 10.0\VC\atlmfc\lib 합니다.

1. UserControl1.Designer.cs를 열고 다음을 추가 문을 사용 하 여:

    ```
    using Microsoft.VisualC.MFC;
    ```

1. 또한 UserControl1.Designer.cs에서에서이 줄을 변경 합니다.

    ```
    partial class UserControl1
    ```

   아래와 같이 변환합니다.

    ```
    partial class UserControl1 : System.Windows.Forms.UserControl, ICommandTarget
    ```

1. 클래스 정의의 첫 번째 줄이 추가 `UserControl1`:

    ```
    private ICommandSource m_CmdSrc;
    ```

1. 다음 메서드 정의를 추가 `UserControl1` (만들겠습니다 MFC 컨트롤의 ID는 다음 단계에서):

    ```
    public void Initialize (ICommandSource cmdSrc)
    {
       m_CmdSrc = cmdSrc;
       // need ID of control in MFC dialog and callback function
       m_CmdSrc.AddCommandHandler(32771, new CommandHandler (singleMenuHandler));
    }

    private void singleMenuHandler (uint cmdUI)
    {
       // User command handler code
       System.Windows.Forms.MessageBox.Show("Custom menu option was clicked.");
    }
    ```

1. 만든 MFC 응용 프로그램을 열고 [방법: 사용자 정의 컨트롤 및 호스트 MDI 뷰 만들기](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)합니다.

1. 호출 하는 메뉴 옵션을 추가 `singleMenuHandler`합니다.

   로 이동 **리소스 뷰** (Ctrl + Shift + E)를 확장 합니다 **메뉴** 폴더를 마우스 두 번 클릭 **IDR_MFC02TYPE**합니다. 메뉴 편집기가 표시 됩니다.

   아래쪽의 메뉴 옵션을 추가 합니다 **보기** 메뉴. 메뉴 옵션에서의 ID를 확인 합니다 **속성** 창입니다. 파일을 저장합니다.

   **솔루션 탐색기**Resource.h 파일을 열고, 방금 추가한 메뉴 옵션에 대 한 ID 값을 복사 및 첫 번째 매개 변수로 해당 값을 붙여 넣습니다. 합니다 `m_CmdSrc.AddCommandHandler` C# 프로젝트의 호출 `Initialize` ( 대체메서드`32771` 필요한 경우).

9. 프로젝트를 빌드하고 실행합니다.

   **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.

   에 **디버그** 메뉴에서 클릭 **디버깅 하지 않고 시작**합니다.

   추가한 메뉴 옵션을 선택 합니다. .Dll의 메서드가 호출 되도록 확인 합니다.

## <a name="see-also"></a>참고자료

[Windows Forms 사용자 정의 컨트롤을 MFC 뷰로 호스팅](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)<br/>
[ICommandSource 인터페이스](../mfc/reference/icommandsource-interface.md)<br/>
[ICommandTarget 인터페이스](../mfc/reference/icommandtarget-interface.md)
