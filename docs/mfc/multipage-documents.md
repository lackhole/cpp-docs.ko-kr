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
ms.openlocfilehash: 81e03657977d31827c5c7c3d3272e3d4255a4a8b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62238493"
---
# <a name="multipage-documents"></a>다중 페이지 문서

이 문서에서는 Windows 인쇄 프로토콜 및 둘 이상의 페이지를 포함 하는 문서를 인쇄 하는 방법을 설명 합니다. 다음 항목을 다룹니다.

- [인쇄 프로토콜](#_core_the_printing_protocol)

- [뷰 클래스 함수를 재정의합니다.](#_core_overriding_view_class_functions)

- [페이지 매김](#_core_pagination)

- [문서 페이지와 프린터 페이지](#_core_printer_pages_vs.._document_pages)

- [인쇄할 때 페이지 매김](#_core_print.2d.time_pagination)

##  <a name="_core_the_printing_protocol"></a> 인쇄 프로토콜

다중 페이지 문서를 인쇄 하려면 프레임 워크와 뷰는 다음과 같은 방식으로 상호 작용 합니다. 먼저 프레임 워크가 표시는 **인쇄** 대화 상자에서 프린터 및 호출에 대 한 장치 컨텍스트를 만듭니다를 [StartDoc](../mfc/reference/cdc-class.md#startdoc) 멤버 함수는 [CDC](../mfc/reference/cdc-class.md) 개체입니다. 한 문서의 각 페이지에 대 한 프레임 워크에서 호출 합니다 [StartPage](../mfc/reference/cdc-class.md#startpage) 멤버 함수는 `CDC` 개체, 페이지 및 호출을 인쇄 하려면 뷰 개체에 지시를 [EndPage](../mfc/reference/cdc-class.md#endpage) 멤버 함수입니다. 뷰를 호출 하는 특정 페이지를 시작 하기 전에 프린터 모드를 변경 해야 합니다 [ResetDC](../mfc/reference/cdc-class.md#resetdc)를 업데이트 합니다 [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) 새 프린터 모드 정보를 포함 하는 구조입니다. 프레임 워크를 호출 하는 전체 문서를 인쇄 합니다 [EndDoc](../mfc/reference/cdc-class.md#enddoc) 멤버 함수입니다.

##  <a name="_core_overriding_view_class_functions"></a> 뷰 클래스 함수를 재정의합니다.

합니다 [CView](../mfc/reference/cview-class.md) 클래스 인쇄 하는 동안 프레임 워크에서 호출 되는 여러 멤버 함수를 정의 합니다. 뷰 클래스에서 이러한 함수를 재정의 하 여 프레임 워크의 인쇄 논리와 뷰 클래스의 인쇄 논리 간의 연결을 제공할 수 있습니다. 다음 표에서 이러한 멤버 함수를 나열합니다.

### <a name="cviews-overridable-functions-for-printing"></a>인쇄용 CView의 재정의 가능 함수

|이름|재정의 이유|
|----------|---------------------------|
|[OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting)|문서의 길이 특히 인쇄 대화 상자에서 값을 삽입 하려면|
|[OnBeginPrinting](../mfc/reference/cview-class.md#onbeginprinting)|글꼴 또는 기타 GDI 리소스 할당|
|[OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc)|지정된 된 페이지에 대 한 장치 컨텍스트의 특성을 조정 하거나 인쇄 때 페이지 번호 매기기를 위해|
|[OnPrint](../mfc/reference/cview-class.md#onprint)|지정 된 페이지를 인쇄 하려면|
|[OnEndPrinting](../mfc/reference/cview-class.md#onendprinting)|GDI 리소스 할당을 취소 하려면|

다른 함수 에서도 인쇄 관련 처리를 수행할 수 있습니다 하지만 이러한 함수는 인쇄 프로세스를 구동 하는 것입니다.

다음 그림 인쇄 프로세스에 관련 된 단계를 보여 줍니다 및 위치를 보여 줍니다. 각 `CView`멤버 함수가 호출 될 인쇄 합니다. 이 문서의 나머지 부분에서는 대부분의 이러한 단계를 자세히 설명합니다. 인쇄 프로세스의 추가 파트는 문서에 설명 되어 있습니다 [GDI 리소스 할당](../mfc/allocating-gdi-resources.md)합니다.

![루프 프로세스 인쇄](../mfc/media/vc37c71.gif "루프 프로세스 인쇄") <br/>
인쇄 루프

##  <a name="_core_pagination"></a> 페이지 매김

프레임 워크에서 인쇄 작업에 대 한 정보를 많이 저장 된 [CPrintInfo](../mfc/reference/cprintinfo-structure.md) 구조입니다. 에 있는 값의 여러 `CPrintInfo` 페이지 매김과 관련; 이러한 값은 다음 표에 나와 있는 것 처럼 액세스할 수 있습니다.

### <a name="page-number-information-stored-in-cprintinfo"></a>CPrintInfo에 저장 된 페이지 번호 정보

|멤버 변수 또는<br /><br /> 함수 이름|참조 된 페이지 번호|
|-----------------------------------------------|----------------------------|
|`GetMinPage`/`SetMinPage`|문서의 첫 번째 페이지|
|`GetMaxPage`/`SetMaxPage`|문서의 마지막 페이지|
|`GetFromPage`|인쇄할 첫 페이지|
|`GetToPage`|인쇄할 마지막 페이지|
|`m_nCurPage`|현재 인쇄 중인 페이지|

페이지 번호는 1에서 시작, 첫 번째 페이지 번호가 지정 됩니다 1, 0이 아닌. 다른 멤버에 대 한 자세한 내용은 [CPrintInfo](../mfc/reference/cprintinfo-structure.md)를 참조 합니다 *MFC 참조*합니다.

프레임 워크가 인쇄 프로세스를 시작할 때 뷰를 호출 [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) 에 대 한 포인터를 전달 하는 멤버 함수는 `CPrintInfo` 구조입니다. 응용 프로그램 마법사의 구현을 제공 `OnPreparePrinting` 를 호출 하는 [DoPreparePrinting](../mfc/reference/cview-class.md#doprepareprinting)의 다른 멤버 함수인 `CView`합니다. `DoPreparePrinting` 프린터 장치 컨텍스트를 만들고 인쇄 대화 상자를 표시 하는 함수가입니다.

이 시점에서 응용 프로그램 문서의 페이지 수는 알 수 없습니다. 기본값 1 및 0xFFFF 문서의 첫 번째 및 마지막 페이지 번호를 사용합니다. 문서에는 페이지 수를 알고 있는 경우 재정의 `OnPreparePrinting` 호출 [SetMaxPage]--brokenlink--(reference/cprintinfo-class.md#setmaxpage)에 대 한 합니다 `CPrintInfo` 구조체를 보내기 전에 `DoPreparePrinting`입니다. 이 문서의 길이 지정할 수 있습니다.

`DoPreparePrinting` 인쇄 대화 상자를 표시합니다. 반환 시는 `CPrintInfo` 구조는 사용자가 지정한 값을 포함 합니다. 선택한 범위의 페이지를 인쇄 하려는 경우 자신이 시작 및 끝 페이지 번호 인쇄 대화 상자에서 지정할 수 있습니다. 프레임 워크를 사용 하 여 이러한 값을 검색 합니다 `GetFromPage` 하 고 `GetToPage` 함수의 [CPrintInfo](../mfc/reference/cprintinfo-structure.md)합니다. 프레임 워크를 호출 하는 사용자 페이지 범위를 지정 하지 않으면 `GetMinPage` 고 `GetMaxPage` 전체 문서를 인쇄 하려면 반환 값을 사용 합니다.

인쇄할 문서의 각 페이지에 대 한 프레임 워크가 뷰 클래스에서 두 멤버 함수를 호출 [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) 하 고 [OnPrint](../mfc/reference/cview-class.md#onprint), 각 함수에 두 개의 매개 변수 전달:에 대 한 포인터를 [ CDC](../mfc/reference/cdc-class.md) 개체에 대 한 포인터를 `CPrintInfo` 구조입니다. 프레임 워크 호출 될 때마다 `OnPrepareDC` 및 `OnPrint`에서 다른 값을 전달 합니다 *m_nCurPage* 의 멤버는 `CPrintInfo` 구조입니다. 이러한 방식으로 프레임 워크는 페이지를 인쇄 해야를 뷰에 알려 줍니다.

합니다 [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) 멤버 함수는 화면 표시에도 사용 됩니다. 그리기를 수행 하기 전에 장치 컨텍스트를 조정을 합니다. `OnPrepareDC` 인쇄에 비슷한 역할을 제공 되지만 몇 가지 차이가: 먼저 합니다 `CDC` 개체 화면 장치 컨텍스트 및 두 번째 대신 프린터 장치 컨텍스트를 나타냅니다는 `CPrintInfo` 개체가 두 번째 매개 변수로 전달 됩니다. (이 매개 변수가 **NULL** 때 `OnPrepareDC` 화면 표시에 대해 호출 됩니다.) 재정의 `OnPrepareDC` 인쇄 되는 페이지에 따라 장치 컨텍스트를 조정 합니다. 예를 들어 뷰포트 원본과 문서의 적절 한 부분을 가져옵니다 인쇄 되도록 하려면 클리핑 영역을 이동할 수 있습니다.

합니다 [OnPrint](../mfc/reference/cview-class.md#onprint) 멤버 함수는 페이지의 실제 인쇄를 수행 합니다. 이 문서 [기본 인쇄 수행 되는 방법](../mfc/how-default-printing-is-done.md) 프레임 워크를 호출 하는 방법을 보여 줍니다 [OnDraw](../mfc/reference/cview-class.md#ondraw) 인쇄를 수행 하는 프린터 장치 컨텍스트를 사용 하 여 합니다. 프레임 워크 호출 보다 정확 하 게 `OnPrint` 사용 하 여는 `CPrintInfo` 구조 및 장치 컨텍스트, 및 `OnPrint` 장치 컨텍스트를 전달 `OnDraw`합니다. 재정의 `OnPrint` 화면 표시 하지 않고에 인쇄 하는 동안에 수행 해야 하는 모든 렌더링을 수행 합니다. 예를 들어, 헤더 또는 바닥글을 인쇄 하려면 (문서를 참조 하세요 [머리글 및 바닥글](../mfc/headers-and-footers.md) 자세한). 그런 다음 호출 `OnDraw` 재정의에서 `OnPrint` 모두 화면 표시에 공통적으로 적용 렌더링과 인쇄 작업을 수행 하 합니다.

팩트는 `OnDraw` 모두 화면 표시 및 인쇄 응용 프로그램 WYSIWYG 임을 의미에 대 한 렌더링을 수행 합니다. "표시 얻게 됩니다." 그러나 wysiwyg (위지윅) 응용 프로그램을 작성 하지는 것으로 가정 합니다. 예를 들어 텍스트 편집기 인쇄에 대 한 굵은 글꼴을 사용 하는 화면에서 굵은 텍스트를 나타내는 컨트롤 코드를 표시 합니다. 이러한 상황에서는 사용 하 여 `OnDraw` 화면 표시를 위해 엄격 하 게 합니다. 재정의 하는 경우 `OnPrint`에 대 한 호출을 대체 `OnDraw` 별도 그리기 함수를 호출 하 여 합니다. 해당 함수는 화면에 표시 하지 않는 특성을 사용 하는 문서에 표시 되는 문서를 그립니다.

##  <a name="_core_printer_pages_vs.._document_pages"></a> 프린터 페이지 vs입니다. 문서 페이지

페이지 번호를 참조 하는 경우 페이지의 프린터의 개념 및 페이지의 문서의 개념을 구분 하는 경우가 있습니다. 프린터의 관점에서 페이지 용지 한 면 됩니다. 그러나 한 장의 용지 문서의 한 페이지를 반드시 같지 않음. 예를 들어 있는 시트를 접을 수 하려는, 뉴스레터, 인쇄 하는 경우 한 장의 용지 나란히 문서의 첫 번째 및 마지막 페이지를 포함할 수 있습니다. 마찬가지로, 스프레드시트, 인쇄 하는 경우 문서 구성 되지 않습니다 페이지 전혀 합니다. 대신, 용지 한 면 1-20 열 6 ~ 10 행을 포함할 수 있습니다.

숫자를 모든 페이지의 [CPrintInfo](../mfc/reference/cprintinfo-structure.md) 구조 프린터 페이지를 참조 하십시오. 프레임 워크 호출 `OnPrepareDC` 고 `OnPrint` 프린터 전달 하는 문서의 각 시트에 한 번씩입니다. 재정의 하는 경우는 [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) 문서 길이 지정 하는 함수, 프린터 페이지를 사용 해야 합니다. 한 일 대응 하는 경우 (즉, 한 프린터 페이지는 한 문서 페이지 같음) 간단 합니다. 반면에 문서 페이지와 프린터 페이지 직접 대응 되지 않으면, 경우에 서로 변환 해야 합니다. 예를 들어 스프레드시트를 인쇄 하는 것이 좋습니다. 재정의 하는 경우 `OnPreparePrinting`, 전체 스프레드시트가 인쇄를 호출 하는 경우 해당 값을 사용할 수 장의 용지 해야 계산 해야 합니다 `SetMaxPage` 멤버 함수 `CPrintInfo`합니다. 마찬가지로, 재정의 하는 경우 `OnPrepareDC`를 변환 해야 *m_nCurPage* 광범위 한 해당 특정 시트에 표시 되며 다음 뷰포트 origin을 적절 하 게 조정 하는 행과 열을 합니다.

##  <a name="_core_print.2d.time_pagination"></a> 인쇄할 때 페이지 매김

상황에 따라 뷰 클래스 모를 수 미리 기간 문서가 실제로 인쇄 될 때까지 합니다. 예를 들어, 응용 프로그램 WYSIWYG이 아니라고 가정 하므로 화면에서 문서 길이 일치 하지 않습니다 인쇄 하는 경우 해당 길이입니다.

재정의 하는 경우 이렇게 하면 문제가 [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) 뷰 클래스에 대 한: 값을 전달할 수 없습니다는 `SetMaxPage` 함수를 [CPrintInfo](../mfc/reference/cprintinfo-structure.md) 의 길이 알 수 없으므로 구조체를 문서입니다. 사용자가 인쇄 대화 상자를 사용 하 여 중지 하는 페이지 번호를 지정 하지 않으면 프레임 워크가 인쇄 루프를 중지 하는 경우를 알지 못합니다. 인쇄 루프를 중지할 시기를 결정 하는 유일한 방법은 문서 인쇄를 종료 될 때 참조 됩니다. 뷰 클래스 끝에 도달한 경우 프레임 워크를 알리기 위해 다음 인쇄 하는 동안 문서 끝에 대 한 확인 해야 합니다.

뷰 클래스의 의존 하는 프레임 워크 [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) 함수를 알려 주기를 중지 하는 경우. 호출한 후 `OnPrepareDC`, 프레임 워크의 멤버를 확인 합니다 `CPrintInfo` 라는 구조 *m_bContinuePrinting*합니다. 기본값은 **TRUE입니다.** 해으로 프레임 워크가 인쇄 루프를 계속 합니다. 로 설정 된 경우 **FALSE**, 프레임 워크 중지 합니다. 인쇄 때 페이지 번호 매기기를 수행 하려면 재정의 `OnPrepareDC` 문서 끝에 도달 하 고 설정 여부를 확인 하려면 *m_bContinuePrinting* 하려면 **FALSE** 했을 때.

기본 구현의 `OnPrepareDC` 설정 *m_bContinuePrinting* 하려면 **FALSE** 현재 페이지 1 보다 큰 경우. 이 문서 길이 지정 하지 않으면 프레임 워크를 가정 문서 길이 한 페이지로 것을 의미 합니다. 이 기본 클래스 버전을 호출 하는 경우 주의 해야 하는 `OnPrepareDC`합니다. 이라고 단정 하지 마십시오 *m_bContinuePrinting* 됩니다 **TRUE** 기본 클래스 버전을 호출한 후입니다.

### <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [머리글 및 바닥글](../mfc/headers-and-footers.md)

- [GDI 리소스 할당](../mfc/allocating-gdi-resources.md)

## <a name="see-also"></a>참고자료

[인쇄](../mfc/printing.md)<br/>
[CView 클래스](../mfc/reference/cview-class.md)<br/>
[CDC 클래스](../mfc/reference/cdc-class.md)
