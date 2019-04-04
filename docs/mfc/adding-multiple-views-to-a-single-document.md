---
title: 단일 문서에 뷰 여러 개 추가
ms.date: 11/04/2016
helpviewer_keywords:
- multiple views [MFC], SDI applications
- documents [MFC], multiple views
- single document interface (SDI), adding views
- views [MFC], SDI applications
ms.assetid: 86d0c134-01d5-429c-b672-36cfb956dc01
ms.openlocfilehash: 593c59c73b58b4364c9d652ce8eb415c17af496c
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58767589"
---
# <a name="adding-multiple-views-to-a-single-document"></a>단일 문서에 뷰 여러 개 추가

Microsoft Foundation 클래스 (MFC) 라이브러리를 사용 하 여 만든 단일 문서 인터페이스 (SDI) 응용 프로그램에서 각 문서 유형에 단일 보기 형식 연관 됩니다. 경우에 따라 새 보기를 사용 하 여 문서의 현재 보기를 전환할 수 있도록는 것이 좋습니다.

> [!TIP]
>  단일 문서의 여러 뷰를 구현에서 추가 절차를 참조 하세요 [CDocument::AddView](../mfc/reference/cdocument-class.md#addview) 하며 [수집](../overview/visual-cpp-samples.md) MFC 샘플입니다.

새로 추가 하 여이 기능을 구현할 수 `CView`-파생 클래스와 기존 MFC 응용 프로그램 보기를 동적으로 전환 하는 것에 대 한 코드를 추가 합니다.

단계를 아래와 같습니다.

- [기존 응용 프로그램 클래스 수정](#vcconmodifyexistingapplicationa1)

- [만들고 새 뷰 클래스를 수정 합니다.](#vcconnewviewclassa2)

- [만들고 새 뷰를 연결 합니다.](#vcconattachnewviewa3)

- [전환 함수 구현](#vcconswitchingfunctiona4)

- [뷰를 전환 하는 것에 대 한 지원 추가](#vcconswitchingtheviewa5)

이 항목의 나머지 부분에서는 다음을 가정합니다.

- 이름을 합니다 `CWinApp`-파생 개체가 `CMyWinApp`, 및 `CMyWinApp` 선언 되 고에 정의 된 *MYWINAPP 합니다. H* 고 *MYWINAPP 합니다. CPP*합니다.

- `CNewView` 새 이름인 `CView`-파생 개체를 및 `CNewView` 선언 되 고에 정의 된 *NEWVIEW 합니다. H* 고 *NEWVIEW 합니다. CPP*합니다.

##  <a name="vcconmodifyexistingapplicationa1"></a> 기존 응용 프로그램 클래스 수정

보기를 전환 하려면 응용 프로그램으로 전환 메서드와 뷰를 저장 하는 멤버 변수를 추가 하 여 응용 프로그램 클래스를 수정 해야 합니다.

선언에 다음 코드를 추가 `CMyWinApp` 에서 *MYWINAPP 합니다. H*:

[!code-cpp[NVC_MFCDocViewSDI#1](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_1.h)]

새 멤버 변수를 `m_pOldView` 고 `m_pNewView`, 현재 보기와 새로 만든된 것을 가리킵니다. 새 메서드 (`SwitchView`) 사용자가 요청한 때 뷰를 전환 합니다. 이 항목의 뒷부분에 나오는 메서드 본문 부분은 [전환 기능을 구현](#vcconswitchingfunctiona4)합니다.

Windows 메시지를 정의 하는 새 헤더 파일을 포함 하 여 응용 프로그램 클래스에 마지막으로 수정한 필요 (**WM_INITIALUPDATE**) 전환 함수에서 사용 되는 합니다.

포함 섹션에서 다음 줄을 삽입 *MYWINAPP 합니다. CPP*:

[!code-cpp[NVC_MFCDocViewSDI#2](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_2.cpp)]

변경 내용을 저장 하 고 단계를 계속 합니다.

##  <a name="vcconnewviewclassa2"></a> 만들고 새 뷰 클래스를 수정 합니다.

새 뷰 클래스를 만드는 쉬워진를 사용 하 여 합니다 **새 클래스** 명령 클래스 뷰에서 사용할 수 있습니다. 이 클래스에 대 한 유일한 요구 사항은에서 파생 되며 `CView`합니다. 응용 프로그램에이 새 클래스를 추가 합니다. 프로젝트에 새 클래스를 추가 하는 방법에 대 한 자세한 내용은 참조 하세요. [클래스 추가](../ide/adding-a-class-visual-cpp.md)합니다.

프로젝트에 클래스를 추가한 후 일부 보기 클래스 멤버의 접근성을 변경 해야 합니다.

수정 *NEWVIEW 합니다. H* 에서 액세스 지정자를 변경 하 여 **보호** 하려면 **공용** 생성자 및 소멸자에 대 한 합니다. 따라서을 만들고 동적으로 제거 하 고 표시 되기 전에 뷰의 모양을 수정 하는 클래스입니다.

변경 내용을 저장 하 고 단계를 계속 합니다.

##  <a name="vcconattachnewviewa3"></a> 만들고 새 뷰를 연결 합니다.

를 만들고 새 뷰를 연결 하려면 수정 해야 합니다 `InitInstance` 응용 프로그램 클래스의 함수입니다. 새 뷰 개체를 차례로 초기화 둘 다 만드는 새 코드를 추가 하는 수정 `m_pOldView` 고 `m_pNewView` 두 개의 기존 뷰 개체를 사용 하 여 합니다.

새 보기 내에서 만들어지므로 `InitInstance` 함수, 신규 및 기존 뷰 응용 프로그램의 수명 동안 유지 합니다. 그러나 응용 프로그램은 새 보기를 동적으로 만들 간단 하 게 수 없습니다.

이 코드에 대 한 호출 뒤에 삽입 `ProcessShellCommand`:

[!code-cpp[NVC_MFCDocViewSDI#3](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_3.cpp)]

변경 내용을 저장 하 고 단계를 계속 합니다.

##  <a name="vcconswitchingfunctiona4"></a> 전환 함수 구현

이전 단계에서 만들어지고 새 뷰 개체를 초기화 하는 코드를 추가 합니다. 전환 메서드를 구현 하는 주요 마지막 `SwitchView`합니다.

응용 프로그램 클래스의 구현 파일의 끝 (*MYWINAPP 합니다. CPP*), 다음 메서드 정의 추가 합니다.

[!code-cpp[NVC_MFCDocViewSDI#4](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_4.cpp)]

변경 내용을 저장 하 고 단계를 계속 합니다.

##  <a name="vcconswitchingtheviewa5"></a> 뷰를 전환 하는 것에 대 한 지원 추가

마지막 단계는 호출 하는 코드를 추가 합니다 `SwitchView` 메서드 뷰 간을 전환 해야 하는 응용 프로그램입니다. 여러 가지 방법으로이 작업을 수행할 수 있습니다: 사용자가 선택할 수에 대 한 새 메뉴 항목을 추가 하거나 특정 조건이 충족 될 때 내부적으로 뷰를 전환 하 여 합니다.

새 메뉴 항목 및 명령 처리기 함수를 추가 하는 방법은 참조 하세요 [명령 및 컨트롤 알림에 대 한 처리기](../mfc/handlers-for-commands-and-control-notifications.md)합니다.

## <a name="see-also"></a>참고자료

[문서/뷰 아키텍처](../mfc/document-view-architecture.md)
