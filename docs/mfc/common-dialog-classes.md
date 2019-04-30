---
title: 일반 대화 상자 클래스
ms.date: 11/04/2016
helpviewer_keywords:
- dialog classes [MFC]
- dialog boxes [MFC], Windows common dialogs
- common dialog boxes [MFC], common dialog classes
- common dialog classes [MFC]
- MFC dialog boxes [MFC], Windows common dialogs
- Windows common dialogs [MFC]
- dialog classes [MFC], common
- common dialog boxes [MFC]
ms.assetid: 5c4f6443-896c-4b05-a7df-8169fdadc71d
ms.openlocfilehash: 5efd885421d8c73c191e2a5603f37d1df85a5168
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388529"
---
# <a name="common-dialog-classes"></a>일반 대화 상자 클래스

클래스 외에도 [CDialog](../mfc/reference/cdialog-class.md)에서 파생 된 여러 클래스를 제공 하는 MFC `CDialog` 다음 표에 나와 있는 것 처럼 자주 사용 되는 대화 상자를 캡슐화 하는 합니다. 캡슐화 된 대화 상자 "공용 대화 상자의" 이라고 하며 Windows 공용 대화 라이브러리 (COMMDLG에 속함. DLL)입니다. Windows 버전 3.1 이상 포함 된 일반 대화 상자 대화 상자 템플릿 리소스와 이러한 클래스에 대 한 코드는 Windows에서 제공 됩니다.

### <a name="common-dialog-classes"></a>일반 대화 상자 클래스

|파생 된 대화 상자 클래스|용도|
|--------------------------|-------------|
|[CColorDialog](../mfc/reference/ccolordialog-class.md)|색을 선택 하는 사용자를 수 있습니다.|
|[CFileDialog](../mfc/reference/cfiledialog-class.md)|사용자를 열거나 저장할 파일 이름을 선택할 수 있습니다.|
|[CFindReplaceDialog](../mfc/reference/cfindreplacedialog-class.md)|사용자를 시작 찾기 또는 바꾸기 작업을 텍스트 파일로 수 있습니다.|
|[CFontDialog](../mfc/reference/cfontdialog-class.md)|글꼴을 지정 하는 사용자 수 있습니다.|
|[CPrintDialog](../mfc/reference/cprintdialog-class.md)|사용자를 인쇄 작업에 대 한 정보를 지정할 수 있습니다.|
|[CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)|Windows 인쇄 속성 시트입니다.|

일반 대화 상자 클래스에 대 한 자세한 내용은 개별 클래스 이름을 참조 합니다 *MFC 참조*합니다. MFC는 또한 여러 OLE에 사용 되는 표준 대화 상자 클래스를 제공 합니다. 이러한 클래스에 대 한 자세한 내용은 기본 클래스를 참조 하세요 [COleDialog](../mfc/reference/coledialog-class.md)를 *MFC 참조*합니다.

MFC의 다른 세 가지 클래스 대화 상자와 비슷한 특징을 갖습니다. 클래스에 대 한 자세한 [CFormView](../mfc/reference/cformview-class.md), [CRecordView](../mfc/reference/crecordview-class.md), 및 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)의 클래스를 참조 합니다 *MFC 참조*합니다. 클래스에 대 한 자세한 [CDialogBar](../mfc/reference/cdialogbar-class.md)를 참조 하십시오 [대화 상자 모음](../mfc/dialog-bars.md)합니다.

## <a name="see-also"></a>참고자료

[대화 상자](../mfc/dialog-boxes.md)<br/>
[대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[OLE의 대화 상자](../mfc/dialog-boxes-in-ole.md)
