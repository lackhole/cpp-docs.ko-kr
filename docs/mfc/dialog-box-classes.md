---
title: 대화 상자 클래스
ms.date: 11/04/2016
f1_keywords:
- vc.classes.dialog
helpviewer_keywords:
- property sheet classes
- dialog box classes
- OLE common dialog classes
- common dialog classes [MFC]
- tab dialog boxes
ms.assetid: db75da23-4eff-4c6c-beae-79cf046fbce9
ms.openlocfilehash: 5747e4450816b803f97ad5ff6338b9e01ad41bca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394613"
---
# <a name="dialog-box-classes"></a>대화 상자 클래스

클래스 `CDialog` 및 해당 파생된 클래스 대화 상자 기능을 캡슐화 합니다. 대화 상자는 특수 한 유형의 창 이므로 `CDialog` 에서 파생 된 `CWnd`합니다. 대화 상자 클래스에서 파생 `CDialog` 또는 하나 사용 하 여 열거나 저장 하는 파일, 인쇄, 글꼴 또는 색을 선택 하는 등의 표준 대화 상자에 대 한 일반 대화 상자 클래스의 검색 및 바꾸기 작업을 시작 하거나 수행 하는 다양 한 OLE 관련 작업입니다.

[CDialog](../mfc/reference/cdialog-class.md)<br/>
모달 및 모덜리스 모든 대화 상자에 대 한 기본 클래스입니다.

[CDataExchange](../mfc/reference/cdataexchange-class.md)<br/>
대화 상자 데이터 교환 및 유효성 검사 정보를 제공합니다.

## <a name="common-dialogs"></a>일반 대화 상자

이러한 대화 상자 클래스는 Windows 일반 대화 상자를 캡슐화합니다. 복잡 한 대화 상자 사용 하기 쉬운 구현을 제공 합니다.

[CCommonDialog](../mfc/reference/ccommondialog-class.md)<br/>
모든 공용 대화 상자에 대 한 기본 클래스입니다.

[CFileDialog](../mfc/reference/cfiledialog-class.md)<br/>
열거나 파일을 저장 하는 표준 대화 상자를 제공 합니다.

[CColorDialog](../mfc/reference/ccolordialog-class.md)<br/>
색을 선택 하기 위한 표준 대화 상자를 제공 합니다.

[CFontDialog](../mfc/reference/cfontdialog-class.md)<br/>
글꼴 선택 하기 위한 표준 대화 상자를 제공 합니다.

[CFindReplaceDialog](../mfc/reference/cfindreplacedialog-class.md)<br/>
검색 및 바꾸기 작업에 대 한 표준 대화 상자를 제공합니다.

[CPrintDialog](../mfc/reference/cprintdialog-class.md)<br/>
파일 인쇄를 위한 표준 대화 상자를 제공 합니다.

[CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)<br/>
Windows 인쇄 속성 시트를 제공합니다.

[CPageSetupDialog](../mfc/reference/cpagesetupdialog-class.md)<br/>
Windows 공용 페이지 설정 대화 상자에서 설정 및 인쇄 여백을 수정에 대 한 추가 지원으로 제공 하는 서비스를 캡슐화 합니다.

## <a name="ole-common-dialogs"></a>OLE 일반 대화 상자

OLE는 Windows에 몇 가지 일반적인 대화 상자를 추가합니다. 이러한 클래스는 OLE 일반 대화 상자를 캡슐화합니다.

[COleDialog](../mfc/reference/coledialog-class.md)<br/>
모든 OLE 대화 상자에 대 한 일반적인 구현을 포함 하는 프레임 워크에서 사용 합니다. 사용자 인터페이스 범주에 있는 모든 대화 상자 클래스는이 기본 클래스에서 파생 됩니다. `COleDialog` 직접 사용할 수 없습니다.

[COleInsertDialog](../mfc/reference/coleinsertdialog-class.md)<br/>
연결 된 새 OLE를 삽입 하거나 항목을 포함 하면 표준 사용자 인터페이스 개체 삽입 대화 상자를 표시 합니다.

[COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md)<br/>
편집 하 여 붙여넣기 명령 구현에 대 한 표준 사용자 인터페이스를 선택 하 여 붙여넣기 대화 상자를 표시 합니다.

[COleLinksDialog](../mfc/reference/colelinksdialog-class.md)<br/>
연결 된 항목에 대 한 정보를 수정 하기 위한 표준 사용자 인터페이스를 링크 편집 대화 상자를 표시 합니다.

[COleChangeIconDialog](../mfc/reference/colechangeicondialog-class.md)<br/>
아이콘 변경 대화 상자, 포함 된 OLE와 사용 하 여 연결 된 아이콘을 변경 하거나 링크 된 항목에 대 한 표준 사용자 인터페이스를 표시 합니다.

[COleConvertDialog](../mfc/reference/coleconvertdialog-class.md)<br/>
변환 대화 상자 OLE 항목을 다른 형식 간에 변환 하는 것에 대 한 표준 사용자 인터페이스를 표시 합니다.

[COlePropertiesDialog](../mfc/reference/colepropertiesdialog-class.md)<br/>
Windows 공용 OLE 속성 대화 상자를 캡슐화합니다. 일반 OLE 속성 대화 상자 표시 Windows 표준에 부합 하는 방식에서 OLE 문서 항목의 속성을 수정 하는 쉬운 방법을 제공 합니다.

[COleUpdateDialog](../mfc/reference/coleupdatedialog-class.md)<br/>
문서에서 모든 링크를 업데이트 하기 위한 표준 사용자 인터페이스 업데이트 대화 상자를 표시 합니다. 대화 상자를 표시 하려면 얼마나 근접 업데이트 절차가 완료 진행률 표시기를 포함 합니다.

[COleChangeSourceDialog](../mfc/reference/colechangesourcedialog-class.md)<br/>
링크의 원본 또는 대상 변경에 대 한 표준 사용자 인터페이스 소스 변경 대화 상자를 표시 합니다.

[COleBusyDialog](../mfc/reference/colebusydialog-class.md)<br/>
서버 작업 중이 고 서버가 응답 하지 대화 상자를 사용 중인 응용 프로그램에 대 한 호출을 처리 하기 위한 표준 사용자 인터페이스를 표시 합니다. 일반적으로 자동으로 표시 합니다 [COleMessageFilter](../mfc/reference/colemessagefilter-class.md) 구현 합니다.

## <a name="property-sheet-classes"></a>속성 시트 클래스

속성 시트 클래스 속성 시트를 라고도 탭된 대화 상자를 사용 하도록 응용 프로그램을 허용 합니다. 속성 시트는 많은 수의 단일 대화 상자에서 컨트롤을 구성 하는 효율적인 방법입니다.

[CPropertyPage](../mfc/reference/cpropertypage-class.md)<br/>
속성 시트 내의 개별 페이지를 제공합니다. 클래스를 파생 `CPropertyPage` 속성 시트에 추가할 각 페이지에 대 한 합니다.

[CPropertySheet](../mfc/reference/cpropertysheet-class.md)<br/>
여러 속성 페이지에 대 한 프레임을 제공 합니다. 속성 시트 클래스를 파생 `CPropertySheet` 에 속성 시트를 신속 하 게 구현 합니다.

[COlePropertyPage](../mfc/reference/colepropertypage-class.md)<br/>
대화 상자에 유사한 그래픽 인터페이스에서 제어 OLE의 속성을 표시 합니다.

## <a name="html-based-dialog-classes"></a>HTML 기반 대화 상자 클래스

[CDHtmlDialog](../mfc/reference/cdhtmldialog-class.md)<br/>
대화 상자를 사용 하지 않고 HTML 리소스를 사용 하 여 해당 사용자 인터페이스를 구현 하는 대화 상자를 만들려면 사용 합니다.

[CMultiPageDHtmlDialog](../mfc/reference/cmultipagedhtmldialog-class.md)<br/>
여러 HTML 페이지를 순차적으로 표시 하 고 각 페이지의 이벤트를 처리 합니다.

## <a name="related-classes"></a>관련된 클래스

이러한 클래스 대화 상자를 본질적으로 없지만 대화 상자 템플릿을 사용 하 여 대화 상자의 동작에 많은 수 있어야 합니다.

[CDialogBar](../mfc/reference/cdialogbar-class.md)<br/>
대화 상자 템플릿을 기반으로 하는 컨트롤 막대입니다.

[CFormView](../mfc/reference/cformview-class.md)<br/>
레이아웃을 대화 상자 템플릿에 정의 된 스크롤 보기입니다. 클래스를 파생 `CFormView` 대화 상자 템플릿을 기반으로 사용자 인터페이스를 구현 합니다.

[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)<br/>
양식을 제공 데이터 액세스 개체 (DAO) 레코드 집합 개체에 직접 연결 하는 보기입니다. 모든 폼 보기와 같은 `CDaoRecordView` 대화 상자 템플릿을 기반으로 합니다.

[CRecordView](../mfc/reference/crecordview-class.md)<br/>
양식을 제공 개방형 데이터베이스 연결 (ODBC) 레코드 집합 개체에 직접 연결 하는 보기입니다. 모든 폼 보기와 같은 `CRecordView` 대화 상자 템플릿을 기반으로 합니다.

[CPrintInfo](../mfc/reference/cprintinfo-structure.md)<br/>
인쇄 또는 인쇄 미리 보기 작업에 대 한 정보를 포함 하는 구조체입니다. 인쇄 아키텍처를 사용한 [CView](../mfc/reference/cview-class.md)합니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../mfc/class-library-overview.md)
