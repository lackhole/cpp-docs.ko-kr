---
title: CFontHolder 클래스
ms.date: 11/04/2016
f1_keywords:
- CFontHolder
- AFXCTL/CFontHolder
- AFXCTL/CFontHolder::CFontHolder
- AFXCTL/CFontHolder::GetDisplayString
- AFXCTL/CFontHolder::GetFontDispatch
- AFXCTL/CFontHolder::GetFontHandle
- AFXCTL/CFontHolder::InitializeFont
- AFXCTL/CFontHolder::QueryTextMetrics
- AFXCTL/CFontHolder::ReleaseFont
- AFXCTL/CFontHolder::Select
- AFXCTL/CFontHolder::SetFont
- AFXCTL/CFontHolder::m_pFont
helpviewer_keywords:
- CFontHolder [MFC], CFontHolder
- CFontHolder [MFC], GetDisplayString
- CFontHolder [MFC], GetFontDispatch
- CFontHolder [MFC], GetFontHandle
- CFontHolder [MFC], InitializeFont
- CFontHolder [MFC], QueryTextMetrics
- CFontHolder [MFC], ReleaseFont
- CFontHolder [MFC], Select
- CFontHolder [MFC], SetFont
- CFontHolder [MFC], m_pFont
ms.assetid: 728ab472-0c97-440d-889f-1324c6e1b6b8
ms.openlocfilehash: 04de8141469f82bdd1fbb6adc1bae94d6026324c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506440"
---
# <a name="cfontholder-class"></a>CFontHolder 클래스

스톡 글꼴 속성을 구현하고 Windows 글꼴 개체 및 `IFont` 인터페이스의 기능을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CFontHolder
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CFontHolder::CFontHolder](#cfontholder)|`CFontHolder` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|Description|
|----------|-----------------|
|[CFontHolder::GetDisplayString](#getdisplaystring)|컨테이너의 속성 브라우저에 표시 되는 문자열을 검색 합니다.|
|[CFontHolder::GetFontDispatch](#getfontdispatch)|글꼴의 `IDispatch` 인터페이스를 반환 합니다.|
|[CFontHolder::GetFontHandle](#getfonthandle)|Windows 글꼴에 대 한 핸들을 반환 합니다.|
|[CFontHolder::InitializeFont](#initializefont)|개체를 `CFontHolder` 초기화 합니다.|
|[CFontHolder::QueryTextMetrics](#querytextmetrics)|관련 글꼴에 대 한 정보를 검색 합니다.|
|[CFontHolder::ReleaseFont](#releasefont)|및`IFont` `CFontHolder` 인터페이스에서개체의`IFontNotification` 연결을 끊습니다.|
|[CFontHolder::Select](#select)|장치 컨텍스트에서 글꼴 리소스를 선택 합니다.|
|[CFontHolder::SetFont](#setfont)|개체를 `IFont` 인터페이스에 연결 합니다. `CFontHolder`|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CFontHolder::m_pFont](#m_pfont)|`CFontHolder` 개체 의`IFont` 인터페이스에 대 한 포인터입니다.|

## <a name="remarks"></a>설명

`CFontHolder`에 기본 클래스가 없습니다.

이 클래스를 사용 하 여 컨트롤에 대 한 사용자 지정 글꼴 속성을 구현 합니다. 이러한 속성을 [만드는 방법에 대 한 자세한 내용은 ActiveX 컨트롤: 글꼴](../../mfc/mfc-activex-controls-using-fonts.md)사용.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CFontHolder`

## <a name="requirements"></a>요구 사항

**헤더:** afxctl

##  <a name="cfontholder"></a>  CFontHolder::CFontHolder

`CFontHolder` 개체를 생성합니다.

```
explicit CFontHolder(LPPROPERTYNOTIFYSINK pNotify);
```

### <a name="parameters"></a>매개 변수

*pNotify*<br/>
글꼴의 `IPropertyNotifySink` 인터페이스에 대 한 포인터입니다.

### <a name="remarks"></a>설명

를 사용 하기 `InitializeFont` 전에를 호출 하 여 결과 개체를 초기화 해야 합니다.

##  <a name="getdisplaystring"></a>  CFontHolder::GetDisplayString

컨테이너의 속성 브라우저에 표시할 수 있는 문자열을 검색 합니다.

```
BOOL GetDisplayString(CString& strValue);
```

### <a name="parameters"></a>매개 변수

*strValue*<br/>
표시 문자열을 보유할 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 에 대 한 참조입니다.

### <a name="return-value"></a>반환 값

문자열이 성공적으로 검색 되 면 0이 아닌 값입니다. 그렇지 않으면 0입니다.

##  <a name="getfontdispatch"></a>  CFontHolder::GetFontDispatch

글꼴의 디스패치 인터페이스에 대 한 포인터를 검색 하려면이 함수를 호출 합니다.

```
LPFONTDISP GetFontDispatch();
```

### <a name="return-value"></a>반환 값

`CFontHolder` 개체 의`IFontDisp` 인터페이스에 대 한 포인터입니다. 을 호출 `GetFontDispatch` 하는 함수는 작업을 `IUnknown::Release` 수행할 때이 인터페이스 포인터에서를 호출 해야 합니다.

### <a name="remarks"></a>설명

를`GetFontDispatch`호출 하기 전에를 호출 `InitializeFont` 합니다.

##  <a name="getfonthandle"></a>  CFontHolder::GetFontHandle

Windows 글꼴에 대 한 핸들을 가져오려면이 함수를 호출 합니다.

```
HFONT GetFontHandle();

HFONT GetFontHandle(
    long cyLogical,
    long cyHimetric);
```

### <a name="parameters"></a>매개 변수

*cyLogical*<br/>
컨트롤이 그려지는 사각형의 높이 (논리 단위)입니다.

*cyHimetric*<br/>
컨트롤의 높이 (MM_HIMETRIC 단위)입니다.

### <a name="return-value"></a>반환 값

글꼴 개체에 대 한 핸들입니다. 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

*CyLogical* 및 *cyHimetric* 의 비율을 사용 하 여 MM_HIMETRIC 단위로 표현 되는 글꼴의 포인트 크기에 대 한 적절 한 표시 크기 (논리 단위)를 계산 합니다.

Display size = ( *cyLogical* / *cyHimetric*) X font size

매개 변수가 없는 버전은 화면에 맞는 글꼴 크기에 대 한 핸들을 반환 합니다.

##  <a name="initializefont"></a>  CFontHolder::InitializeFont

개체를 `CFontHolder` 초기화 합니다.

```
void InitializeFont(
    const FONTDESC* pFontDesc = NULL,
    LPDISPATCH pFontDispAmbient = NULL);
```

### <a name="parameters"></a>매개 변수

*pFontDesc*<br/>
글꼴의 특징을 지정 하는 글꼴 설명 구조 [(글꼴 설명)에](/windows/win32/api/olectl/ns-olectl-fontdesc)대 한 포인터입니다.

*pFontDispAmbient*<br/>
컨테이너의 앰비언트 글꼴 속성에 대 한 포인터입니다.

### <a name="remarks"></a>설명

*PFontDispAmbient* 가 NULL이 아닌 경우 개체 `CFontHolder` 는 컨테이너의 앰비언트 글꼴 속성에서 사용 `IFont` 하는 인터페이스의 복제본에 연결 됩니다.

*PFontDispAmbient* 가 null 인 경우에는 *pfontdesc* 가 가리키는 글꼴 설명에서 새 font 개체가 만들어지거나 기본 설명에서 *pfontdesc* 가 NULL 인 경우에는 새 font 개체가 만들어집니다.

개체를 생성 한 후이 `CFontHolder` 함수를 호출 합니다.

##  <a name="m_pfont"></a>  CFontHolder::m_pFont

`CFontHolder` 개체 의`IFont` 인터페이스에 대 한 포인터입니다.

```
LPFONT m_pFont;
```

##  <a name="querytextmetrics"></a>  CFontHolder::QueryTextMetrics

`CFontHolder` 개체로 표시 되는 실제 글꼴에 대 한 정보를 검색 합니다.

```
void QueryTextMetrics(LPTEXTMETRIC lptm);
```

### <a name="parameters"></a>매개 변수

*lptm*<br/>
정보를 받을 [Textmetric](/windows/win32/api/wingdi/ns-wingdi-textmetricw) 구조체에 대 한 포인터입니다.

##  <a name="releasefont"></a>  CFontHolder::ReleaseFont

이 함수는 `IFont` 인터페이스 `CFontHolder` 에서 개체의 연결을 끊습니다.

```
void ReleaseFont();
```

##  <a name="select"></a>  CFontHolder::Select

지정 된 장치 컨텍스트에 컨트롤의 글꼴을 선택 하려면이 함수를 호출 합니다.

```
CFont* Select(
    CDC* pDC,
    long cyLogical,
    long cyHimetric);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
글꼴이 선택 된 장치 컨텍스트입니다.

*cyLogical*<br/>
컨트롤이 그려지는 사각형의 높이 (논리 단위)입니다.

*cyHimetric*<br/>
컨트롤의 높이 (MM_HIMETRIC 단위)입니다.

### <a name="return-value"></a>반환 값

대체 되는 글꼴에 대 한 포인터입니다.

### <a name="remarks"></a>설명

*CyLogical* 및 *cyHimetric* 매개 변수에 대 한 자세한 내용은 [GetFontHandle](#getfonthandle) 를 참조 하세요.

##  <a name="setfont"></a>  CFontHolder::SetFont

기존 글꼴을 해제 하 고 `CFontHolder` 개체를 `IFont` 인터페이스에 연결 합니다.

```
void SetFont(LPFONT pNewFont);
```

### <a name="parameters"></a>매개 변수

*pNewFont*<br/>
새 `IFont` 인터페이스에 대 한 포인터입니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CPropExchange 클래스](../../mfc/reference/cpropexchange-class.md)
