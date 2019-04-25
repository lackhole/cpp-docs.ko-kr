---
title: 문서 프레임 창 만들기
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], creating
- document templates [MFC], and document frame windows
- windows [MFC], creating
- runtime, class information
- run-time class [MFC], and document frame window creation
- document frame windows [MFC], creating
- MFC, frame windows
ms.assetid: 8671e239-b76f-4dea-afa8-7024e6e58ff5
ms.openlocfilehash: 66a951994a75cbd99debeb2c6511739411cdd470
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174031"
---
# <a name="creating-document-frame-windows"></a>문서 프레임 창 만들기

[문서/뷰 만들기](../mfc/document-view-creation.md) 표시 하는 방법을 [CDocTemplate](../mfc/reference/cdoctemplate-class.md) 프레임 창, 문서 및 뷰를 만들고 모두 함께 연결 하는 오케스트레이션 하는 개체입니다. 세 [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) 에 대 한 인수는 `CDocTemplate` 생성자 프레임 창, 문서 및 문서 템플릿 파일에서 새 명령 등 사용자 명령에 대 한 응답에서 동적으로 작성 하는 뷰 클래스를 지정 합니다. 메뉴 또는 MDI 창 메뉴에서 새 창 명령을 합니다. 문서 서식 파일 보기 및 문서에 대 한 프레임 창을 만들 때 나중에 사용할이 정보를 저장 합니다.

에 대 한는 [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) 파생 된 속성이 제대로 작동 하는 메커니즘 프레임 창 클래스를 사용 하 여 선언 해야 합니다 [DECLARE_DYNCREATE](../mfc/reference/run-time-object-model-services.md#declare_dyncreate) 매크로입니다. 문서 프레임 창 클래스의 동적 생성 메커니즘을 사용 하 여 만드는 프레임 워크 해야 하기 때문에 이것이 `CObject`합니다.

사용자가 문서를 만드는 명령, 프레임 워크 문서 템플릿을 문서 개체, 뷰 및 뷰를 표시 하는 프레임 창 만들기를 호출 합니다. 문서 템플릿을 문서 프레임 창을 만들면 해당 클래스의 개체를 만듭니다-에서 파생 된 클래스 [CFrameWnd](../mfc/reference/cframewnd-class.md) SDI 응용 프로그램에 대 한 주고 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) MDI에 대 한 응용 프로그램입니다. 프레임 창 개체를 다음 호출 하는 프레임 워크 [LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) 리소스에서 생성 정보를 얻으려면 하 고 Windows 창을 만들기 위해 멤버 함수입니다. 프레임 워크는 프레임 창 개체 창 핸들에 연결합니다. 다음 문서 프레임 창의 자식 창으로 뷰를 만듭니다.

결정 하는 데 주의 해야 [초기화 시점](../mfc/when-to-initialize-cwnd-objects.md) 여 `CWnd`-파생 개체입니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [CObject (동적 생성 메커니즘 해당)에서 클래스 파생 시키기](../mfc/deriving-a-class-from-cobject.md)

- [문서/뷰 만들기 (템플릿 및 프레임 창 만들기)](../mfc/document-view-creation.md)

- [프레임 창 제거](../mfc/destroying-frame-windows.md)

## <a name="see-also"></a>참고자료

[프레임 창 사용](../mfc/using-frame-windows.md)
