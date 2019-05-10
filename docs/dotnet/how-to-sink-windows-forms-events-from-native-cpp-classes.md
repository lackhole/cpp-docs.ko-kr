---
title: '방법: 네이티브에서 Windows Forms 이벤트 싱크 C++ 클래스'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- event handling, managed/native interop
- event handling, sinking .NET in C++
- event handling, .NET/native interop
- event handling, Windows Forms in C++
ms.assetid: 6e30ddee-d058-4c8d-9956-2a43d86f19d5
ms.openlocfilehash: d02bcea4efce03c8fb11650d344468236737cfbd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387268"
---
# <a name="how-to-sink-windows-forms-events-from-native-c-classes"></a>방법: 네이티브에서 Windows Forms 이벤트 싱크 C++ 클래스

네이티브 설정할 수 있습니다. C++ 관리 되는 Windows Forms 컨트롤 또는 MFC 매크로 map 형식 사용 하 여 다른 폼에서 발생 하는 이벤트에서 콜백을 받으려면 클래스입니다. 뷰 및 대화 상자에 이벤트를 싱크하기 컨트롤에 대 한 동일한 작업을 수행 하는 것과 비슷합니다.

이 작업을 수행 하려면을 지정 해야 합니다.

- 연결 프로그램 `OnClick` 제어를 통해 이벤트 처리기 [MAKE_DELEGATE](../mfc/reference/delegate-and-interface-maps.md#make_delegate)합니다.

- 사용 하 여 대리자 맵에 [BEGIN_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#begin_delegate_map)를 [END_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#end_delegate_map), 및 [EVENT_DELEGATE_ENTRY](../mfc/reference/delegate-and-interface-maps.md#event_delegate_entry)합니다.

이 샘플에서 수행한 작업을 계속 [방법: Windows Forms에서 DDX/DDV 데이터 바인딩 수행](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)합니다.

이제 MFC 컨트롤 연결 (`m_MyControl`) 라는 관리 되는 이벤트 처리기 대리자를 사용 하 여 `OnClick` 관리 되는 항목에 대 한 <xref:System.Windows.Forms.Control.Click> 이벤트입니다.

### <a name="to-attach-the-onclick-event-handler"></a>OnClick 이벤트 처리기를 연결 합니다.

1. BOOL CMFC01Dlg::OnInitDialog 구현에 다음 코드를 추가 합니다.

    ```
    m_MyControl.GetControl()->button1->Click += MAKE_DELEGATE( System::EventHandler, OnClick );
    ```

1. CMFC01Dlg 클래스의 선언에 public 섹션에 다음 코드를 추가 합니다: 공용 CDialog 합니다.

    ```
    // delegate map
    BEGIN_DELEGATE_MAP( CMFC01Dlg )
    EVENT_DELEGATE_ENTRY( OnClick, System::Object^, System::EventArgs^ )
    END_DELEGATE_MAP()

    void OnClick( System::Object^ sender, System::EventArgs^ e );
    ```

1. 마지막으로,에 대 한 구현을 추가 `OnClick` CMFC01Dlg.cpp 하려면:

    ```
    void CMFC01Dlg::OnClick(System::Object^ sender, System::EventArgs^ e)
    {
        AfxMessageBox(_T("Button clicked"));
    }
    ```

## <a name="see-also"></a>참고자료

[MAKE_DELEGATE](../mfc/reference/delegate-and-interface-maps.md#make_delegate)<br/>
[BEGIN_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#begin_delegate_map)<br/>
[END_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#end_delegate_map)<br/>
[EVENT_DELEGATE_ENTRY](../mfc/reference/delegate-and-interface-maps.md#event_delegate_entry)
