---
title: '방법: 사용자 정의 컨트롤 및 호스트 MDI 뷰 만들기'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms Controls
- Windows Forms [C++], MFC support
ms.assetid: 625b5821-f923-4701-aca0-c1a4ceca4f63
ms.openlocfilehash: 7d535fce47be5504f6f521cda1267344206287da
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387437"
---
# <a name="how-to-create-the-user-control-and-host-mdi-view"></a>방법: 사용자 정의 컨트롤 및 호스트 MDI 뷰 만들기

다음 단계에는.NET Framework 사용자 정의 컨트롤을 만들고 컨트롤 클래스 라이브러리 (특히 Windows 컨트롤 라이브러리 프로젝트의 경우) 사용자 정의 컨트롤을 작성 한 다음 프로젝트를 어셈블리로 컴파일합니다 하는 방법을 보여 줍니다. 컨트롤에서 파생 된 클래스를 사용 하는 MFC 응용 프로그램에서 사용할 수 있습니다 [CView 클래스](../mfc/reference/cview-class.md) 하 고 [CWinFormsView 클래스](../mfc/reference/cwinformsview-class.md)합니다.

Windows Forms 사용자 정의 컨트롤을 만들고 컨트롤 클래스 라이브러리를 작성 하는 방법에 대 한 정보를 참조 하세요. [방법: 사용자 컨트롤 작성](/dotnet/framework/winforms/controls/how-to-author-composite-controls)합니다.

> [!NOTE]
>  일부 경우에는 타사 Grid 컨트롤 같은 Windows Forms 컨트롤, 동작할 수 있습니다 하지 안정적으로 MFC 응용 프로그램에서 호스트 되는 경우. 권장된 해결 방법을 MFC 응용 프로그램에 Windows Forms 사용자 정의 컨트롤을 배치 하 고 사용자 정의 컨트롤 내에서 타사 표 형태 컨트롤을 배치 하는 것입니다.

이 절차에 절차에 따라 WindowsFormsControlLibrary1 이라는 Windows Forms 컨트롤 라이브러리 프로젝트를 만들었다고 가정 [방법: 대화 상자에서 사용자 정의 컨트롤 및 호스트 만들기](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)합니다.

### <a name="to-create-the-mfc-host-application"></a>MFC 호스트 응용 프로그램을 만들려면

1. MFC 응용 프로그램 프로젝트를 만듭니다.

   에 **파일** 메뉴에서 **새로 만들기**를 클릭 하 고 **프로젝트**합니다. 에 **시각적 C++**  폴더를 선택 **MFC 응용 프로그램**합니다.

   에 **이름** 상자에 입력 합니다 `MFC02` 변경 합니다 **솔루션** 로 설정 **솔루션에 추가**. **확인**을 클릭합니다.

   에 **MFC 응용 프로그램 마법사**에서 모든 기본값을 적용 하 고 클릭 **마침**합니다. 이 다중 문서 인터페이스를 사용 하 여 MFC 응용 프로그램을 만듭니다.

1. 공용 언어 런타임 (CLR) 지원에 대 한 프로젝트를 구성 합니다.

   **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 합니다 `MFC01` 프로젝트 노드를 선택한 **속성** 상황에 맞는 메뉴에서. 합니다 **속성 페이지** 대화 상자가 나타납니다.

   아래 **구성 속성**를 선택 **일반**합니다. 아래는 **프로젝트 기본값** 으로 설정 **공용 언어 런타임 지원을** 하 **공용 언어 런타임 지원 (/ clr)** 합니다.

   아래 **구성 속성**, 확장 **C /C++**  을 클릭 합니다 **일반** 노드. 설정할 **디버그 정보 형식** 하 **프로그램 데이터베이스 (/Zi)** 합니다.

   클릭 합니다 **코드 생성** 노드. 설정 **최소 다시 빌드 가능** 하 **없음 (/ Gm-)** 합니다. 설정할 수도 **기본 런타임 검사** 하 **기본**입니다.

   클릭 **확인** 변경 내용을 적용 하려면.

1. Stdafx.h에서 다음 줄을 추가 합니다.

    ```
    #using <System.Windows.Forms.dll>
    ```

1. .NET 컨트롤에 대 한 참조를 추가 합니다.

   **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 합니다 `MFC02` 프로젝트 노드를 선택 **추가**를 **참조**합니다. 에 **속성 페이지**, 클릭 **새 참조 추가**, WindowsFormsControlLibrary1 선택 (아래는 **프로젝트** 탭), 클릭 **확인** . 형식의 대 한 참조를 추가 [/FU](../build/reference/fu-name-forced-hash-using-file.md) 컴파일러 옵션은 프로그램을 컴파일되지;에 WindowsFormsControlLibrary1.dll 복사를 `MFC02` 디렉터리를 프로젝트에 프로그램이 실행 됩니다.

1. Stdafx.h에서이 줄을 찾습니다.

    ```
    #endif // _AFX_NO_AFXCMN_SUPPORT
    ```

   위에 다음이 줄을 추가 합니다.

    ```
    #include <afxwinforms.h>   // MFC Windows Forms support
    ```

1. 상속 되도록 뷰 클래스를 수정 [CWinFormsView](../mfc/reference/cwinformsview-class.md)합니다.

   MFC02View.h에서 바꿉니다 [CView](../mfc/reference/cview-class.md) 사용 하 여 [CWinFormsView](../mfc/reference/cwinformsview-class.md) 코드를 다음과 같이 표시 되도록 합니다.

    ```
    class CMFC02View : public CWinFormsView
    {
    };
    ```

   MDI 응용 프로그램에 추가 뷰를 추가 하려면를 호출 해야 합니다 [CWinApp::AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate) 만든 각 보기에 대 한 합니다.

1. 아래에 표시 된 생성자를 사용 하 여 기존의 빈 생성자를 바꾸고 IMPLEMENT_DYNCREATE 매크로 및 메시지 맵에서 CView를 cwinformsview로 변경 MFC02View.cpp 파일을 수정 합니다.

    ```
    IMPLEMENT_DYNCREATE(CMFC02View, CWinFormsView)

    CMFC02View::CMFC02View(): CWinFormsView(WindowsFormsControlLibrary1::UserControl1::typeid)
    {
    }
    BEGIN_MESSAGE_MAP(CMFC02View, CWinFormsView)
    //leave existing body as is
    END_MESSAGE_MAP()
    ```

1. 프로젝트를 빌드하고 실행합니다.

   **솔루션 탐색기**MFC02를 마우스 오른쪽 단추로 클릭 하 고 선택 **시작 프로젝트로 설정**합니다.

   **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.

   에 **디버그** 메뉴에서 클릭 **디버깅 하지 않고 시작**합니다.

## <a name="see-also"></a>참고자료

[Windows Forms 사용자 정의 컨트롤을 MFC 뷰로 호스팅](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)
