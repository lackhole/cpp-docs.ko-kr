---
title: MFC 애플리케이션 아키텍처 클래스
ms.date: 11/04/2016
f1_keywords:
- vc.classes.mfc
helpviewer_keywords:
- MFC, classes
- MFC, application development
- classes [MFC], MFC
- application architecture classes [MFC]
ms.assetid: 71b2de54-b44d-407e-9c71-9baf954e18d9
ms.openlocfilehash: 47feeb056d02b81bb88ccf3c5fd49bc983583ee7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62239307"
---
# <a name="mfc-application-architecture-classes"></a>MFC 애플리케이션 아키텍처 클래스

이 범주에는 클래스를 framework 응용 프로그램의 아키텍처에 기여합니다. 이러한 대부분의 응용 프로그램에 공통적으로 적용 되는 기능을 제공 합니다. 응용 프로그램별 기능을 추가 하기 위해 프레임 워크를 입력 합니다. 일반적으로 이렇게 하면 아키텍처 클래스에서 새 클래스를 파생 하 고 다음 새 멤버를 추가 하거나 기존 멤버 함수를 재정의 합니다.

[응용 프로그램 마법사](../mfc/reference/mfc-application-wizard.md) 서로 다른 방법으로 응용 프로그램 프레임 워크를 사용 하는 모든 응용 프로그램의 여러 형식을 생성 합니다. SDI (단일 문서 인터페이스) 및 MDI (다중 문서 인터페이스) 응용 프로그램을 모두 사용할 문서/뷰 아키텍처를 호출 하는 프레임 워크의 일부입니다. 다른 유형의 응용 프로그램 대화 상자 기반 응용 프로그램, 폼 기반 응용 프로그램 및 Dll 등 문서/뷰 아키텍처 기능 중 일부만 사용합니다.

문서/뷰 응용 프로그램 문서, 뷰 및 프레임 창 하나 이상의 집합을 포함 합니다. 문서 템플릿 개체를 각 문서/뷰/프레임 집합에 대 한 클래스를 연결합니다.

MFC 응용 프로그램에서 문서/뷰 아키텍처를 사용 해야 하지만 이렇게 하려면 장점이 여러 가지가 있습니다. MFC OLE 컨테이너 및 서버 지원을 기반으로 문서/뷰 아키텍처를 그대로 인쇄 및 인쇄 미리 보기를 지원 합니다.

모든 MFC 응용 프로그램에 두 개 이상의 개체: 응용 프로그램 개체에서 파생 [CWinApp](../mfc/reference/cwinapp-class.md), 및에서 종종 간접적으로 파생 되는 주 창 개체의 일종 [CWnd](../mfc/reference/cwnd-class.md)합니다. (주 창에서 파생 되는 대부분의 경우 [CFrameWnd](../mfc/reference/cframewnd-class.md)를 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md), 또는 [CDialog](../mfc/reference/cdialog-class.md)에서 파생 되는 모든 `CWnd`.)

문서/뷰 아키텍처를 사용 하는 응용 프로그램 추가 개체를 포함 합니다. 주 개체입니다.

- 클래스에서 파생 된 응용 프로그램 개체 [CWinApp](../mfc/reference/cwinapp-class.md)앞서 언급 했 듯이, 합니다.

- 클래스에서 파생 된 하나 이상의 문서 클래스 개체 [CDocument](../mfc/reference/cdocument-class.md)합니다. 문서 클래스 개체 보기에서 처리 하는 데이터의 내부 표현에 대 한 책임이 있습니다. 데이터 파일에 연결할 수 있습니다.

- 클래스에서 파생 된 뷰 개체를 하나 이상의 [CView](../mfc/reference/cview-class.md)합니다. 각 보기에는 문서에 연결 되 고 프레임 창과 연결 된 창입니다. 뷰를 표시 및 문서 클래스 개체에 포함 된 데이터를 조작 합니다.

문서/뷰 응용 프로그램 프레임 창에 포함 될 수도 (에서 파생 된 [CFrameWnd](../mfc/reference/cframewnd-class.md)) 및 문서 템플릿 (에서 파생 된 [CDocTemplate](../mfc/reference/cdoctemplate-class.md)).

## <a name="see-also"></a>참고자료

[클래스 개요](../mfc/class-library-overview.md)
