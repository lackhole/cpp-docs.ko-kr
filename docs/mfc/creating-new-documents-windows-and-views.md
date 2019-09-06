---
title: 새 문서, 창 및 뷰 만들기
ms.date: 11/19/2018
helpviewer_keywords:
- MDI [MFC], creating windows
- window objects [MFC], creating
- objects [MFC], creating document objects
- MFC default objects
- frame windows [MFC], creating
- windows [MFC], MDI
- MFC, documents
- view objects [MFC], creating
- windows [MFC], creating
- overriding, default view behavior
- views [MFC], initializing
- customizing MFC default objects
- MFC, frame windows
- MFC, views
- MDI [MFC], frame windows
- child windows [MFC], creating MDI
- view objects [MFC]
- document objects [MFC], creating
- MFC default objects [MFC], customizing
- views [MFC], overriding default behavior
- initializing views [MFC]
ms.assetid: 88aa1f5f-2078-4603-b16b-a2b4c7b4a2a3
ms.openlocfilehash: 3d4ca55a9bff6ec42643db745896a2cea96dcefb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62242632"
---
# <a name="creating-new-documents-windows-and-views"></a>새 문서, 창 및 뷰 만들기

다음 그림에서는 문서, 뷰 및 프레임 창 만들기 프로세스의 개요를 제공합니다. 관련있는 개체에 대한 추가 세부 정보는 다른 기사를 참조합니다.

이 프로세스를 완료하면 협력 개체가 존재하고 서로에 대한 포인터를 저장 합니다. 다음 그림에서는 개체가 생성되는 순서를 보여 줍니다. 그림들은 해당 순서에 대하여 설명합니다.

![문서 만들기 시퀀스](../mfc/media/vc387l1.gif "문서 만들기 시퀀스") <br/>
문서를 만드는 순서

![프레임 창 만들기 시퀀스](../mfc/media/vc387l2.png "프레임 창 만들기 시퀀스") <br/>
프레임 창을 만드는 순서

![뷰를 만드는 순서](../mfc/media/vc387l3.gif "뷰 만들기 시퀀스") <br/>
뷰를 만드는 순서

프레임워크가 새 문서, 뷰 및 프레임 창 개체를 초기화하는 방법에 대한 내용은 MFC 라이브러리 참조에서 [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), [CFrameWnd](../mfc/reference/cframewnd-class.md), [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) 및 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) 클래스를 참조합니다. 또한 **파일** 메뉴의 **새로 만들기**와 **열기** 항목에 대한 프레임워크의 표준 명령 설명에서 생성 및 초기화 절차에 대한 설명은 [Technical Note 22](../mfc/tn022-standard-commands-implementation.md)를 참조합니다.

##  <a name="_core_initializing_your_own_additions_to_these_classes"></a> 이 클래스의 초기화에 추가하기

앞의 그림은 멤버함수를 재정의하여 응용 프로그램의 개체를 초기화 할 수 있는 지점도 제안합니다. `OnInitialUpdate`를 재정의하는 것이 뷰를 초기화 하는 가장 좋은 지점입니다. `OnInitialUpdate` 호출은 프레임창을 만들고 프레임 창의 뷰가 문서에 첨부된 직후에 발생 합니다. 예를들어 뷰가 스크롤 뷰라면 (`CView` 대신 `CScrollView`에서 파상된) `OnInitialUpdate`를 재정의하여 문서 크기에 기반한 뷰 크기를 설정해야 합니다. (이 과정은 [CScrollView](../mfc/reference/cscrollview-class.md)의 설명에 표현되어 있습니다.) `CDocument` 멤버 함수 `OnNewDocument`와 `OnOpenDocument`를 재정의하여 응용 프로그램별 문서 초기화를 제공할 수 있습니다. 일반적으로 문서는 두 가지 방법으로 만들 수 있으므로 두가지 모두 재정의 해야합니다.

대부분의 경우에서 재정의 기본 클래스 버전을 호출합니다. 자세한 내용은 MFC 라이브러리 참조에서 클래스 [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), [CFrameWnd](../mfc/reference/cframewnd-class.md) 및 [CWinApp](../mfc/reference/cwinapp-class.md)의 명명된 멤버함수를 참조합니다.

## <a name="see-also"></a>참고자료

[문서 템플릿 및 문서/뷰 만들기 프로세스](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[문서 템플릿 만들기](../mfc/document-template-creation.md)<br/>
[문서/뷰 만들기](../mfc/document-view-creation.md)<br/>
[MFC 개체 간 관계](../mfc/relationships-among-mfc-objects.md)
