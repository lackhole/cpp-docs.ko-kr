﻿---
title: MFC 개체 간 관계
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, relationships between key objects
- objects [MFC], relationships
- relationships, MFC objects
- MFC object relationships
ms.assetid: 6e8f3b51-e80f-4d88-94c8-4c1e4ee163ad
ms.openlocfilehash: bb8d1fcd9737b33d52038746a26f4e1bd1043e95
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62309046"
---
# <a name="relationships-among-mfc-objects"></a>MFC 개체 간 관계

문서/뷰 생성 과정을 전체적으로 파악해 봅시다. 문서, 뷰와 문서와 연관된 뷰가 포함된 프레임 창이 있는 실행 중인 프로그램을 생각해 봅니다.

- 문서는 문서를 만든 서식 파일에 해당 문서 및 포인터의 뷰 목록을 유지 합니다.

- 뷰는 해당 문서에 대한 포인터를 유지하며 부모 프레임 창의 자식입니다.

- 문서 프레임 창은 현재 활성 뷰에 대한 포인터를 유지합니다.

- 문서 템플릿은 해당 템플릿의 열려 있는 문서의 목록을 유지합니다.

- 응용 프로그램에는 해당 문서 템플릿 목록을 유지합니다.

- Windows는 열려 있는 창을 모두 추적하여 메시지를 보낼 수 있습니다.

이러한 관계는 문서/뷰를 만드는 동안 설정됩니다. 다음 표에서는 실행 중인 프로그램의 개체가 다른 개체에 액세스하는 방법을 보여 줍니다. 모든 개체는 전역 함수 [AfxGetApp](../mfc/reference/application-information-and-management.md#afxgetapp)를 호출하여 응용 프로그램 개체에 대한 포인터를 가져올 수 있습니다.

### <a name="gaining-access-to-other-objects-in-your-application"></a>응용 프로그램의 다른 개체에 액세스

|개체에서|다른 개체에 액세스 하는 방법|
|-----------------|---------------------------------|

|문서|문서의 뷰 목록에 액세스하기 위해 [GetFirstViewPosition](../mfc/reference/cdocument-class.md#getfirstviewposition)과 [GetNextView](../mfc/reference/cdocument-class.md#getnextview)를 사용합니다.<br /><br />문서 템플릿을 가져오기 위해 [GetDocTemplate](../mfc/reference/cdocument-class.md#getdoctemplate)을 호출합니다.|
|뷰|문서를 가져오기 위해 [GetDocument](../mfc/reference/cview-class.md#getdocument)를 호출합니다.<br /><br />프레임 창을 가져오기 위해 [GetParentFrame](../mfc/reference/cwnd-class.md#getparentframe)을 호출합니다.|
|문서 프레임 창|현재 뷰를 가져오기 위해 [GetActiveView](../mfc/reference/cframewnd-class.md#getactiveview)를 호출합니다.<br /><br />현재 뷰에 연결된 문서를 가져오기 위해 [GetActiveDocument](../mfc/reference/cframewnd-class.md#getactivedocument)를 호출합니다.|

|MDI 프레임 창|현재 활성화된 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)를 가져오기 위해 [MDIGetActive](../mfc/reference/cmdiframewnd-class.md#mdigetactive)를 호출합니다.|

일반적으로 프레임 창에는 하나의 뷰가 있지만 경우에 따라 분할자 창과 같이 동일한 프레임 창에 여러 뷰가 있을 수 있습니다. 프레임 창은 현재 활성화된 뷰에 대한 포인터를 유지합니다. 포인터는 다른 뷰가 활성화 될 때마다 업데이트 됩니다.

> [!NOTE]
>  주 프레임 창에 대한 포인터는 [m_pMainWnd](../mfc/reference/cwinthread-class.md#m_pmainwnd) 멤버 변수에 저장됩니다. `CWinApp`의 `InitInstance` 멤버 함수를 재정의할 때 `OnFileNew`를 호출하면 *m_pMainWnd*가 설정됩니다. `OnFileNew`를 호출하지 않으면 `InitInstance`에서 변수값을 직접 설정해야 합니다. (명령줄에 /Embedding이 있으면 SDI COM 구성 요소 (서버) 응용 프로그램에서는 설정할 수 없습니다.) *m_pMainWnd*는 이제 `CWinThread`이 아닌 `CWinApp` 클래스의 멤버입니다.

## <a name="see-also"></a>참고자료

[문서 템플릿 및 문서/뷰 만들기 프로세스](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[문서 템플릿 만들기](../mfc/document-template-creation.md)<br/>
[문서/뷰 만들기](../mfc/document-view-creation.md)<br/>
[새 문서, 창 및 뷰 만들기](../mfc/creating-new-documents-windows-and-views.md)
