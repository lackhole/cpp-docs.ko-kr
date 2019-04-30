---
title: DDX_DHtml 도우미 매크로
ms.date: 11/04/2016
f1_keywords:
- AFXDHTML/DDX_DHtml_ElementValue
- AFXDHTML/DDX_DHtml_ElementInnerText
- AFXDHTML/DDX_DHtml_ElementInnerHtml
- AFXDHTML/DDX_DHtml_Anchor_Href
- AFXDHTML/DDX_DHtml_Anchor_Target
- AFXDHTML/DDX_DHtml_Img_Src
- AFXDHTML/DDX_DHtml_Frame_Src
- AFXDHTML/DDX_DHtml_IFrame_Src
helpviewer_keywords:
- macros [MFC], exchanging data with HMTL pages
- DDX macros [MFC]
- HTML pages [MFC], helper macros
- DDX (dialog data exchange), DHtml helper macros
- macros [MFC], DDX_DHtml helpers
ms.assetid: c46302d2-ea43-4fea-bfc2-6f590d99f267
ms.openlocfilehash: 90c80dbc5c8b6788f3afad3cf77d796139fbd946
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323036"
---
# <a name="ddxdhtml-helper-macros"></a>DDX_DHtml 도우미 매크로

DDX_DHtml 도우미 매크로는 HTML 페이지에 있는 컨트롤의 자주 사용 되는 속성에 쉽게 액세스할 수 있도록 합니다.

### <a name="data-exchange-macros"></a>데이터 교환 매크로

|||
|-|-|
|[DDX_DHtml_ElementValue](#ddx_dhtml_elementvalue)|설정 하거나 선택한 컨트롤에서 값 속성을 검색 합니다.|
|[DDX_DHtml_ElementInnerText](#ddx_dhtml_elementinnertext)|설정 하거나 현재 요소의 시작 및 끝 태그 사이의 텍스트를 검색 합니다.|
|[DDX_DHtml_ElementInnerHtml](#ddx_dhtml_elementinnerhtml)|설정 하거나 현재 요소의 시작 및 끝 태그 사이의 HTML을 검색 합니다.|
|[DDX_DHtml_Anchor_Href](#ddx_dhtml_anchor_href)|설정 하거나 대상 URL 또는 앵커 지점을 검색 합니다.|
|[DDX_DHtml_Anchor_Target](#ddx_dhtml_anchor_target)|설정 하거나 대상 창이 나 프레임을 검색 합니다.|
|[DDX_DHtml_Img_Src](#ddx_dhtml_img_src)|설정 하거나 이미지 또는 문서에서 비디오 클립의 이름을 검색 합니다.|
|[DDX_DHtml_Frame_Src](#ddx_dhtml_frame_src)|설정 하거나 연결된 된 프레임의 URL을 검색 합니다.|
|[DDX_DHtml_IFrame_Src](#ddx_dhtml_iframe_src)|설정 하거나 연결된 된 프레임의 URL을 검색 합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** afxdhtml.h

## <a name="ddx_dhtml_anchor_href"></a> DDX_DHtml_Anchor_Href

설정 하거나 대상 URL 또는 앵커 지점을 검색 합니다.

```
DDX_DHtml_Anchor_Href(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>매개 변수

*dx*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다.

*name*<br/>
HTML 컨트롤의 ID 매개 변수에 대해 지정 된 값입니다.

*var*<br/>
교환할 값입니다.

## <a name="remarks"></a>설명

이 매크로 호출 합니다 [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) 는 DISPID_IHTMLANCHORELEMENT_HREF를 사용 하 여 함수 디스패치 id입니다.

## <a name="ddx_dhtml_anchor_target"></a>  DDX_DHtml_Anchor_Target

설정 하거나 대상 창이 나 프레임을 검색 합니다.

```
DDX_DHtml_Anchor_Target(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>매개 변수

*dx*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다.

*name*<br/>
HTML 컨트롤의 ID 매개 변수에 대해 지정 된 값입니다.

*var*<br/>
교환할 값입니다.

## <a name="remarks"></a>설명

이 매크로 호출 합니다 [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) 는 DISPID_IHTMLANCHORELEMENT_TARGET를 사용 하 여 함수 디스패치 id입니다.

## <a name="ddx_dhtml_elementinnerhtml"></a>  DDX_DHtml_ElementInnerHtml

설정 하거나 현재 요소의 시작 및 끝 태그 사이의 HTML을 검색 합니다.

```
DDX_DHtml_ElementInnerHtml(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>매개 변수

*dx*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다.

*name*<br/>
HTML 컨트롤의 ID 매개 변수에 대해 지정 된 값입니다.

*var*<br/>
교환할 값입니다.

## <a name="remarks"></a>설명

이 매크로 호출 합니다 [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) 는 DISPID_IHTMLELEMENT_INNERHTML를 사용 하 여 함수 디스패치 id입니다.

## <a name="ddx_dhtml_elementinnertext"></a>  DDX_DHtml_ElementInnerText

설정 하거나 현재 요소의 시작 및 끝 태그 사이의 텍스트를 검색 합니다.

```
DDX_DHtml_ElementInnerText(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>매개 변수

*dx*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다.

*name*<br/>
HTML 컨트롤의 ID 매개 변수에 대해 지정 된 값입니다.

*var*<br/>
교환할 값입니다.

## <a name="remarks"></a>설명

이 매크로 호출 합니다 [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) 는 DISPID_IHTMLELEMENT_INNERTEXT를 사용 하 여 함수 디스패치 id입니다.

## <a name="ddx_dhtml_elementvalue"></a> DDX_DHtml_ElementValue

설정 하거나 선택한 컨트롤에서 값 속성을 검색 합니다.

```
DDX_DHtml_ElementValue(
    CDataExchange* dx,
    LPCTSTR name,
    var)
```

#### <a name="parameters"></a>매개 변수

*dx*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다.

*name*<br/>
HTML 컨트롤의 ID 매개 변수에 대해 지정 된 값입니다.

*var*<br/>
교환할 값입니다. 참조 *값* 에 [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext)합니다.

## <a name="remarks"></a>설명

이 매크로 Value 속성에 있는 컨트롤에서 실행 하는 경우에 성공할 수 있습니다. 값 속성이 있는 컨트롤에는 편집 상자, 목록 상자 및 콤보 상자 포함 됩니다.

이 매크로 호출 합니다 [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) 는 DISPID_A_VALUE를 사용 하 여 함수 디스패치 id입니다.

## <a name="ddx_dhtml_frame_src"></a> DDX_DHtml_Frame_Src

설정 하거나 연결된 된 프레임의 URL을 검색 합니다.

```
DDX_DHtml_Frame_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>매개 변수

*dx*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다.

*name*<br/>
HTML 컨트롤의 ID 매개 변수에 대해 지정 된 값입니다.

*var*<br/>
교환할 값입니다.

## <a name="remarks"></a>설명

이 매크로 호출 합니다 [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) 는 DISPID_IHTMLFRAMEBASE_SRC를 사용 하 여 함수 디스패치 id입니다.

## <a name="ddx_dhtml_iframe_src"></a> DDX_DHtml_IFrame_Src

설정 하거나 연결된 된 프레임의 URL을 검색 합니다.

```
DDX_DHtml_IFrame_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>매개 변수

*dx*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다.

*name*<br/>
HTML 컨트롤의 ID 매개 변수에 대해 지정 된 값입니다.

*var*<br/>
교환할 값입니다.

## <a name="remarks"></a>설명

이 매크로 호출 합니다 [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) 는 DISPID_IHTMLFRAMEBASE_SRC를 사용 하 여 함수 디스패치 id입니다.

## <a name="ddx_dhtml_img_src"></a>DDX_DHtml_Img_Src

이미지 또는 문서에서 비디오 클립의 이름을 검색 하거나 가져옵니다.

```
DDX_DHtml_Img_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>매개 변수

*dx*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다.

*name*<br/>
HTML 컨트롤의 ID 매개 변수에 대해 지정 된 값입니다.

*var*<br/>
교환할 값입니다.

## <a name="remarks"></a>설명

이미지 요소에 대 한 src 속성을 검색할 DDX_DHtml_Img_Src 매크로 사용 하는 경우 Internet Explorer 이미지 개체는 이미지 원본에 대 한 완전히 이스케이프 된 URL을 반환 합니다. 예를 들어 DDX_DHtml_Img_Src 매크로 사용 하 여 "몇 가지 흥미로운 그림" 문자열에는 IMAGE 요소의 src 속성을 설정 하는 경우 해당 속성에 Internet Explorer를 검색 하는 경우는 문자열을 반환할 "res://d:\myapplication\myapp.exe/some% 20interesting %20picture입니다. "

이 매크로 호출 합니다 [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) 는 DISPID_IHTMLIMGELEMENT_SRC를 사용 하 여 함수 디스패치 id입니다.

## <a name="see-also"></a>참고자료

[CDHtmlDialog 클래스](../../mfc/reference/cdhtmldialog-class.md)
