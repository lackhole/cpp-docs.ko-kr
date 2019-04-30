---
title: MFC 대화 상자에서 Windows Form 사용자 정의 컨트롤 호스팅
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- hosting Windows Forms control [C++]
- Windows Forms [C++], MFC support
ms.assetid: 9f66ee52-b7cb-4ffd-8306-392a5da990d8
ms.openlocfilehash: 56cf00da71fe6c47e39de2a8fc06df572a301a61
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222990"
---
# <a name="hosting-a-windows-form-user-control-in-an-mfc-dialog-box"></a>MFC 대화 상자에서 Windows Form 사용자 정의 컨트롤 호스팅

MFC ActiveX 컨트롤의 특수 한 종류는 Windows Forms 컨트롤을 호스트 하 고 ActiveX 인터페이스, 속성 및 메서드를 사용 하 여 컨트롤을 사용 하 여 통신을 <xref:System.Windows.Forms.Control> 클래스입니다. 컨트롤에 적용할.NET Framework 속성 및 메서드를 사용 하는 것이 좋습니다.

MFC를 사용 하는 Windows Forms을 보여 주는 샘플 응용 프로그램을 참조 하세요 [MFC 및 Windows Forms 통합](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en)합니다.

> [!NOTE]
>  현재 릴리스에서 `CDialogBar` 개체는 Windows Forms 컨트롤을 호스팅할 수 없습니다.

## <a name="in-this-section"></a>섹션 내용

[방법: 대화 상자에 사용자 정의 컨트롤 및 호스트 만들기](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)

[방법: 바인딩 Windows Forms에서 DDX/DDV 데이터](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)

[방법: 네이티브 C++ 클래스에서 Windows Forms 이벤트 싱크](../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)

## <a name="reference"></a>참조

[CWinFormsControl 클래스](../mfc/reference/cwinformscontrol-class.md) &#124; [CDialog 클래스](../mfc/reference/cdialog-class.md) &#124; [CWnd 클래스](../mfc/reference/cwnd-class.md)&#124; <xref:System.Windows.Forms.Control>

## <a name="see-also"></a>참고자료

[MFC에서 Windows Form 사용자 정의 컨트롤 사용](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
[Windows Forms/MFC 프로그래밍의 차이점](../dotnet/windows-forms-mfc-programming-differences.md)<br/>
[Windows Forms 사용자 정의 컨트롤을 MFC 뷰로 호스팅](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)<br/>
[Windows Form 사용자 정의 컨트롤을 MFC 대화 상자로 호스팅](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)
