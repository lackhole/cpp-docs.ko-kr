---
title: Windows Form 사용자 정의 컨트롤을 MFC 대화 상자로 호스팅
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms [C++], hosting as MFC Dialog
- hosting Windows Forms control [C++]
ms.assetid: 0434a9d7-8b14-48e6-ad69-9ba9a684677a
ms.openlocfilehash: 4c4ee8c8b4570b598ba20b3bd5e1cf4c706ee885
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57740784"
---
# <a name="hosting-a-windows-form-user-control-as-an-mfc-dialog-box"></a>Windows Form 사용자 정의 컨트롤을 MFC 대화 상자로 호스팅

템플릿 클래스를 제공 하는 MFC [CWinFormsDialog](../mfc/reference/cwinformsdialog-class.md) Windows Forms 사용자 정의 컨트롤을 호스팅할 수 있도록 (<xref:System.Windows.Forms.UserControl>) 모달 또는 모덜리스 MFC 대화 상자에서. `CWinFormsDialog` MFC 클래스에서 파생 된 [CDialog](../mfc/reference/cdialog-class.md)이므로 모달 또는 모덜리스 대화 상자를 시작할 수 있습니다.

프로세스는 `CWinFormsDialog` 사용자 정의 컨트롤을 호스트 하는 데 사용 하는에 설명 된 유사 [MFC 대화 상자에서 Windows Form 사용자 정의 컨트롤 호스팅](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)합니다. 그러나 `CWinFormsDialog` 초기화 및 직접 프로그래밍할 수 하지 않아도 되도록 사용자 컨트롤의 호스팅 관리 합니다.

MFC를 사용 하는 Windows Forms을 보여 주는 샘플 응용 프로그램을 참조 하세요 [MFC 및 Windows Forms 통합](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en)합니다.

### <a name="to-create-the-mfc-host-application"></a>MFC 호스트 응용 프로그램을 만들려면

1. MFC 응용 프로그램 프로젝트를 만듭니다.

   에 **파일** 메뉴에서 **새로 만들기**를 클릭 하 고 **프로젝트**합니다. 에 **Visual c + +** 폴더 선택 **MFC 응용 프로그램**합니다.

   에 **이름** 상자에 입력 합니다 `MFC03` 솔루션 설정을 변경 하 고 **솔루션을 추가할**합니다. 클릭 **확인**합니다.

   에 **MFC 응용 프로그램 마법사**에서 모든 기본값을 적용 하 고 클릭 **마침**합니다. 이 다중 문서 인터페이스를 사용 하 여 MFC 응용 프로그램을 만듭니다.

1. 프로젝트를 구성 합니다.

   **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 합니다 **MFC03** 프로젝트 노드를 선택한 **속성**합니다. 합니다 **속성 페이지** 대화 상자가 나타납니다.

   에 **속성 페이지** 대화 상자의 합니다 **구성 속성** 트리 컨트롤 **일반**, 그런 다음를 **프로젝트 기본값**으로 설정 **공용 언어 런타임 지원** 하 **공용 언어 런타임 지원 (/ clr)** 합니다. **확인**을 클릭합니다.

1. .NET 컨트롤에 대 한 참조를 추가 합니다.

   **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 합니다 **MFC03** 선택한 프로젝트 노드 **추가**를 **참조**합니다. 에 **속성 페이지**, 클릭 **새 참조 추가**, WindowsControlLibrary1을 선택 (아래는 **프로젝트** 탭), 클릭 **확인**합니다. 형식의 대 한 참조를 추가 [/FU](../build/reference/fu-name-forced-hash-using-file.md) 컴파일러 옵션은 프로그램을 컴파일되지; WindowsControlLibrary1.dll에 복사 합니다 `MFC03` 프로그램이 실행 되는 프로젝트 디렉터리.

1. 추가 `#include <afxwinforms.h>` stdafx.h에서 기존 끝 `#include` 문입니다.

1. 새 클래스를 서브클래싱하는 추가 `CDialog`합니다.

   프로젝트 이름을 마우스 오른쪽 단추로 클릭 하 고 서브클래싱하는 CHostForWinForm 이라는 MFC 클래스 추가 `CDialog`합니다. 대화 상자 리소스 않아도 되므로 리소스 ID를 삭제할 수 있습니다 (선택 **리소스 뷰**를 확장 합니다 **대화 상자** 폴더 및 delete `IDD_HOSTFORWINFORM` 리소스입니다.  그런 다음 ID에 대 한 참조에서에서 제거 코드 합니다.).

1. 바꿉니다 `CDialog` CHostForWinForm.h 및 CHostForWinForm.cpp 파일에서 `CWinFormsDialog<WindowsControlLibrary1::UserControl1>`합니다.

1. CHostForWinForm 클래스에서 DoModal을 호출 합니다.

   MFC03.cpp에 추가 `#include "HostForWinForm.h"`합니다.

   CMFC03App::InitInstance의 정의에서 return 문의 하기 전에 다음을 추가 합니다.

    ```cpp
    CHostForWinForm m_HostForWinForm;
    m_HostForWinForm.DoModal();
    ```

1. 프로젝트를 빌드하고 실행합니다.

   **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.

   에 **디버그** 메뉴에서 클릭 **디버깅 하지 않고 시작**합니다.

   그런 다음 MFC 응용 프로그램에서 Windows Forms에서 컨트롤의 상태를 모니터링 하는 코드를 추가 합니다.

1. OnInitDialog에 대 한 처리기를 추가 합니다.

   표시 된 **속성** 창 (F4). **클래스 뷰**에서 CHostForWinForm을 선택 합니다. 에 **속성** 창에서 선택 재정의 OnInitDialog에 대 한 행의 왼쪽 열에서 클릭 및 선택 \< 추가 >. 그러면 CHostForWinForm.h에 다음 줄 추가:

    ```cpp
    virtual BOOL OnInitDialog();
    ```

1. 다음과 같이 CHostForWinForm.cpp에서 OnInitDialog를 정의 합니다.

    ```cpp
    BOOL CHostForWinForm::OnInitDialog() {
       CWinFormsDialog<WindowsControlLibrary1::UserControl1>::OnInitDialog();
       GetControl()->button1->Click += MAKE_DELEGATE(System::EventHandler, OnButton1);
       return TRUE;
    }
    ```

1. 다음 OnButton1 처리기를 추가 합니다. CHostForWinForm.h에서 CHostForWinForm 클래스의 public 섹션에 다음 줄을 추가 합니다.

    ```cpp
    virtual void OnButton1( System::Object^ sender, System::EventArgs^ e );

    BEGIN_DELEGATE_MAP( CHostForWinForm )
       EVENT_DELEGATE_ENTRY( OnButton1, System::Object^, System::EventArgs^ );
    END_DELEGATE_MAP()
    ```

   CHostForWinForm.cpp에이 정의 추가 합니다.

    ```cpp
    void CHostForWinForm::OnButton1( System::Object^ sender, System::EventArgs^ e )
    {
       System::Windows::Forms::MessageBox::Show("test");
    }
    ```

1. 프로젝트를 빌드하고 실행합니다. Windows 폼에 있는 단추를 클릭 하면 MFC 응용 프로그램에서 코드가 실행 됩니다.

    다음 Windows 폼에 텍스트 상자에 값을 MFC 코드에서 표시 하는 코드를 추가 합니다.

1. CHostForWinForm.h에서 CHostForWinForm 클래스의 public 섹션에 다음 선언을 추가 합니다.

    ```cpp
    CString m_sEditBoxOnWinForm;
    ```

1. CHostForWinForm.cpp의 dodataexchange 정의에서 함수의 끝에 다음 세 줄을 추가 합니다.

    ```cpp
    if (pDX->m_bSaveAndValidate)
       m_sEditBoxOnWinForm = CString( GetControl()->textBox1->Text);
    else
       GetControl()->textBox1->Text = gcnew System::String(m_sEditBoxOnWinForm);
    ```

1. CHostForWinForm.cpp의 onbutton1 정의에서 함수의 끝에 다음 세 줄을 추가 합니다.

    ```cpp
    this->UpdateData(TRUE);
    System::String ^ z = gcnew System::String(m_sEditBoxOnWinForm);
    System::Windows::Forms::MessageBox::Show(z);
    ```

1. 프로젝트를 빌드하고 실행합니다.

## <a name="see-also"></a>참고자료

<xref:System.Windows.Forms.UserControl?displayProperty=fullName>
[MFC에서 Windows Form 사용자 정의 컨트롤 사용](../dotnet/using-a-windows-form-user-control-in-mfc.md)
