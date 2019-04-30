---
title: 문서 뷰 아키텍처
ms.date: 11/19/2018
helpviewer_keywords:
- CView class [MFC], view architecture
- CDocument class [MFC]
- MFC, views
- views [MFC], MFC document/view model
- document objects [MFC]
- document objects [MFC], MFC document/view model
- MFC, documents
- documents [MFC], MFC document/view model
- document objects [MFC], document/view architecture
ms.assetid: 6127768a-553f-462a-b01b-a5ee6068c81e
ms.openlocfilehash: d1b1f80f44fdc66a3174ea75c15e139f98a4520b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389689"
---
# <a name="documentview-architecture"></a>문서/뷰 아키텍처

기본적으로 MFC 응용 프로그램 마법사 문서 클래스 및 뷰 클래스를 사용 하 여 기초 응용 프로그램을 만듭니다. MFC는이 두 클래스에 데이터 관리를 구분합니다. 문서는 데이터를 저장 하 고 및 데이터를 인쇄 관리, 데이터의 여러 뷰 업데이트를 조정 합니다. 뷰는 데이터를 표시 하 고 사용자 상호 작용, 편집 및 선택 영역을 포함 하 여 관리 합니다.

이 모델에서는 MFC 문서 개체로 읽고 영구적 저장소로 데이터를 씁니다. 문서 (예: 데이터베이스) 있는 어디서 나 데이터에 대 한 인터페이스를 제공할 수도 있습니다. 사용자 선택 영역 창에서 데이터를 렌더링 하 고 데이터의 편집에서 데이터 표시를 관리 하는 별도 뷰 개체입니다. 문서에서 표시 데이터를 가져오는 뷰와 데이터 내용을 문서에 다시 알립니다.

쉽게 재정의 하거나 무시 문서/뷰를 서로 구분할 수 있지만 대부분의 경우에서이 모델에 따라 매력적인 이유가 있습니다. 가장 좋은 스프레드시트 및 차트 보기와 같은 동일한 문서의 여러 뷰를 할 때입니다. 문서/뷰 모델 코드 일반적인 모든 뷰 (예: 계산 엔진) 문서에 있을 수 있습니다 하는 동안 데이터의 각 뷰를 나타내는 별도 뷰 개체를 수 있습니다. 또한 문서는 데이터가 변경 될 때마다 모든 보기를 업데이트 하는 작업에 사용 합니다.

MFC 문서/뷰 아키텍처 쉽게 여러 뷰, 여러 문서 형식, 분할 창 및 기타 중요 한 사용자 인터페이스 기능을 지원 합니다.

사용자와 프로그래머에 게 두드러진 MFC 프레임 워크의 일부는 문서 및 보기. 대부분의 프레임 워크를 사용 하 여 응용 프로그램 개발 작업 문서 및 뷰 클래스 작성에 들어갑니다. 이 문서에서는 설명합니다.

- 문서, 뷰 및 프레임 워크에서 조작 방법을 위해.

- 해야 할 사항을 구현 하는 데 있습니다.

문서/보기의 중심에는 네 가지 주요 클래스:

합니다 [CDocument](../mfc/reference/cdocument-class.md) (또는 [COleDocument](../mfc/reference/coledocument-class.md)) 클래스를 저장 하거나 프로그램의 데이터를 제어 하는 데 사용 되는 개체를 지원 하며 문서 프로그래머가 정의한 클래스에 대 한 기본 기능을 제공 합니다. 문서를 일반적으로 파일 메뉴에서 열기 명령을 사용 하 여 열고 파일 메뉴에서 저장 명령을 사용 하 여 저장 하는 데이터의 단위를 나타냅니다.

합니다 [CView](../mfc/reference/cview-class.md) (또는 여러 파생된 클래스 중 하나) 프로그래머가 정의한 뷰 클래스에 대 한 기본 기능을 제공 합니다. 뷰를 문서에 연결 되어 있고 문서와 사용자 간의 중개자 역할: 뷰 화면에서 문서의 이미지를 렌더링 한 문서에는 작업으로 사용자 입력 해석 합니다. 뷰는 또한 인쇄 및 인쇄 미리 보기 이미지를 렌더링합니다.

[CFrameWnd](../mfc/reference/cframewnd-class.md) (또는 해당 변형 중 하나)는 하나 이상의 문서 뷰 주위 틀을 제공 하는 개체를 지원 합니다.

[CDocTemplate](../mfc/reference/cdoctemplate-class.md) (또는 [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md) 하거나 [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md)) 지정 된 형식의 하나 이상의 기존 문서를 조정 하 고 올바른 만들기를 관리 하는 개체를 지원 합니다. 문서, 뷰 및 해당 형식에 대 한 프레임 창 개체입니다.

다음 그림을 문서와 뷰 간의 관계를 보여 줍니다.

![뷰는 표시 되는 문서의 부분](../mfc/media/vc379n1.gif "뷰는 표시 되는 문서의 부분") <br/>
문서 및 보기

클래스 라이브러리의 문서/뷰 구현에는 데이터 자체 데이터에 대해 사용자 작업 및 해당 표시에서 구분합니다. 데이터의 모든 변경 내용은 문서 클래스를 통해 관리 됩니다. 뷰에 액세스 하 여 데이터를 업데이트 하려면이 인터페이스를 호출 합니다.

문서, 연결 된 뷰, 및 보기의 프레임 창 문서 템플릿에 의해 생성 됩니다. 문서 템플릿에 하나의 문서 종류의 모든 문서 만들기 및 관리 하는 일을 담당 합니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [문서/뷰 아키텍처에 대 한 자세한 설명](../mfc/a-portrait-of-the-document-view-architecture.md)

- [문서/뷰 아키텍처의 이점](../mfc/advantages-of-the-document-view-architecture.md)

- [응용 프로그램 마법사로 만든 문서 및 뷰 클래스](../mfc/document-and-view-classes-created-by-the-mfc-application-wizard.md)

- [문서/뷰 아키텍처의 대체](../mfc/alternatives-to-the-document-view-architecture.md)

- [단일 문서에 뷰 여러 개 추가](../mfc/adding-multiple-views-to-a-single-document.md)

- [문서 사용](../mfc/using-documents.md)

- [뷰 사용](../mfc/using-views.md)

- [여러 문서 형식, 뷰 및 프레임 창](../mfc/multiple-document-types-views-and-frame-windows.md)

- [초기화 하 고 문서 및 뷰 정리](../mfc/initializing-and-cleaning-up-documents-and-views.md)

- [문서 및 뷰 클래스에 대 한 고유한 추가 초기화](../mfc/creating-new-documents-windows-and-views.md)

- [문서 및 뷰를 이용한 데이터베이스 클래스 사용](../data/mfc-using-database-classes-with-documents-and-views.md)

- [문서 및 뷰 하지 않는 데이터베이스 클래스 사용](../data/mfc-using-database-classes-without-documents-and-views.md)

- [샘플](../overview/visual-cpp-samples.md)

## <a name="see-also"></a>참고자료

[사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)<br/>
[Windows](../mfc/windows.md)<br/>
[프레임 창](../mfc/frame-windows.md)<br/>
[문서 템플릿 및 문서/뷰 만들기 프로세스](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[문서/뷰 만들기](../mfc/document-view-creation.md)<br/>
[새 문서, 창 및 뷰 만들기](../mfc/creating-new-documents-windows-and-views.md)
