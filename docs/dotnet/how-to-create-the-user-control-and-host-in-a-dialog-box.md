---
title: '방법: 대화 상자에서 사용자 정의 컨트롤 및 호스트 만들기'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], hosting a Windows Forms Control
- Windows Forms [C++], MFC support
ms.assetid: 03a53032-2f03-4fa2-b567-031615a26011
ms.openlocfilehash: bdf7e2f4961a16e6538c7bbcc690ef44ba87fcaf
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57751494"
---
# <a name="how-to-create-the-user-control-and-host-in-a-dialog-box"></a>방법: 대화 상자에서 사용자 정의 컨트롤 및 호스트 만들기

이 문서의 단계는 만들려는 대화 상자 기반 가정 ([CDialog 클래스](../mfc/reference/cdialog-class.md)) 수 있지만 Microsoft Foundation 클래스 (MFC) 프로젝트를 추가할 수도 Windows Forms 컨트롤에 대 한 지원을 기존 MFC 대화 상자.

### <a name="to-create-the-net-user-control"></a>.NET 사용자 정의 컨트롤을 만들려면

1. 이라는 Visual C# Windows Forms 컨트롤 라이브러리 프로젝트를 만듭니다 `WindowsFormsControlLibrary1`합니다.

   **파일** 메뉴에서 **새로 만들기** 를 클릭한 다음 **프로젝트**를 클릭합니다. 에 **Visual C#** 폴더 선택 **Windows Forms 컨트롤 라이브러리**합니다.

   수락 합니다 `WindowsFormsControlLibrary1` 를 클릭 하 여 프로젝트 이름 **확인**합니다.

   기본적으로.NET 컨트롤의 이름이 됩니다 `UserControl1`합니다.

1. 자식 컨트롤을 추가할 `UserControl1`합니다.

   에 **도구 상자**오픈 합니다 **모든 Windows Forms** 목록. 끌어서를 **단추** 컨트롤을 `UserControl1` 디자인 화면입니다.

   또한 추가 **텍스트 상자** 컨트롤입니다.

1. **솔루션 탐색기**를 두 번 클릭 **UserControl1.Designer.cs** 를 편집용으로 엽니다. TextBox 및 Button의 선언을 변경 `private` 에 `public`입니다.

1. 프로젝트를 빌드합니다.

   **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.

### <a name="to-create-the-mfc-host-application"></a>MFC 호스트 응용 프로그램을 만들려면

1. MFC 응용 프로그램 프로젝트를 만듭니다.

   **파일** 메뉴에서 **새로 만들기** 를 클릭한 다음 **프로젝트**를 클릭합니다. 에 **Visual c + +** 폴더 선택 **MFC 응용 프로그램**합니다.

   **이름** 상자에 `MFC01`을 입력합니다. 솔루션 설정 변경 **솔루션을 추가할**합니다. **확인**을 클릭합니다.

   에 **MFC 응용 프로그램 마법사**, 응용 프로그램 유형 선택 **대화 상자 기반**입니다. 나머지 기본 설정을 적용 하 고 클릭 **완료**합니다. 이 MFC 대화 상자에 있는 MFC 응용 프로그램을 만듭니다.

1. 자리 표시자 컨트롤을 MFC 대화 상자에 추가 합니다.

   에 **뷰** 메뉴에서 클릭 **리소스 뷰**합니다. **리소스 뷰**를 확장 합니다 **대화 상자** 폴더를 두 번 클릭 `IDD_MFC01_DIALOG`. 대화 상자 리소스에 나타납니다 **리소스 편집기**합니다.

   에 **도구 상자**오픈 합니다 **대화 상자 편집기** 목록. 끌어서를 **정적 텍스트** 대화 상자 리소스를 제어 합니다. 합니다 **정적 텍스트** 컨트롤.NET Windows Forms 컨트롤에 대 한 자리 표시자로 제공 됩니다. Windows Forms 컨트롤의 대략적인 크기를 조정 합니다.

   에 **속성** 창에서를 **ID** 의 **정적 텍스트** 컨트롤을 `IDC_CTRL1` 변경를 **TabStop** 속성을 **True**합니다.

1. 공용 언어 런타임 (CLR) 지원에 대 한 프로젝트를 구성 합니다.

   **솔루션 탐색기**MFC01 프로젝트 노드를 마우스 오른쪽 단추로 클릭 한 다음 클릭 **속성**합니다.

   에 **속성 페이지** 대화 상자의 **구성 속성**를 선택 **일반**합니다. 에 **프로젝트 기본값** 으로 설정 **공용 언어 런타임 지원을** 하 **공용 언어 런타임 지원 (/ clr)** 합니다.

   아래 **구성 속성**, 확장 **C/c + +** 선택 합니다 **일반** 노드. 설정할 **디버그 정보 형식** 하 **프로그램 데이터베이스 (/Zi)** 합니다.

   선택 된 **코드 생성** 노드. 설정 **최소 다시 빌드 가능** 하 **없음 (/ Gm-)** 합니다. 설정할 수도 **기본 런타임 검사** 하 **기본**입니다.

   클릭 **확인** 변경 내용을 적용 합니다.

1. .NET 컨트롤에 대 한 참조를 추가 합니다.

   **솔루션 탐색기**에서 MFC01 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 클릭 **추가**하십시오 **참조**합니다. 에 **속성 페이지**, 클릭 **새 참조 추가**를 선택 **WindowsFormsControlLibrary1** (아래를 **프로젝트** 탭)를 클릭 **확인**합니다. 형식의 대 한 참조를 추가 된 [/FU](../build/reference/fu-name-forced-hash-using-file.md) 프로그램을 컴파일되지 않도록 컴파일러 옵션입니다. 또한 프로그램이 실행 되 고 있도록 \MFC01\ 프로젝트 폴더에 WindowsFormsControlLibrary1.dll의 복사본이 저장 합니다.

1. Stdafx.h에서이 줄을 찾습니다.

    ```
    #endif // _AFX_NO_AFXCMN_SUPPORT
    ```

   위에 다음이 줄을 추가 합니다.

    ```
    #include <afxwinforms.h>   // MFC Windows Forms support
    ```

1. 관리 되는 컨트롤을 만드는 코드를 추가 합니다.

   첫째, 관리 되는 컨트롤을 선언 합니다. MFC01Dlg.h에서 대화 상자 클래스의 선언으로 이동 하 고 다음과 같이 Protected 범위에서 사용자 정의 컨트롤에 대 한 데이터 멤버를 추가 합니다.

    ```
    class CMFC01Dlg : public CDialog
    {
       // ...
       // Data member for the .NET User Control:
       CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_ctrl1;
    ```

   다음으로 관리 되는 컨트롤에 대 한 구현을 제공 합니다. MFC01Dlg.cpp에서 대화 상자에서 재정의할 `CMFC01Dlg::DoDataExchange` MFC 응용 프로그램 마법사에서 생성 된 (없습니다 `CAboutDlg::DoDataExchange`를 동일한 파일에), 관리 되는 컨트롤을 만들고 정적 자리 표시자 IDC_CTRL1과 연결 하려면 다음 코드를 추가 합니다.

    ```
    void CMFC01Dlg::DoDataExchange(CDataExchange* pDX)
    {
       CDialog::DoDataExchange(pDX);
       DDX_ManagedControl(pDX, IDC_CTRL1, m_ctrl1);
    }
    ```

1. 프로젝트를 빌드하고 실행합니다.

   **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **MFC01** 을 클릭 한 다음 **시작 프로젝트로 설정**합니다.

   **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.

   에 **디버그** 메뉴에서 클릭 **디버깅 하지 않고 시작**합니다. MFC 대화 상자에는 Windows Forms 컨트롤을 표시 됩니다.

## <a name="see-also"></a>참고자료

[MFC 대화 상자에서 Windows Form 사용자 정의 컨트롤 호스팅](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)
