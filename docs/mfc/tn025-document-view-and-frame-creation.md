---
title: 'TN025: 문서, 뷰 및 프레임 만들기'
ms.date: 11/04/2016
f1_keywords:
- vc.creation
helpviewer_keywords:
- documents [MFC], view and frame creation
- TN025
ms.assetid: 09254d72-6e1d-43db-80e9-693887dbeda2
ms.openlocfilehash: 4958e7c4ca2c3cf9eed6420d72d0399fa112098d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62305998"
---
# <a name="tn025-document-view-and-frame-creation"></a>TN025: 문서, 뷰 및 프레임 만들기

> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 노트에서는 WinApps, DocTemplates, 문서, 프레임 및 뷰의 생성 및 소유권 문제에 대해 설명합니다.

## <a name="winapp"></a>WinApp

시스템에는 하나의 `CWinApp` 개체가 있습니다.

이 개체는 프레임워크의 내부 `WinMain` 구현에 의해 정적으로 생성되고 초기화됩니다. 파생 되어야 합니다 `CWinApp` 유용한 작업을 수행 하려면 (예외: MFC 확장명 Dll 사용 해야 합니다는 `CWinApp` 인스턴스-초기화 이루어집니다 `DllMain` 대신).

하나의 `CWinApp` 개체는 문서 템플릿 목록을 소유합니다(`CPtrList`). 응용 프로그램당 하나 이상의 문서 템플릿이 있습니다. DocTemplates는 일반적으로 `CWinApp::InitInstance`에 있는 리소스 파일(즉, 문자열 배열)에서 로드됩니다.

```
pTemplate = new CDocTemplate(IDR_MYDOCUMENT, ...);

AddDocTemplate(pTemplate);
```

하나의 `CWinApp` 개체는 응용 프로그램에서 모든 프레임 창을 소유합니다. 응용 프로그램에 대 한 주 프레임 창에 저장 되어야 합니다 `CWinApp::m_pMainWnd`; 설정 하는 일반적으로 *m_pMainWnd* 에 `InitInstance` AppWizard를 사용 하지 않을 경우 구현 합니다. SDI(단일 문서 인터페이스)의 경우 기본 응용 프로그램 프레임 창뿐만 아니라 유일한 문서 프레임 창으로 작동하는 하나의 `CFrameWnd`입니다. MDI(다중 문서 인터페이스)의 경우에는 모든 자식 `CMDIFrameWnd`를 포함하는 기본 응용 프로그램 프레임 창으로 작동하는 MDI 프레임(`CFrameWnd` 클래스)입니다. 각 자식 창은 `CMDIChildWnd`(`CFrameWnd`에서 파생) 클래스에 속하며 잠재적으로 여러 문서 프레임 창 중 하나로 작동합니다.

## <a name="doctemplates"></a>DocTemplates

`CDocTemplate`는 문서의 생성자 및 관리자입니다. 이 템플릿은 생성되는 문서를 소유합니다. 응용 프로그램에 아래에 설명된 리소스 기반 접근 방법이 사용될 경우 `CDocTemplate`에서 파생될 필요가 없습니다.

SDI 응용 프로그램의 경우 `CSingleDocTemplate` 클래스는 하나의 열린 문서를 추적합니다. MDI 응용 프로그램의 경우 `CMultiDocTemplate` 클래스는 해당 템플릿으로부터 생성된 모든 현재 열린 문서의 목록(`CPtrList`)을 유지합니다. `CDocTemplate::AddDocument` 및 `CDocTemplate::RemoveDocument`는 템플릿에서 문서를 추가 또는 제거하기 위한 가상 멤버 함수를 제공합니다. `CDocTemplate` 이의 friend `CDocument` 보호를 설정할 수 있습니다 `CDocument::m_pDocTemplate` 문서를 생성 한 doc 템플릿을 다시 가리키도록 후방 포인터입니다.

`CWinApp`은 기본 `OnFileOpen` 구현을 처리하며, 이 구현은 다시 모든 doc 템플릿을 쿼리합니다. 이러한 구현에는 이미 열린 문서 조사 및 새 문서를 여는 데 사용할 형식 결정이 포함됩니다.

`CDocTemplate`은 문서 및 프레임에 대한 UI 바인딩을 관리합니다.

`CDocTemplate`은 명명되지 않은 문서의 개수를 유지합니다.

## <a name="cdocument"></a>CDocument

A `CDocument` 가 소유 하는 `CDocTemplate`합니다.

문서에는 해당 문서(`CView`)를 표시 중인 현재 열린 뷰 목록(`CPtrList`에서 파생)을 가집니다.

문서는 뷰를 생성/제거하지 않지만 생성된 후 서로 연결됩니다. 문서를 닫으면(파일/닫기 사용) 연결된 모든 뷰가 닫힙니다. 문서의 마지막 뷰가 닫히면(창/닫기) 문서가 닫힙니다.

`CDocument::AddView`, `RemoveView` 인터페이스는 뷰 목록을 유지 관리하는 데 사용됩니다. `CDocument` 이의 friend `CView` 설정할 수 있습니다는 `CView::m_pDocument` 후방 포인터입니다.

## <a name="cframewnd"></a>CFrameWnd

`CFrameWnd`(프레임이라고도 부름)는 MFC 1.0에서 동일한 역할을 수행하지만 이제 `CFrameWnd` 클래스는 새 클래스를 파생하지 않는 여러 경우에 사용되도록 설계되었습니다. 파생된 클래스 `CMDIFrameWnd` 및 `CMDIChildWnd`도 향상되어 많은 표준 명령이 이미 구현되어 있습니다.

`CFrameWnd`는 프레임의 클라이언트 영역에서 창 만들기 작업을 수행합니다. 일반적으로 프레임의 클라이언트 영역을 채우는 하나의 기본 창이 있습니다.

MDI 프레임 창의 경우 클라이언트 영역은 모든 MDI 자식 프레임 창의 부모가 되는 MDICLIENT 컨트롤로 채워집니다. SDI 프레임 창 또는 MDI 자식 프레임 창의 경우에는 클라이언트 영역이 일반적으로 `CView` 파생 창 개체로 채워집니다. `CSplitterWnd`의 경우, 뷰의 클라이언트 영역은 `CSplitterWnd` 창 개체로 채워지며, `CView` 파생 창 개체(분할 창당 하나)는 `CSplitterWnd`의 자식 창으로 생성됩니다.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
