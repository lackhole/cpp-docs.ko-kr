---
title: 'ActiveX 컨트롤 컨테이너: 대화 상자가 아닌 컨테이너에서 컨트롤을 사용 하 여'
ms.date: 11/04/2016
helpviewer_keywords:
- Create method [MFC], ActiveX controls
- CreateControl method [MFC]
- ActiveX controls [MFC], creating
- ActiveX control containers [MFC], non-dialog containers
- ActiveX control containers [MFC], inserting controls
ms.assetid: 46f195b0-b8ca-4409-8cca-fbfaf2c9ab9f
ms.openlocfilehash: 70a67a6952d5361177b89e3ba514d7036b5799b6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394873"
---
# <a name="activex-control-containers-using-controls-in-a-non-dialog-container"></a>ActiveX 컨트롤 컨테이너: 대화 상자가 아닌 컨테이너에서 컨트롤을 사용 하 여

일부 SDI 등의 응용 프로그램 또는 MDI 응용 프로그램에서 응용 프로그램의 창에서 컨트롤을 포함 해야 합니다. 합니다 **만들기** 시각적 개체에 의해 삽입 된 래퍼 클래스의 멤버 함수 C++, 대화 상자에 대 한 필요 없이 동적으로 컨트롤의 인스턴스를 만들 수 있습니다.

합니다 **만들기** 멤버 함수에 다음 매개 변수:

*lpszWindowName*<br/>
(해당 되는 경우) 컨트롤의 텍스트 또는 캡션 속성에 표시할 텍스트 포인터입니다.

*dwStyle*<br/>
Windows 스타일입니다. 전체 목록을 참조 하세요 [CWnd::CreateControl](../mfc/reference/cwnd-class.md#createcontrol)합니다.

*rect*<br/>
컨트롤의 크기와 위치를 지정합니다.

*pParentWnd*<br/>
일반적으로 컨트롤의 부모 창 지정을 `CDialog`입니다. 않아야 **NULL**합니다.

*nID*<br/>
컨트롤 ID를 지정 하 고 컨트롤에 참조 컨테이너에서 사용할 수 있습니다.

SDI 응용 프로그램의 폼 보기에서이 함수를 사용 하 여 동적으로 만들려면 ActiveX 컨트롤의 예로 것입니다. 컨트롤의 인스턴스를 만들 수 있습니다는 `WM_CREATE` 응용 프로그램의 처리기입니다.

예를 들어 `CMyView` 는 기본 뷰 클래스 `CCirc` 래퍼 클래스 및 가변 원형 H는 헤더 (합니다. H) 래퍼 클래스의 파일입니다.

이 기능을 구현 하는 것은 4 단계 프로세스입니다.

### <a name="to-dynamically-create-an-activex-control-in-a-non-dialog-window"></a>동적으로 대화 상자가 아닌 창에서 ActiveX 컨트롤을 만들려면

1. 가변 원형 삽입 CMYVIEW에서 H입니다. H, 직전의 `CMyView` 클래스 정의:

   [!code-cpp[NVC_MFC_AxCont#12](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_1.h)]

1. 멤버 변수 추가 (형식의 `CCirc`)의 보호 된 섹션에는 `CMyView` 클래스 CMYVIEW에 정의 합니다. H:

   [!code-cpp[NVC_MFC_AxCont#13](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_2.h)]
    [!code-cpp[NVC_MFC_AxCont#14](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_3.h)]

1. 추가 된 `WM_CREATE` 클래스에 메시지 처리기 `CMyView`합니다.

1. 처리기 함수에서 `CMyView::OnCreate`, 컨트롤의 호출 `Create` 함수를 사용 하는 **이** 부모 창으로 포인터:

   [!code-cpp[NVC_MFC_AxCont#15](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_4.cpp)]

1. 프로젝트를 다시 빌드합니다. 응용 프로그램의 뷰를 만들 때마다 Circ 컨트롤을 동적으로 생성 됩니다.

## <a name="see-also"></a>참고자료

[ActiveX 컨트롤 컨테이너](../mfc/activex-control-containers.md)
