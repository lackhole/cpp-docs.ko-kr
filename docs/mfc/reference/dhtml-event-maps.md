---
title: DHTML 이벤트 맵
ms.date: 11/04/2016
f1_keywords:
- vc.macros.shared
helpviewer_keywords:
- event map macros [MFC]
- DHTML [MFC], event map macros
- macros [MFC], DHTML event map
- DHTML events [MFC], event map
- DHTML events [MFC]
ms.assetid: 9a2c8ae7-7216-4a5e-bc60-6b98695be0c6
ms.openlocfilehash: 5ae37acd3e0b0c2636e6a3e985490a2feab8fa34
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62322815"
---
# <a name="dhtml-event-maps"></a>DHTML 이벤트 맵

DHTML 이벤트를 처리 하려면 다음 매크로 사용할 수 있습니다.

## <a name="dhtml-event-map-macros"></a>DHTML 이벤트 맵 매크로

다음 매크로 사용 하 여에 DHTML 이벤트를 처리할 수 있습니다 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)-클래스를 파생 합니다.

|||
|-|-|
|[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)|DHTML 이벤트 맵의 시작을 표시 합니다.|
|[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)|DHTML 이벤트 맵의 시작을 표시 합니다.|
|[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)|DHTML 이벤트 맵을 선언합니다.|
|[DHTML_EVENT](#dhtml_event)|단일 HTML 요소에 대 한 문서 수준에서 이벤트를 처리 하는 데 사용 합니다.|
|[DHTML_EVENT_AXCONTROL](#dhtml_event_axcontrol)|ActiveX 컨트롤에 의해 발생 하는 이벤트를 처리 하는 데 사용 합니다.|
|[DHTML_EVENT_CLASS](#dhtml_event_class)|특정 CSS 클래스를 사용 하 여 모든 HTML 요소에 대 한 문서 수준에서 이벤트를 처리 하는 데 사용 합니다.|
|[DHTML_EVENT_ELEMENT](#dhtml_event_element)|요소 수준에서 이벤트를 처리 하는 데 사용 합니다.|
|[DHTML_EVENT_ONAFTERUPDATE](#dhtml_event_onafterupdate)|처리 하는 데 사용 된 `onafterupdate` HTML 요소에서 이벤트입니다.|
|[DHTML_EVENT_ONBEFOREUPDATE](#dhtml_event_onbeforeupdate)|처리 하는 데 사용 된 `onbeforeupdate` HTML 요소에서 이벤트입니다.|
|[DHTML_EVENT_ONBLUR](#dhtml_event_onblur)|처리 하는 데 사용 된 `onblur` HTML 요소에서 이벤트입니다.|
|[DHTML_EVENT_ONCHANGE](#dhtml_event_onchange)|처리 하는 데 사용 된 `onchange` HTML 요소에서 이벤트입니다.|
|[DHTML_EVENT_ONCLICK](#dhtml_event_onclick)|처리 하는 데 사용 된 `onclick` HTML 요소에서 이벤트입니다.|
|[DHTML_EVENT_ONDATAAVAILABLE](#dhtml_event_ondataavailable)|처리 하는 데 사용 된 `ondataavailable` HTML 요소에서 이벤트입니다.|
|[DHTML_EVENT_ONDATASETCHANGED](#dhtml_event_ondatasetchanged)|처리 하는 데 사용 된 `ondatasetchanged` HTML 요소에서 이벤트입니다.|
|[DHTML_EVENT_ONDATASETCOMPLETE](#dhtml_event_ondatasetcomplete)|처리 하는 데 사용 된 `ondatasetcomplete` HTML 요소에서 이벤트입니다.|
|[DHTML_EVENT_ONDBLCLICK](#dhtml_event_ondblclick)|처리 하는 데 사용 된 `ondblclick` HTML 요소에서 이벤트입니다.|
|[DHTML_EVENT_ONDRAGSTART](#dhtml_event_ondragstart)|처리 하는 데 사용 된 `ondragstart` HTML 요소에서 이벤트입니다.|
|[DHTML_EVENT_ONERRORUPDATE](#dhtml_event_onerrorupdate)|처리 하는 데 사용 된 `onerrorupdate` HTML 요소에서 이벤트입니다.|
|[DHTML_EVENT_ONFILTERCHANGE](#dhtml_event_onfilterchange)|처리 하는 데 사용 된 `onfilterchange` HTML 요소에서 이벤트입니다.|
|[DHTML_EVENT_ONFOCUS](#dhtml_event_onfocus)|처리 하는 데 사용 된 `onfocus` HTML 요소에서 이벤트입니다.|
|[DHTML_EVENT_ONHELP](#dhtml_event_onhelp)|처리 하는 데 사용 된 `onhelp` HTML 요소에서 이벤트입니다.|
|[DHTML_EVENT_ONKEYDOWN](#dhtml_event_onkeydown)|처리 하는 데 사용 된 `onkeydown` HTML 요소에서 이벤트입니다.|
|[DHTML_EVENT_ONKEYPRESS](#dhtml_event_onkeypress)|처리 하는 데 사용 된 `onkeypress` HTML 요소에서 이벤트입니다.|
|[DHTML_EVENT_ONKEYUP](#dhtml_event_onkeyup)|처리 하는 데 사용 된 `onkeyup` HTML 요소에서 이벤트입니다.|
|[DHTML_EVENT_ONMOUSEDOWN](#dhtml_event_onmousedown)|처리 하는 데 사용 된 `onmousedown` HTML 요소에서 이벤트입니다.|
|[DHTML_EVENT_ONMOUSEMOVE](#dhtml_event_onmousemove)|처리 하는 데 사용 된 `onmousemove` HTML 요소에서 이벤트입니다.|
|[DHTML_EVENT_ONMOUSEOUT](#dhtml_event_onmouseout)|처리 하는 데 사용 된 `onmouseout` HTML 요소에서 이벤트입니다.|
|[DHTML_EVENT_ONMOUSEOVER](#dhtml_event_onmouseover)|처리 하는 데 사용 된 `onmouseover` HTML 요소에서 이벤트입니다.|
|[DHTML_EVENT_ONMOUSEUP](#dhtml_event_onmouseup)|처리 하는 데 사용 된 `onmouseup` HTML 요소에서 이벤트입니다.|
|[DHTML_EVENT_ONRESIZE](#dhtml_event_onresize)|처리 하는 데 사용 된 `onresize` HTML 요소에서 이벤트입니다.|
|[DHTML_EVENT_ONROWENTER](#dhtml_event_onrowenter)|처리 하는 데 사용 된 `onrowenter` HTML 요소에서 이벤트입니다.|
|[DHTML_EVENT_ONROWEXIT](#dhtml_event_onrowexit)|처리 하는 데 사용 된 `onrowexit` HTML 요소에서 이벤트입니다.|
|[DHTML_EVENT_ONSELECTSTART](#dhtml_event_onselectstart)|처리 하는 데 사용 된 `onselectstart` HTML 요소에서 이벤트입니다.|
|[DHTML_EVENT_TAG](#dhtml_event_tag)|특정 HTML 태그를 사용 하 여 모든 요소에 대 한 문서 수준에서 이벤트를 처리 하는 데 사용 합니다.|
|[END_DHTML_EVENT_MAP](#end_dhtml_event_map)|DHTML 이벤트 맵의 끝을 표시 합니다.|
|[END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline)|DHTML 이벤트 맵의 끝을 표시 합니다. |

## <a name="url-event-map-macros"></a>URL 이벤트 맵 매크로

다음 매크로 사용 하 여에 DHTML 이벤트를 처리할 수 있습니다 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-클래스를 파생 합니다.

|||
|-|-|
|[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)|다중 페이지 DHTML 및 URL 이벤트 맵의 시작을 표시 합니다.|
|[BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map)|포함 된 DHTML 이벤트 맵 시작을 표시 합니다.|
|[BEGIN_URL_ENTRIES](#begin_url_entries)|URL 이벤트 항목 맵은의 시작을 표시 합니다.|
|[DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map)|다중 페이지 DHTML 및 URL 이벤트 맵을 선언합니다.|
|[END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)|다중 페이지 DHTML 및 URL 이벤트 맵의 끝을 표시 합니다.|
|[END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map)|포함 된 DHTML 이벤트 맵 끝을 표시 합니다.|
|[END_URL_ENTRIES](#end_url_entries)|URL 이벤트 항목 맵은의 끝을 표시 합니다.|
|[URL_EVENT_ENTRY](#url_event_entry)|다중 페이지 대화 상자에서 페이지로 URL 또는 HTML 리소스를 매핑합니다.|

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="begin_dhtml_event_map"></a>  BEGIN_DHTML_EVENT_MAP

DHTML 이벤트 맵으로 식별 되는 클래스에 대 한 소스 파일에 배치 하는 경우의 시작을 표시 `className`합니다.

```
BEGIN_DHTML_EVENT_MAP(className)
```

### <a name="parameters"></a>매개 변수

*className*<br/>
DHTML 이벤트 맵을 포함 하는 클래스의 이름입니다. 이 클래스에 직접 또는 간접적으로에서 파생 되어야 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) 등과 합니다 [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) 해당 클래스 정의 내에서 매크로입니다.

### <a name="remarks"></a>설명

DHTML 이벤트 맵 정보를 제공 하는 클래스에 추가 `CDHtmlDialog` HTML 요소 또는 ActiveX 컨트롤 클래스의 처리기 함수는 웹 페이지에 의해 발생 하는 경로 이벤트를 사용할 수 있습니다.

BEGIN_DHTML_EVENT_MAP 매크로 클래스의 구현 (.cpp) 파일 클래스를 처리 하는 이벤트에 대 한 DHTML_EVENT 매크로 뒤 (mouseover 이벤트에 대 한 예를 들어 DHTML_EVENT_ONMOUSEOVER)에 배치 합니다. 사용 된 [END_DHTML_EVENT_MAP](#end_dhtml_event_map) 이벤트 map의 끝을 표시 하는 매크로입니다. 이러한 매크로 다음 함수를 구현합니다.

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="begin_dhtml_event_map_inline"></a>  BEGIN_DHTML_EVENT_MAP_INLINE

DHTML 이벤트 맵 클래스 정의 내에서 시작을 표시 *className*합니다.

```
BEGIN_DHTML_EVENT_MAP_INLINE(className)
```

### <a name="parameters"></a>매개 변수

*className*<br/>
DHTML 이벤트 맵을 포함 하는 클래스의 이름입니다. 이 클래스에 직접 또는 간접적으로에서 파생 되어야 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) 등과 합니다 [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) 해당 클래스 정의 내에서 매크로입니다.

### <a name="remarks"></a>설명

DHTML 이벤트 맵 정보를 제공 하는 클래스에 추가 `CDHtmlDialog` HTML 요소 또는 ActiveX 컨트롤 클래스의 처리기 함수는 웹 페이지에 의해 발생 하는 경로 이벤트를 사용할 수 있습니다.

BEGIN_DHTML_EVENT_MAP 매크로 클래스의 정의 (.h) 파일 클래스를 처리 하는 이벤트에 대 한 DHTML_EVENT 매크로 뒤 (mouseover 이벤트에 대 한 예를 들어 DHTML_EVENT_ONMOUSEOVER)에 배치 합니다. 사용 된 [END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline) 이벤트 map의 끝을 표시 하는 매크로입니다. 이러한 매크로 다음 함수를 구현합니다.

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="declare_dhtml_event_map"></a>  DECLARE_DHTML_EVENT_MAP

클래스 정의에 DHTML 이벤트 맵을 선언합니다.

```
DECLARE_DHTML_EVENT_MAP()
```

### <a name="remarks"></a>설명

이 매크로의 정의에 사용 하는 것 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)-클래스를 파생 합니다.

사용 하 여 [BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map) 하거나 [BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline) 맵을 구현 합니다.

[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) 다음 함수를 선언 합니다.

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap( );`

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event"></a>  DHTML_EVENT

(문서 수준)으로 식별 되는 이벤트 처리 *dispid* 으로 식별 되는 HTML 요소에서 발생 *elemName*합니다.

```
DHTML_EVENT(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>매개 변수

*dispid*<br/>
처리할 이벤트의 DISPID입니다.

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 문서 이벤트를 처리 하려는 경우 null입니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_axcontrol"></a>  DHTML_EVENT_AXCONTROL

으로 식별 되는 이벤트 처리 *dispid* 식별 된 ActiveX 컨트롤에 의해 발생 *컨트롤 이름*합니다.

```
DHTML_EVENT_AXCONTROL(dispid, controlName,  memberFxn)
```

### <a name="parameters"></a>매개 변수

*dispid*<br/>
처리할 이벤트의 디스패치 ID입니다.

*controlName*<br/>
이벤트를 시작 하는 컨트롤의 HTML ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_class"></a>  DHTML_EVENT_CLASS

(문서 수준)으로 식별 되는 이벤트 처리 *dispid* 로 식별 되는 CSS 클래스를 사용 하 여 모든 HTML 요소에 의해 발생 한 *elemName*합니다.

```
DHTML_EVENT_CLASS(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>매개 변수

*dispid*<br/>
처리할 이벤트의 디스패치 ID입니다.

*elemName*<br/>
이벤트 소싱 HTML 요소의 CSS 클래스를 포함 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_element"></a>  DHTML_EVENT_ELEMENT

처리 (으로 식별 되는 요소에 *elemName*)로 식별 되는 이벤트 *dispid*합니다.

```
DHTML_EVENT_ELEMENT(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>매개 변수

*dispid*<br/>
처리할 이벤트의 디스패치 ID입니다.

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

이벤트의 소스에서 식별 되는 요소 수이 매크로 nonbubbling 이벤트 처리를 사용 하는 경우 *elemName*합니다.

이 매크로 버블링 이벤트를 처리 하는 데 사용 됩니다, 요소에서 식별 *elemName* 이벤트의 소스로 사용할 수 없습니다 (원본에 포함 된 어떤 요소 라도 될 수 있습니다 *elemName*).

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_onafterupdate"></a>  DHTML_EVENT_ONAFTERUPDATE

(문서 수준)를 처리 합니다 `onafterupdate` 으로 식별 되는 HTML 요소에서 이벤트 발생 *elemName*합니다.

```
DHTML_EVENT_ONAFTERUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_onbeforeupdate"></a>  DHTML_EVENT_ONBEFOREUPDATE

(문서 수준)를 처리 합니다 `onbeforeupdate` 으로 식별 되는 HTML 요소에서 이벤트 발생 *elemName*합니다.

```
DHTML_EVENT_ONBEFOREUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_onblur"></a>  DHTML_EVENT_ONBLUR

요소 수준에서 처리 된 `onblur` 이벤트입니다. Nonbubbling 이벤트입니다.

```
DHTML_EVENT_ONBLUR(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_onchange"></a>  DHTML_EVENT_ONCHANGE

요소 수준에서 처리 된 `onchange` 이벤트입니다. Nonbubbling 이벤트입니다.

```
DHTML_EVENT_ONCHANGE(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_onclick"></a>  DHTML_EVENT_ONCLICK

(문서 수준)를 처리 합니다 `onclick` 으로 식별 되는 HTML 요소에서 이벤트 발생 *elemName*합니다.

```
DHTML_EVENT_ONCLICK(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_ondataavailable"></a>  DHTML_EVENT_ONDATAAVAILABLE

(문서 수준)를 처리 합니다 `ondataavailable` 으로 식별 되는 HTML 요소에서 이벤트 발생 *elemName*합니다.

```
DHTML_EVENT_ONDATAAVAILABLE(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_ondatasetchanged"></a>  DHTML_EVENT_ONDATASETCHANGED

(문서 수준)를 처리 합니다 `ondatasetchanged` 으로 식별 되는 HTML 요소에서 이벤트 발생 *elemName*합니다.

```
DHTML_EVENT_ONDATASETCHANGED(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_ondatasetcomplete"></a>  DHTML_EVENT_ONDATASETCOMPLETE

(문서 수준)를 처리 합니다 `ondatasetcomplete` 으로 식별 되는 HTML 요소에서 이벤트 발생 `elemName`합니다.

```
DHTML_EVENT_ONDATASETCOMPLETE(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_ondblclick"></a>  DHTML_EVENT_ONDBLCLICK

(문서 수준)를 처리 합니다 `ondblclick` 으로 식별 되는 HTML 요소에서 이벤트 발생 *elemName*합니다.

```
DHTML_EVENT_ONDBLCLICK(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_ondragstart"></a>  DHTML_EVENT_ONDRAGSTART

(문서 수준)를 처리 합니다 `ondragstart` 으로 식별 되는 HTML 요소에서 이벤트 발생 *elemName*합니다.

```
DHTML_EVENT_ONDRAGSTART(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_onerrorupdate"></a>  DHTML_EVENT_ONERRORUPDATE

(문서 수준)를 처리 합니다 `onerrorupdate` 으로 식별 되는 HTML 요소에서 이벤트 발생 *elemName*합니다.

```
DHTML_EVENT_ONERRORUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_onfilterchange"></a>  DHTML_EVENT_ONFILTERCHANGE

(문서 수준)를 처리 합니다 `onfilterchange` 으로 식별 되는 HTML 요소에서 이벤트 발생 *elemName*합니다.

```

DHTML_EVENT_ONFILTERCHANGE(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_onfocus"></a>  DHTML_EVENT_ONFOCUS

요소 수준에서 처리 된 `onfocus` 이벤트입니다. Nonbubbling 이벤트입니다.

```

DHTML_EVENT_ONFOCUS(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_onhelp"></a>  DHTML_EVENT_ONHELP

(문서 수준)를 처리 합니다 `onhelp` 으로 식별 되는 HTML 요소에서 이벤트 발생 *elemName*합니다.

```

DHTML_EVENT_ONHELP(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_onkeydown"></a>  DHTML_EVENT_ONKEYDOWN

(문서 수준)를 처리 합니다 `onkeydown` 으로 식별 되는 HTML 요소에서 이벤트 발생 *elemName*합니다.

```

DHTML_EVENT_ONKEYDOWN(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_onkeypress"></a>  DHTML_EVENT_ONKEYPRESS

(문서 수준)를 처리 합니다 `onkeypress` 으로 식별 되는 HTML 요소에서 이벤트 발생 *elemName*합니다.

```

DHTML_EVENT_ONKEYPRESS(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_onkeyup"></a>  DHTML_EVENT_ONKEYUP

(문서 수준)를 처리 합니다 `onkeyup` 으로 식별 되는 HTML 요소에서 이벤트 발생 *elemName*합니다.

```

DHTML_EVENT_ONKEYUP(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_onmousedown"></a>  DHTML_EVENT_ONMOUSEDOWN

(문서 수준)를 처리 합니다 `onmousedown` 으로 식별 되는 HTML 요소에서 이벤트 발생 *elemName*합니다.

```

DHTML_EVENT_ONMOUSEDOWN(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_onmousemove"></a>  DHTML_EVENT_ONMOUSEMOVE

(문서 수준)를 처리 합니다 `onmousemove` 으로 식별 되는 HTML 요소에서 이벤트 발생 *elemName*합니다.

```

DHTML_EVENT_ONMOUSEMOVE(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_onmouseout"></a>  DHTML_EVENT_ONMOUSEOUT

(문서 수준)를 처리 합니다 `onmouseout` 으로 식별 되는 HTML 요소에서 이벤트 발생 *elemName*합니다.

```

DHTML_EVENT_ONMOUSEOUT(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_onmouseover"></a>  DHTML_EVENT_ONMOUSEOVER

(문서 수준)를 처리 합니다 `onmouseover` 으로 식별 되는 HTML 요소에서 이벤트 발생 *elemName*합니다.

```

DHTML_EVENT_ONMOUSEOVER(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_onmouseup"></a>  DHTML_EVENT_ONMOUSEUP

(문서 수준)를 처리 합니다 `onmouseup` 으로 식별 되는 HTML 요소에서 이벤트 발생 *elemName*합니다.

```

DHTML_EVENT_ONMOUSEUP(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_onresize"></a>  DHTML_EVENT_ONRESIZE

요소 수준에서 처리 된 `onresize` 이벤트입니다. Nonbubbling 이벤트입니다.

```

DHTML_EVENT_ONRESIZE(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_onrowenter"></a>  DHTML_EVENT_ONROWENTER

(문서 수준)를 처리 합니다 `onrowenter` 으로 식별 되는 HTML 요소에서 이벤트 발생 *elemName*합니다.

```

DHTML_EVENT_ONROWENTER(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_onrowexit"></a>  DHTML_EVENT_ONROWEXIT

(문서 수준)를 처리 합니다 `onrowexit` 으로 식별 되는 HTML 요소에서 이벤트 발생 *elemName*합니다.

```

DHTML_EVENT_ONROWEXIT(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_onselectstart"></a>  DHTML_EVENT_ONSELECTSTART

(문서 수준)를 처리 합니다 `onselectstart` 으로 식별 되는 HTML 요소에서 이벤트 발생 *elemName*합니다.

```

DHTML_EVENT_ONSELECTSTART(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*elemName*<br/>
이벤트 소싱 HTML 요소의 ID를 보유 하는 LPCWSTR 합니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="dhtml_event_tag"></a>  DHTML_EVENT_TAG

(문서 수준)으로 식별 되는 이벤트 처리 `dispid` 로 식별 되는 HTML 태그를 사용 하 여 모든 HTML 요소에서 발생 *elemName*합니다.

```
DHTML_EVENT_TAG(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>매개 변수

*dispid*<br/>
처리할 이벤트의 디스패치 ID입니다.

*elemName*<br/>
이벤트 소싱 HTML 요소의 HTML 태그입니다.

*memberFxn*<br/>
이벤트 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 항목을 추가 합니다 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에서입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="end_dhtml_event_map"></a>  END_DHTML_EVENT_MAP

DHTML 이벤트 맵의 끝을 표시 합니다.

```
END_DHTML_EVENT_MAP()
```

### <a name="remarks"></a>설명

와 함께 사용 해야 합니다 [BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="begin_dhtml_url_event_map"></a>  BEGIN_DHTML_URL_EVENT_MAP

다중 페이지 대화 상자에 DHTML 및 URL 이벤트 맵 정의 시작합니다.

```
BEGIN_DHTML_URL_EVENT_MAP()
```

### <a name="remarks"></a>설명

BEGIN_DHTML_URL_EVENT_MAP 구현 파일에 배치 하 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-클래스를 파생 합니다. 사용 하 여 수행 [DHTML 이벤트 맵 포함](#begin_embed_dhtml_event_map) 및 [URL 항목](#begin_url_entries)를 사용 하 여 닫고 [END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)합니다. 포함 된 [DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map) 클래스 정의 내에서 매크로입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#196](../../mfc/codesnippet/cpp/dhtml-event-maps_1.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="begin_embed_dhtml_event_map"></a>  BEGIN_EMBED_DHTML_EVENT_MAP

다중 페이지 대화 상자에 포함 된 DHTML 이벤트 맵 정의 시작합니다.

```
BEGIN_EMBED_DHTML_EVENT_MAP(className, mapName)
```

### <a name="parameters"></a>매개 변수

*className*<br/>
이벤트 맵을 포함 하는 클래스의 이름입니다. 이 클래스에서 직접 또는 간접적으로 파생 시켜야 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)합니다. 포함 된 DHTML 이벤트 맵 내에 있어야 합니다.는 [DHTML 및 URL 이벤트 맵](#begin_dhtml_url_event_map)).

*mapName*<br/>
이 이벤트 매핑 페이지를 지정 합니다. 일치 *맵 이름* 에 [URL_EVENT_ENTRY](#url_event_entry) 실제로 URL 또는 HTML 리소스를 정의 하는 매크로입니다.

### <a name="remarks"></a>설명

여러 HTML 페이지에 DHTML 이벤트를 발생 시킬 수 있으며 각, 다중 페이지 DHTML 대화 상자 구성 때문에 포함 된 이벤트 맵 이벤트 처리기는 페이지 별로에 매핑할 사용 됩니다.

DHTML 및 URL 이벤트 맵 내에서 포함 된 이벤트 맵 BEGIN_EMBED_DHTML_EVENT_MAP 매크로 뒤에 이루어진 [DHTML_EVENT](#dhtml_event) 매크로 [END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map) 매크로입니다.

각 포함 된 이벤트 맵에 해당 필요 [URL 이벤트 항목](#url_event_entry) 매핑할 *맵 이름* (BEGIN_EMBED_DHTML_EVENT_MAP에서 지정) URL 또는 HTML 리소스입니다.

### <a name="example"></a>예제

예제를 참조 하세요 [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="begin_url_entries"></a>  BEGIN_URL_ENTRIES

다중 페이지 대화 상자에서 URL 이벤트 항목 맵 정의를 시작합니다.

```
BEGIN_URL_ENTRIES(className)
```

### <a name="parameters"></a>매개 변수

*className*<br/>
URL 이벤트 항목 맵을 포함하는 클래스의 이름입니다. 이 클래스에서 직접 또는 간접적으로 파생 시켜야 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)합니다. URL 이벤트 항목 맵 내에 있어야 합니다.는 [DHTML 및 URL 이벤트 맵](#begin_dhtml_url_event_map)).

### <a name="remarks"></a>설명

다중 페이지 DHTML 대화로 여러 HTML 페이지의 구성 때문에 URL 이벤트 항목은 매핑하는 데 Url 또는 HTML 리소스를 해당 [DHTML 이벤트 맵 포함](#begin_embed_dhtml_event_map)합니다. URL_EVENT_ENTRY 매크로 BEGIN_URL_ENTRIES 사이 배치 하 고 [END_URL_ENTRIES](#end_url_entries) 매크로입니다.

### <a name="example"></a>예제

예제를 참조 하세요 [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="declare_dhtml_url_event_map"></a>  DECLARE_DHTML_URL_EVENT_MAP

클래스 정의에 DHTML 및 URL 이벤트 맵을 선언합니다.

```
DECLARE_DHTML_URL_EVENT_MAP()
```

### <a name="remarks"></a>설명

이 매크로의 정의에 사용 하는 것 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-클래스를 파생 합니다.

DHTML 및 URL 이벤트 맵 포함 [DHTML 이벤트 맵 포함](#begin_embed_dhtml_event_map) 하 고 [URL 이벤트 항목](#begin_url_entries) DHTML 이벤트 처리기는 페이지 별로에 매핑할 합니다. 사용 하 여 [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map) 지도 구현 합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="end_dhtml_url_event_map"></a>  END_DHTML_URL_EVENT_MAP

DHTML 및 URL 이벤트 맵의 끝을 표시 합니다.

```
END_DHTML_URL_EVENT_MAP(className)
```

### <a name="parameters"></a>매개 변수

*className*<br/>
이벤트 맵을 포함 하는 클래스의 이름입니다. 이 클래스에서 직접 또는 간접적으로 파생 시켜야 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)합니다. 이 일치 해야 *className* 해당 [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map) 매크로입니다.

### <a name="example"></a>예제

예제를 참조 하세요 [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="end_embed_dhtml_event_map"></a>  END_EMBED_DHTML_EVENT_MAP

포함 된 DHTML 이벤트 맵 끝을 표시 합니다.

```
END_EMBED_DHTML_EVENT_MAP()
```

### <a name="example"></a>예제

예제를 참조 하세요 [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="end_url_entries"></a>  END_URL_ENTRIES

URL 이벤트 항목 맵은의 끝을 표시 합니다.

```
END_URL_ENTRIES()
```

### <a name="example"></a>예제

예제를 참조 하세요 [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="url_event_entry"></a>  URL_EVENT_ENTRY

다중 페이지 대화 상자에서 페이지로 URL 또는 HTML 리소스를 매핑합니다.

```
URL_EVENT_ENTRY(className, url,  mapName)
```

### <a name="parameters"></a>매개 변수

*className*<br/>
URL 이벤트 항목 맵을 포함하는 클래스의 이름입니다. 이 클래스에서 직접 또는 간접적으로 파생 시켜야 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)합니다. URL 이벤트 항목 맵 내에 있어야 합니다.는 [DHTML 및 URL 이벤트 맵](#begin_dhtml_url_event_map)).

*url*<br/>
페이지에 대 한 URL 또는 HTML 리소스입니다.

*mapName*<br/>
URL이 페이지를 지정 *url*합니다. 일치 *맵 이름* 에 [BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map) 이 페이지에서 이벤트를 매핑하는 매크로입니다.

### <a name="remarks"></a>설명

페이지가 HTML 리소스를 이면 *url* 리소스의 ID 번호 (즉, "123", 없습니다 123 또는 ID_HTMLRES1)의 문자열 표현 이어야 합니다.

페이지 식별자 *맵 이름*를 연결 하는 데 사용 되는 임의의 기호 URL 이벤트 항목 맵에 DHTML 이벤트 맵 포함 됩니다. DHTML 및 URL 이벤트 맵 범위 제한 됩니다.

### <a name="example"></a>예제

예제를 참조 하세요 [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

##  <a name="end_dhtml_event_map_inline"></a>END_DHTML_EVENT_MAP_INLINE

DHTML 이벤트 맵의 끝을 표시 합니다.

### <a name="syntax"></a>구문

```
END_DHTML_EVENT_MAP_INLINE( )
```

### <a name="remarks"></a>설명

와 함께 사용 해야 합니다 [BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdhtml.h

## <a name="see-also"></a>참고자료

[매크로 및 전역](mfc-macros-and-globals.md)
