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
ms.openlocfilehash: d11d0978763d9599b0471a8e994f15a267f7cb8f
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685556"
---
# <a name="common-dialog-classes"></a>일반 대화 상자 클래스

클래스 [CDialog](../mfc/reference/cdialog-class.md)외에 MFC는 다음 표와 같이 일반적으로 사용 되는 대화 상자를 캡슐화 하는 `CDialog`에서 파생 된 여러 클래스를 제공 합니다. 캡슐화 된 대화 상자는 "일반 대화 상자" 라고 하며 Windows 공용 대화 상자 라이브러리 (주석 대화 상자)의 일부입니다. DLL). 이러한 클래스에 대 한 대화 상자 템플릿 리소스 및 코드는 Windows 버전 3.1 이상에 포함 된 Windows 공용 대화 상자에 제공 됩니다.

### <a name="common-dialog-classes"></a>일반 대화 상자 클래스

|파생 된 대화 상자 클래스|용도|
|--------------------------|-------------|
|[CColorDialog](../mfc/reference/ccolordialog-class.md)|사용자가 색을 선택할 수 있습니다.|
|[CFileDialog](../mfc/reference/cfiledialog-class.md)|사용자가 열거나 저장할 파일 이름을 선택할 수 있습니다.|
|[CFindReplaceDialog](../mfc/reference/cfindreplacedialog-class.md)|사용자가 텍스트 파일에서 찾기 또는 바꾸기 작업을 시작할 수 있습니다.|
|[CFontDialog](../mfc/reference/cfontdialog-class.md)|사용자가 글꼴을 지정할 수 있습니다.|
|[CPrintDialog](../mfc/reference/cprintdialog-class.md)|사용자가 인쇄 작업에 대 한 정보를 지정할 수 있습니다.|
|[CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)|Windows 인쇄 속성 시트입니다.|

일반 대화 상자 클래스에 대 한 자세한 내용은 *MFC 참조*에서 개별 클래스 이름을 참조 하세요. 또한 MFC는 OLE에 사용 되는 여러 가지 표준 대화 상자 클래스를 제공 합니다. 이러한 클래스에 대 한 자세한 내용은 *MFC 참조*에서 기본 클래스인 [coledialog](../mfc/reference/coledialog-class.md)를 참조 하세요.

MFC의 세 가지 다른 클래스에는 대화 상자와 같은 특징이 있습니다. [CFormView](../mfc/reference/cformview-class.md), [CRecordView](../mfc/reference/crecordview-class.md)및 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)클래스에 대 한 자세한 내용은 *MFC 참조*의 클래스를 참조 하세요. [CDialogBar](../mfc/reference/cdialogbar-class.md)클래스에 대 한 자세한 내용은 [대화 상자 모음](../mfc/dialog-bars.md)을 참조 하세요.

## <a name="see-also"></a>참조

[대화 상자](../mfc/dialog-boxes.md)<br/>
[MFC에서 대화 상자 작업](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[OLE의 대화 상자](../mfc/dialog-boxes-in-ole.md)
