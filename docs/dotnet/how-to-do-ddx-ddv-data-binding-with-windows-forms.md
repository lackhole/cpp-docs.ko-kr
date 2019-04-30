---
title: '방법: Windows Forms 바인딩 DDX-DDV 데이터'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], hosting a Windows Forms Control
- Windows Forms [C++], MFC support
ms.assetid: b2957370-cf1f-4779-94ac-228cd393686c
ms.openlocfilehash: 558c763fd18cd1569ff23435bf6156b3117f117d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387320"
---
# <a name="how-to-do-ddxddv-data-binding-with-windows-forms"></a>방법: 바인딩 Windows Forms에서 DDX/DDV 데이터

[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol) 호출 [CWinFormsControl::CreateManagedControl](../mfc/reference/cwinformscontrol-class.md#createmanagedcontrol) 리소스 컨트롤 id입니다. 일치 하는 컨트롤을 만들려면 사용 하는 경우 `DDX_ManagedControl` 에 대 한는 `CWinFormsControl` 컨트롤 (마법사에서 생성 된 코드에서)를 호출 하지 않아야 `CreateManagedControl` 동일한 컨트롤에 대 한 명시적으로 합니다.

호출 `DDX_ManagedControl` 에 [CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) 리소스 Id에서에서 컨트롤을 만들려고 합니다. 데이터 교환에 대 한 Windows Forms 컨트롤에서 DDX/DDV 함수를 사용할 필요가 없습니다. 대신 관리 되는 컨트롤의 속성에 액세스 하는 코드를 배치할 수 있습니다는 `DoDataExchange` 다음 예제와 같이 대화 상자 (또는 뷰) 클래스의 메서드.

다음 예제에서는 네이티브 바인딩하는 방법 C++ .NET 사용자 정의 컨트롤 문자열입니다.

## <a name="example"></a>예제

다음은 MFC 문자열 DDX/DDV 데이터 바인딩 예가 `m_str` 사용 하 여 사용자 정의 `NameText` .NET 사용자 컨트롤의 속성입니다.

컨트롤을 만들 때 [CDialog::OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) 호출 `CMyDlg::DoDataExchange` 처음으로 모든 코드를 참조 하는 `m_UserControl` 뒤에 야 합니다 `DDX_ManagedControl` 호출 합니다.

만든 MFC01 응용 프로그램에서이 코드를 구현할 수 있습니다 [방법: 대화 상자에서 사용자 정의 컨트롤 및 호스트 만들기](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)합니다.

CMFC01Dlg의 선언에 다음 코드를 넣습니다.

```
class CMFC01Dlg : public CDialog
{
   CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_MyControl;
   CString m_str;
};
```

## <a name="example"></a>예제

CMFC01Dlg의 구현에서 다음 코드를 넣습니다.

```
void CMFC01Dlg::DoDataExchange(CDataExchange* pDX)
{
   CDialog::DoDataExchange(pDX);
   DDX_ManagedControl(pDX, IDC_CTRL1, m_MyControl);

   if (pDX->m_bSaveAndValidate) {
      m_str = m_MyControl->textBox1->Text;
   } else
   {
      m_MyControl->textBox1->Text = gcnew System::String(m_str);
   }
}
```

## <a name="example"></a>예제

이제 확인 단추 클릭에 대 한 처리기 메서드를 추가 합니다. 클릭 합니다 **리소스 뷰** 탭 합니다. 리소스 뷰를 두 번 클릭 `IDD_MFC01_DIALOG`합니다. 대화 상자 리소스에는 리소스 편집기에 나타납니다. 다음 두 번 확인 단추 클릭...

다음과 같이 처리기를 정의 합니다.

```
void CMFC01Dlg::OnBnClickedOk()
{
   AfxMessageBox(CString(m_MyControl.GetControl()->textBox1->Text));
   OnOK();
}
```

## <a name="example"></a>예제

고 BOOL CMFC01Dlg::OnInitDialog() 구현에 다음 줄을 추가 합니다.

```
m_MyControl.GetControl()->textBox1->Text = "hello";
```

이제 작성 하 고 응용 프로그램을 실행할 수 있습니다. 텍스트 상자에 텍스트 응용 프로그램을 닫으면 팝업 메시지 상자에 표시를 확인 합니다.

## <a name="see-also"></a>참고자료

[CWinFormsControl 클래스](../mfc/reference/cwinformscontrol-class.md)<br/>
[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol)<br/>
[CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange)
