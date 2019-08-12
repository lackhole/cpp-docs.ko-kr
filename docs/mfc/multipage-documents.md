---
title: 다중 페이지 문서
ms.date: 11/19/2018
helpviewer_keywords:
- pagination [MFC]
- overriding [MFC], View class functions for printing
- OnPrepareDC method [MFC]
- CPrintInfo structure [MFC], multipage documents
- OnEndPrinting method [MFC]
- protocols [MFC], printing protocol
- document pages vs. printer pages [MFC]
- printer mode [MFC]
- printing [MFC], multipage documents
- printers [MFC], printer mode
- documents [MFC], printing
- OnPreparePrinting method [MFC]
- OnPrint method [MFC]
- DoPreparePrinting method and pagination [MFC]
- OnDraw method [MFC], printing
- pagination [MFC], printing multipage documents
- printing [MFC], protocol
- pages [MFC], printing
- OnBeginPrinting method [MFC]
- multipage documents [MFC]
- printing [MFC], pagination
- documents [MFC], paginating
ms.assetid: 69626b86-73ac-4b74-b126-9955034835ef
ms.openlocfilehash: 7ef4267c311c1de516f75c3b54677adfbfaba5c9
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916434"
---
# <a name="multipage-documents"></a>다중 페이지 문서

이 문서에서는 Windows 인쇄 프로토콜을 설명 하 고 둘 이상의 페이지를 포함 하는 문서를 인쇄 하는 방법을 설명 합니다. 이 문서에서는 다음 항목을 다룹니다.

- [인쇄 프로토콜](#_core_the_printing_protocol)

- [뷰 클래스 함수 재정의](#_core_overriding_view_class_functions)

- [페이지 매김](#_core_pagination)

- [프린터 페이지 및 문서 페이지](#_core_printer_pages_vs.._document_pages)

- [인쇄 시간 페이지 매김](#_core_print.2d.time_pagination)

##  <a name="_core_the_printing_protocol"></a>인쇄 프로토콜

다중 페이지 문서를 인쇄 하기 위해 프레임 워크와 뷰는 다음과 같은 방식으로 상호 작용 합니다. 먼저 프레임 워크는 **인쇄** 대화 상자를 표시 하 고, 프린터에 대 한 장치 컨텍스트를 만들며, [CDC](../mfc/reference/cdc-class.md) 개체의 [startdoc](../mfc/reference/cdc-class.md#startdoc) 멤버 함수를 호출 합니다. 그런 다음 문서의 각 페이지에 대해 프레임 워크는 `CDC` 개체의 [StartPage](../mfc/reference/cdc-class.md#startpage) 멤버 함수를 호출 하 고, 뷰 개체에 페이지를 인쇄 하도록 지시 하 고, [endpage](../mfc/reference/cdc-class.md#endpage) 멤버 함수를 호출 합니다. 특정 페이지를 시작 하기 전에 프린터 모드를 변경 해야 하는 경우 뷰는 [Resetdc](../mfc/reference/cdc-class.md#resetdc)를 호출 하며,이는 새 프린터 모드 정보를 포함 하는 [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) 구조를 업데이트 합니다. 전체 문서를 인쇄 하면 프레임 워크에서 [Enddoc](../mfc/reference/cdc-class.md#enddoc) 멤버 함수를 호출 합니다.

##  <a name="_core_overriding_view_class_functions"></a>뷰 클래스 함수 재정의

[CView](../mfc/reference/cview-class.md) 클래스는 인쇄 하는 동안 프레임 워크에서 호출 하는 여러 멤버 함수를 정의 합니다. 뷰 클래스에서 이러한 함수를 재정의 하 여 프레임 워크의 인쇄 논리와 뷰 클래스의 인쇄 논리 사이에 연결을 제공 합니다. 다음 표에서는 이러한 멤버 함수를 보여 줍니다.

### <a name="cviews-overridable-functions-for-printing"></a>인쇄용으로 재정의 가능한 CView 함수

|이름|재정의 이유|
|----------|---------------------------|
|[OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting)|인쇄 대화 상자, 특히 문서의 길이에 값을 삽입 하려면|
|[OnBeginPrinting](../mfc/reference/cview-class.md#onbeginprinting)|글꼴이 나 기타 GDI 리소스를 할당 하려면|
|[OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc)|지정 된 페이지에 대 한 장치 컨텍스트의 특성을 조정 하거나 인쇄 시간 페이지 매김을 수행 하려면|
|[OnPrint](../mfc/reference/cview-class.md#onprint)|지정 된 페이지를 인쇄 하려면|
|[OnEndPrinting](../mfc/reference/cview-class.md#onendprinting)|GDI 리소스 할당을 취소 하려면|

다른 함수 에서도 인쇄 관련 처리를 수행할 수 있지만 이러한 함수는 인쇄 프로세스를 구동 하는 함수입니다.

다음 그림에서는 인쇄 프로세스와 관련 된 단계를 보여 주고 각 `CView`의 인쇄 멤버 함수가 호출 되는 위치를 보여 줍니다. 이 문서의 나머지 부분에서는 이러한 단계에 대해 자세히 설명 합니다. 인쇄 프로세스의 추가 부분은 [GDI 리소스 할당](../mfc/allocating-gdi-resources.md)문서에 설명 되어 있습니다.

![루프 프로세스 인쇄](../mfc/media/vc37c71.gif "루프 프로세스 인쇄") <br/>
인쇄 루프

##  <a name="_core_pagination"></a> 페이지 매김

프레임 워크는 인쇄 작업에 대 한 많은 정보를 [Cprintinfo](../mfc/reference/cprintinfo-structure.md) 구조에 저장 합니다. 의 `CPrintInfo` 일부 값은 페이지 매김과 관련이 있습니다. 이러한 값은 다음 표에 나와 있는 것 처럼 액세스할 수 있습니다.

### <a name="page-number-information-stored-in-cprintinfo"></a>CPrintInfo에 저장 된 페이지 번호 정보

|멤버 변수 또는<br /><br /> 함수 이름|참조 된 페이지 번호|
|-----------------------------------------------|----------------------------|
|`GetMinPage`/`SetMinPage`|문서의 첫 페이지|
|`GetMaxPage`/`SetMaxPage`|문서의 마지막 페이지|
|`GetFromPage`|인쇄할 첫 페이지|
|`GetToPage`|인쇄할 마지막 페이지|
|`m_nCurPage`|현재 인쇄 중인 페이지|

페이지 번호는 1부터 시작 합니다. 즉, 첫 번째 페이지의 번호는 0이 아니라 1입니다. 이러한 멤버 및 [Cprintinfo](../mfc/reference/cprintinfo-structure.md)의 다른 멤버에 대 한 자세한 내용은 *MFC 참조*를 참조 하세요.

인쇄 프로세스의 시작 부분에서 프레임 워크는 뷰의 [onprepareprinting](../mfc/reference/cview-class.md#onprepareprinting) 멤버 함수를 호출 하 여 `CPrintInfo` 구조체에 대 한 포인터를 전달 합니다. 응용 프로그램 마법사는의 `OnPreparePrinting` `CView`다른 멤버 함수인 [doprepareprinting](../mfc/reference/cview-class.md#doprepareprinting)를 호출 하는의 구현을 제공 합니다. `DoPreparePrinting`는 인쇄 대화 상자를 표시 하 고 프린터 장치 컨텍스트를 만드는 함수입니다.

이 시점에서 응용 프로그램은 문서에 있는 페이지 수를 알 수 없습니다. 문서의 첫 페이지와 마지막 페이지의 숫자에 기본값 1과 0xFFFF를 사용 합니다. 문서에 있는 페이지 수를 알고 있는 경우로 `OnPreparePrinting` `DoPreparePrinting`보내기 전에 `CPrintInfo` 구조에 대해 [setmaxpage]--brokenlink--(reference/cprintinfo-class. md # setmaxpage)를 재정의 하 고 호출 합니다. 이렇게 하면 문서의 길이를 지정할 수 있습니다.

`DoPreparePrinting`그런 다음 인쇄 대화 상자를 표시 합니다. 반환 될 때 구조체에 `CPrintInfo` 는 사용자가 지정한 값이 포함 됩니다. 사용자가 선택 된 페이지 범위만 인쇄 하려는 경우 인쇄 대화 상자에서 시작 및 끝 페이지 번호를 지정할 수 있습니다. 프레임 워크는 [cprintinfo](../mfc/reference/cprintinfo-structure.md)의 `GetFromPage` 및 `GetToPage` 함수를 사용 하 여 이러한 값을 검색 합니다. 사용자가 페이지 범위를 지정 하지 않은 경우 프레임 워크는 `GetMinPage` 및 `GetMaxPage` 를 호출 하 고 반환 된 값을 사용 하 여 전체 문서를 인쇄 합니다.

인쇄 될 문서의 각 페이지에 대해 프레임 워크는 view 클래스의 두 멤버 함수 [Onpreparedc](../mfc/reference/cview-class.md#onpreparedc) 및 [OnPrint](../mfc/reference/cview-class.md#onprint)를 호출 하 고 각 함수에 두 개의 매개 변수를 전달 합니다. [CDC](../mfc/reference/cdc-class.md) 개체에 대 `CPrintInfo` 한 포인터와에 대 한 포인터입니다. 구조체나. 프레임 워크 `OnPrepareDC` 는 및 `OnPrint`를 호출할 때마다 `CPrintInfo` 구조체의 *m_nCurPage* 멤버에 다른 값을 전달 합니다. 이러한 방식으로 프레임 워크는 인쇄할 페이지를 표시 합니다.

[Onpreparedc](../mfc/reference/cview-class.md#onpreparedc) 구성원 함수는 화면 표시에도 사용 됩니다. 그리기를 수행 하기 전에 장치 컨텍스트에 대 한 조정을 수행 합니다. `OnPrepareDC`는 인쇄에서 비슷한 역할을 수행 하지만 두 가지 차이점이 있습니다. 첫째, 개체는 `CDC` 화면 장치 컨텍스트 대신 프린터 장치 컨텍스트를 나타내고 `CPrintInfo` , 두 번째는 개체를 두 번째 매개 변수로 전달 합니다. 이 매개 변수는 가 화면 `OnPrepareDC` 표시를 위해 호출 될 때 NULL입니다. 인쇄 `OnPrepareDC` 중인 페이지를 기준으로 장치 컨텍스트를 조정 하려면를 재정의 합니다. 예를 들어 뷰포트 원점 및 클리핑 영역을 이동 하 여 문서의 적절 한 부분이 인쇄 되도록 할 수 있습니다.

[OnPrint](../mfc/reference/cview-class.md#onprint) 멤버 함수는 페이지의 실제 인쇄를 수행 합니다. [기본 인쇄를 수행 하는 방법](../mfc/how-default-printing-is-done.md) 에 대 한 문서는 프레임 워크가 인쇄를 수행 하기 위해 프린터 장치 컨텍스트와 함께 [OnDraw](../mfc/reference/cview-class.md#ondraw) 를 호출 하는 방법을 보여 줍니다. 보다 정확 하 게 말하자면 프레임 `OnPrint` 워크는 `CPrintInfo` 구조체와 장치 컨텍스트를 사용 하 `OnPrint` 여를 호출 하 고 `OnDraw`장치 컨텍스트를에 전달 합니다. 화면 `OnPrint` 을 표시 하지 않고 인쇄 중에만 수행 해야 하는 렌더링을 수행 하려면를 재정의 합니다. 예를 들어 머리글이 나 바닥글을 인쇄 하려면 (자세한 내용은 [머리글 및 바닥글](../mfc/headers-and-footers.md) 문서 참조)를 참조 하세요. 그런 다음 `OnDraw` `OnPrint` 재정의에서를 호출 하 여 화면 표시와 인쇄 모두에 공통적인 렌더링을 수행 합니다.

화면 표시와 `OnDraw` 인쇄에 대 한 렌더링을 수행 하는 사실은 응용 프로그램이 WYSIWYG 임을 의미 합니다. "표시 되는 항목은 무엇 인가요?" 그러나 WYSIWYG 응용 프로그램을 작성 하지 않는 것으로 가정 합니다. 예를 들어 텍스트 편집기를 사용 하 여 인쇄 하는 경우 텍스트 편집기를 사용 하 여 화면에 굵은 텍스트를 나타내는 컨트롤 코드를 표시 합니다. 이러한 상황에서는 화면 표시에 대해 `OnDraw` 엄격 하 게를 사용 합니다. 을 재정의 `OnPrint`하는 경우 `OnDraw` 호출을 별도의 그리기 함수에 대 한 호출로 대체 합니다. 이 함수는 화면에 표시 되지 않는 특성을 사용 하 여 문서를 용지에 표시 되는 방식으로 그립니다.

##  <a name="_core_printer_pages_vs.._document_pages"></a>프린터 페이지 및 문서 페이지

페이지 번호를 참조 하는 경우에는 페이지의 프린터 개념과 문서의 페이지 개념을 구분 해야 하는 경우가 있습니다. 프린터의 관점에서 페이지는 용지 한 장입니다. 그러나 용지 한 곳에는 문서의 한 페이지가 반드시 일치 하지는 않습니다. 예를 들어, 용지를 접을 회보를 인쇄 하는 경우 한 용지는 문서의 첫 페이지와 마지막 페이지를 나란히 포함할 수 있습니다. 마찬가지로 스프레드시트를 인쇄 하는 경우 문서는 페이지로 구성 되지 않습니다. 대신, 용지 한 곳에는 열 1 ~ 20, 열 6부터 10까지 포함 될 수 있습니다.

[Cprintinfo](../mfc/reference/cprintinfo-structure.md) 구조의 모든 페이지 번호는 프린터 페이지를 참조 합니다. 프레임 워크는 `OnPrepareDC` 프린터 `OnPrint` 를 통과 하는 각 용지에 대해 및를 한 번씩 호출 합니다. [Onprepareprinting](../mfc/reference/cview-class.md#onprepareprinting) 함수를 재정의 하 여 문서의 길이를 지정 하는 경우 프린터 페이지를 사용 해야 합니다. 일대일 대응이 있는 경우 (즉, 하나의 프린터 페이지가 하나의 문서 페이지와 같음)이는 간단 합니다. 반면에 문서 페이지와 프린터 페이지가 직접 일치 하지 않는 경우에는 둘 사이를 변환 해야 합니다. 예를 들어 스프레드시트를 인쇄 하는 것이 좋습니다. 재정의할 `OnPreparePrinting`때 전체 스프레드시트를 인쇄 하는 데 필요한 용지 수를 계산한 다음의 `CPrintInfo`멤버 함수를 `SetMaxPage` 호출할 때이 값을 사용 해야 합니다. 마찬가지로를 재정의할 `OnPrepareDC`때 *m_nCurPage* 를 특정 시트에 표시 되는 행 및 열 범위로 변환한 다음 그에 따라 뷰포트 원본을 조정 해야 합니다.

##  <a name="_core_print.2d.time_pagination"></a>인쇄 시간 페이지 매김

일부 경우에는 보기 클래스가 실제로 인쇄 될 때까지 문서를 미리 알 수 없습니다. 예를 들어 응용 프로그램이 WYSIWYG가 아니면 화면에서 문서의 길이가 인쇄 될 때의 길이와 일치 하지 않는 것으로 가정 합니다.

이로 인해 뷰 클래스에 대해 [onprepareprinting](../mfc/reference/cview-class.md#onprepareprinting) 를 재정의할 때 문제가 발생 합니다. 문서 길이를 몰라도 `SetMaxPage` [cprintinfo](../mfc/reference/cprintinfo-structure.md) 구조의 함수에 값을 전달할 수 없습니다. 사용자가 인쇄 대화 상자를 사용 하 여 중지할 페이지 번호를 지정 하지 않은 경우 프레임 워크에서 인쇄 루프를 중지할 시기를 알지 못합니다. 인쇄 루프를 중지할 시기를 결정 하는 방법은 문서를 인쇄 하 고 종료 될 때를 확인 하는 것입니다. 보기 클래스는 문서를 인쇄 하는 동안 문서의 끝을 확인 한 다음 끝에 도달할 때 프레임 워크에 알립니다.

프레임 워크는 뷰 클래스의 [Onpreparedc](../mfc/reference/cview-class.md#onpreparedc) 함수를 사용 하 여 중지할 때이를 알립니다. 를 `OnPrepareDC`호출한 후 프레임 워크는 *m_bContinuePrinting*라는 `CPrintInfo` 구조체의 멤버를 확인 합니다. 기본값은 **TRUE입니다.** 남아 있는 한 프레임 워크는 인쇄 루프를 계속 합니다. **FALSE**로 설정 된 경우 프레임 워크는 중지 됩니다. 인쇄 시간 페이지 매김을 수행 하려면를 재정의 `OnPrepareDC` 하 여 문서의 끝에 도달 했는지 여부를 확인 하 고, *m_bContinuePrinting* 을 **FALSE** 로 설정 합니다.

현재 페이지가 1 보다 `OnPrepareDC` 큰 경우의 기본 구현은 *m_bContinuePrinting* 을 **FALSE** 로 설정 합니다. 즉, 문서의 길이가 지정 되지 않은 경우 프레임 워크는 문서가 한 페이지 긴 것으로 가정 합니다. 이에 대 한 한 가지 결과는의 `OnPrepareDC`기본 클래스 버전을 호출 하는 경우 주의 해야 한다는 것입니다. 기본 클래스 버전을 호출한 후 *m_bContinuePrinting* 가 **TRUE** 가 된다고 가정 하지 마십시오.

### <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [머리글 및 바닥글](../mfc/headers-and-footers.md)

- [GDI 리소스 할당](../mfc/allocating-gdi-resources.md)

## <a name="see-also"></a>참고자료

[인쇄](../mfc/printing.md)<br/>
[CView 클래스](../mfc/reference/cview-class.md)<br/>
[CDC 클래스](../mfc/reference/cdc-class.md)
