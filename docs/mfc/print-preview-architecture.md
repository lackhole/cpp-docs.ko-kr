---
title: 인쇄 미리 보기 아키텍처
ms.date: 11/04/2016
helpviewer_keywords:
- print preview [MFC], process
- previewing printing
- print preview [MFC], architecture
- printing [MFC], print preview
- print preview [MFC], modifications to MFC
ms.assetid: 0efc87e6-ff8d-43c5-9d72-9b729a169115
ms.openlocfilehash: ea80b67b3f6bb6980e4e8f7f12a967cb7bb5b6c7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62218731"
---
# <a name="print-preview-architecture"></a>인쇄 미리 보기 아키텍처

이 문서에서는 MFC 프레임워크에서 인쇄 미리 보기 기능을 구현하는 방법을 설명합니다. 다루는 항목은 다음과 같습니다.

- [인쇄 미리 보기 프로세스](#_core_the_print_preview_process)

- [인쇄 미리 보기 수정](#_core_modifying_print_preview)

인쇄 미리 보기는 화면 표시 및 인쇄와는 다소 다릅니다. 디바이스에 이미지를 직접 그리는 대신 애플리케이션이 화면을 사용해서 프린터를 시뮬레이션해야 하기 때문입니다. 이 위해 Microsoft Foundation Class 라이브러리에서 파생 된 특별 한 (문서화 되지 않은) 클래스를 정의 [CDC 클래스](../mfc/reference/cdc-class.md)라는 `CPreviewDC`합니다. 또는 `CDC` 개체는 두 개의 디바이스 컨텍스트를 포함하지만 일반적으로 동일합니다. 에 `CPreviewDC` 개체를 서로: 첫 번째 시뮬레이션 되는 프린터, 두 번째 출력 실제로 표시 되는 화면을 나타냅니다.

##  <a name="_core_the_print_preview_process"></a> 인쇄 미리 보기 프로세스

인쇄 미리 보기 명령을 선택 하면 합니다 **파일** 메뉴에서 프레임 워크를 만듭니다를 `CPreviewDC` 개체입니다. 애플리케이션이 프린터 디바이스 컨텍스트의 특성을 설정하는 작업을 수행할 때마다 프레임워크도 화면 디바이스 컨텍스트에서 비슷한 작업을 수행합니다. 예를 들어 애플리케이션이 인쇄 글꼴을 선택하면, 프레임워크도 프린터 글꼴을 시뮬레이션하는 화면 표시를 위해 글꼴을 선택합니다. 애플리케이션이 프린터에 출력을 보낼 때마다 프레임워크는 대신 출력을 화면으로 전송합니다.

인쇄 미리 보기는 또한 문서의 페이지를 그리는 순서도 인쇄와 다릅니다. 인쇄 중에는 특정 페이지 범위가 렌더링될 때까지 프레임워크가 인쇄 루프를 계속 수행합니다. 인쇄 미리 보기 중에는 언제라도 1~2개의 페이지가 표시되며, 애플리케이션은 대기 상태입니다. 사용자의 반응이 있기 전까지는 추가 페이지가 표시되지 않습니다. 응용 프로그램 인쇄 미리 보기 중에 일반적인 화면 표시와 마찬가지로 WM_PAINT 메시지에 응답 해야 합니다.

합니다 [CView::OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) 인쇄 작업의 시작 부분에는 것 처럼 함수는 미리 보기 모드가 호출 되는 경우에 호출 됩니다. 합니다 [CPrintInfo 구조체](../mfc/reference/cprintinfo-structure.md) 함수에 전달 된 구조체 일부 멤버가 인쇄 미리 보기 작업의 특정 특성에 맞게 설정할 수 있는 해당 값을 포함 합니다. 예를 들어, 설정할 수 있습니다 합니다 *m_nNumPreviewPages* 멤버를 한 페이지 또는 두 페이지 모드에서 문서를 미리 볼 것인지 여부를 지정 합니다.

##  <a name="_core_modifying_print_preview"></a> 인쇄 미리 보기 수정

인쇄 미리 보기의 동작과 모양은 여러 가지 방법으로 비교적 쉽게 수정할 수 있습니다. 예를 들어, 다음과 같은 작업이 가능합니다.

- 인쇄 미리 보기 창에 문서의 특정 페이지에 쉽게 액세스할 수 있는 스크롤 막대를 표시합니다.

- 인쇄 미리 보기를 표시할 때 현재 페이지를 먼저 표시하여 문서에서 사용자의 위치를 유지합니다.

- 인쇄 미리 보기 및 인쇄를 위해 서로 다른 초기화를 수행합니다.

- 인쇄 미리 보기에서 사용자의 고유 형식으로 페이지 번호를 표시합니다.

문서가 얼마나 긴지 알고 있고 적합한 값을 사용해서 `SetMaxPage`를 호출하면 프레임 워크가 인쇄 중은 물론 미리 보기 모드에서도 이 정보를 사용할 수 있습니다. 프레임워크가 문서 길이를 알게 되면, 미리 보기 창에 스크롤 막대를 제공하여 사용자가 미리 보기 모드에서 문서의 앞/뒤로 이동할 수 있습니다. 문서 길이를 설정하지 않은 경우에는 프레임워크가 현재 위치를 나타내는 스크롤 상자 위치를 결정할 수 없으므로, 프레임워크가 스크롤 막대를 추가하지 않습니다. 이 경우, 문서에서 페이지를 이동하려면 미리 보기 창의 컨트롤 막대에서 다음 페이지 및 이전 페이지 단추를 사용해야 합니다.

인쇄 미리 보기에는 것에 값을 할당 하는 데 유용 합니다 *m_nCurPage* 소속 `CPrintInfo`는 없습니다 이렇게 하면 일반 인쇄의 경우에 합니다. 일반적인 인쇄의 경우, 이 멤버는 프레임워크에서 뷰 클래스로 정보를 전달합니다. 이를 통해 프레임워크는 인쇄할 페이지를 뷰에 알려줍니다.

반면, 인쇄 미리 보기 모드를 시작할 때에 *m_nCurPage* 반대 방향으로 정보를 전달 하는 멤버: 프레임 워크는 뷰에서 합니다. 프레임워크는 이 멤버의 값을 사용해서 먼저 미리 보기로 표시할 페이지를 결정합니다. 이 멤버의 기본값은 1이므로 문서의 첫 번째 페이지가 처음에 표시됩니다. 인쇄 미리 보기 명령이 호출될 때 표시할 페이지 번호로 이 멤버를 설정하도록 `OnPreparePrinting`을 재정의할 수 있습니다. 이렇게 하면 애플리케이션이 일반적인 표시 모드에서 인쇄 미리 보기 모드로 이동할 때 사용자의 현재 위치를 유지할 수 있습니다.

일부 경우에는 인쇄 작업 또는 인쇄 미리 보기를 위해 호출되었는지 여부에 따라 `OnPreparePrinting`이 다른 초기화를 수행하도록 해야 할 수 있습니다. 검사 하 여이 확인할 수 있습니다 합니다 *m_bPreview* 멤버 변수를 `CPrintInfo` 구조입니다. 이 멤버 설정할지 **TRUE** 인쇄 미리 보기를 호출할 때.

합니다 `CPrintInfo` 구조는 또한 라는 멤버가 포함 *m_strPageDesc*에 단일 페이지 및 다중 페이지 모드 화면 맨 아래에 표시 된 문자열의 서식을 지정 하는 데 사용 됩니다. 기본적으로 폼의 이러한 문자열은 "페이지 *n*" 및 "페이지 *n* - *m*," 수정할 수 있지만 *m_strPageDesc* 에서 내 `OnPreparePrinting` 문자열을 설정 합니다. 참조 [CPrintInfo 구조체](../mfc/reference/cprintinfo-structure.md) 에 *MFC 참조* 자세한 내용은 합니다.

## <a name="see-also"></a>참고자료

[인쇄 및 인쇄 미리 보기](../mfc/printing-and-print-preview.md)<br/>
[인쇄](../mfc/printing.md)<br/>
[CView 클래스](../mfc/reference/cview-class.md)<br/>
[CDC 클래스](../mfc/reference/cdc-class.md)
