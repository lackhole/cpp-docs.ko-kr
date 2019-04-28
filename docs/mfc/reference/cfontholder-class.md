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
ms.openlocfilehash: 623ce5da46716e3f9a562862fc0375fb8704bb21
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182214"
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

|이름|설명|
|----------|-----------------|
|[CFontHolder::GetDisplayString](#getdisplaystring)|컨테이너의 속성 브라우저에 표시 되는 문자열을 검색 합니다.|
|[CFontHolder::GetFontDispatch](#getfontdispatch)|글꼴의 반환 `IDispatch` 인터페이스입니다.|
|[CFontHolder::GetFontHandle](#getfonthandle)|Windows 글꼴에 대 한 핸들을 반환합니다.|
|[CFontHolder::InitializeFont](#initializefont)|초기화는 `CFontHolder` 개체입니다.|
|[CFontHolder::QueryTextMetrics](#querytextmetrics)|관련된 글꼴에 대 한 정보를 검색합니다.|
|[CFontHolder::ReleaseFont](#releasefont)|연결을 끊습니다 합니다 `CFontHolder` 에서 개체를 `IFont` 및 `IFontNotification` 인터페이스입니다.|
|[CFontHolder::Select](#select)|장치 컨텍스트에 글꼴 리소스를 선택합니다.|
|[CFontHolder::SetFont](#setfont)|연결 된 `CFontHolder` 개체는 `IFont` 인터페이스입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CFontHolder::m_pFont](#m_pfont)|에 대 한 포인터를 `CFontHolder` 개체의 `IFont` 인터페이스입니다.|

## <a name="remarks"></a>설명

`CFontHolder` 기본 클래스는 없습니다.

이 클래스를 사용 하 여 컨트롤에 대 한 사용자 지정 글꼴 속성을 구현 합니다. 이러한 속성을 만드는 방법에 대 한 정보를 문서를 참조 하세요. [ActiveX 컨트롤: 글꼴을 사용 하 여](../../mfc/mfc-activex-controls-using-fonts.md)입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CFontHolder`

## <a name="requirements"></a>요구 사항

**헤더:** afxctl.h

##  <a name="cfontholder"></a>  CFontHolder::CFontHolder

`CFontHolder` 개체를 생성합니다.

```
explicit CFontHolder(LPPROPERTYNOTIFYSINK pNotify);
```

### <a name="parameters"></a>매개 변수

*pNotify*<br/>
글꼴에 대 한 포인터 `IPropertyNotifySink` 인터페이스입니다.

### <a name="remarks"></a>설명

호출 해야 `InitializeFont` 를 사용 하기 전에 결과 개체를 초기화 합니다.

##  <a name="getdisplaystring"></a>  CFontHolder::GetDisplayString

컨테이너의 속성 브라우저에 표시 될 수 있는 문자열을 검색 합니다.

```
BOOL GetDisplayString(CString& strValue);
```

### <a name="parameters"></a>매개 변수

*strValue*<br/>
에 대 한 참조를 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 표시 문자열을 보유 하는 것입니다.

### <a name="return-value"></a>반환 값

문자열; 검색 된 경우 0이 아닌 값 그렇지 않으면 0입니다.

##  <a name="getfontdispatch"></a>  CFontHolder::GetFontDispatch

글꼴의 디스패치 인터페이스에 대 한 포인터를 검색 하려면이 함수를 호출 합니다.

```
LPFONTDISP GetFontDispatch();
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `CFontHolder` 개체의 `IFontDisp` 인터페이스입니다. 호출 하는 함수 `GetFontDispatch` 를 호출 해야 `IUnknown::Release` 작업을 완료 하는 경우이 인터페이스 포인터에 대 한 합니다.

### <a name="remarks"></a>설명

호출 `InitializeFont` 호출 하기 전에 `GetFontDispatch`입니다.

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
높이 컨트롤을 그리는 사각형의 논리 단위에서입니다.

*cyHimetric*<br/>
컨트롤의 MM_HIMETRIC 단위에서 높이입니다.

### <a name="return-value"></a>반환 값

글꼴 개체에 대 한 핸들 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

비율 *cyLogical* 하 고 *cyHimetric* 적절 하 게 표시할 크기 MM_HIMETRIC 단위로 표시 하는 글꼴의 포인트 크기에 대 한 논리 단위를 계산 하는 데 사용 됩니다.

Display size = ( *cyLogical* / *cyHimetric*) X font size

버전 매개 변수 없이 화면에 대 한 올바른 크기가 글꼴 핸들을 반환 합니다.

##  <a name="initializefont"></a>  CFontHolder::InitializeFont

초기화는 `CFontHolder` 개체입니다.

```
void InitializeFont(
    const FONTDESC* pFontDesc = NULL,
    LPDISPATCH pFontDispAmbient = NULL);
```

### <a name="parameters"></a>매개 변수

*pFontDesc*<br/>
글꼴 설명 구조에 대 한 포인터 ( [FONTDESC](/windows/desktop/api/olectl/ns-olectl-tagfontdesc)) 글꼴 특성을 지정 하는 합니다.

*pFontDispAmbient*<br/>
컨테이너의 앰비언트 글꼴 속성에 대 한 포인터입니다.

### <a name="remarks"></a>설명

하는 경우 *pFontDispAmbient* NULL이 아니면 합니다 `CFontHolder` 개체의 복제본에 연결 되어를 `IFont` 컨테이너의 앰비언트 글꼴 속성에 의해 사용 되는 인터페이스입니다.

하는 경우 *pFontDispAmbient* 가 null 인 경우 새 글꼴 개체 가리키는 글꼴 설명에서 만들어진 *pFontDesc* 또는 *pFontDesc* 가 null 인 경우 기본값에서 설명입니다.

생성 한 후이 함수 호출을 `CFontHolder` 개체입니다.

##  <a name="m_pfont"></a>  CFontHolder::m_pFont

에 대 한 포인터를 `CFontHolder` 개체의 `IFont` 인터페이스입니다.

```
LPFONT m_pFont;
```

##  <a name="querytextmetrics"></a>  CFontHolder::QueryTextMetrics

표현 되는 실제 글꼴에 대 한 정보를 검색 합니다 `CFontHolder` 개체입니다.

```
void QueryTextMetrics(LPTEXTMETRIC lptm);
```

### <a name="parameters"></a>매개 변수

*lptm*<br/>
에 대 한 포인터를 [TEXTMETRIC](/windows/desktop/api/wingdi/ns-wingdi-tagtextmetrica) 구조는 정보를 받게 됩니다.

##  <a name="releasefont"></a>  CFontHolder::ReleaseFont

연결을 끊습니다이 함수는 `CFontHolder` 개체에서 해당 `IFont` 인터페이스입니다.

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
장치 컨텍스트 글꼴을 선택 합니다.

*cyLogical*<br/>
높이 컨트롤을 그리는 사각형의 논리 단위에서입니다.

*cyHimetric*<br/>
컨트롤의 MM_HIMETRIC 단위에서 높이입니다.

### <a name="return-value"></a>반환 값

대체 되는 글꼴에 대 한 포인터입니다.

### <a name="remarks"></a>설명

참조 [GetFontHandle](#getfonthandle) 대 한 설명은 합니다 *cyLogical* 하 고 *cyHimetric* 매개 변수입니다.

##  <a name="setfont"></a>  CFontHolder::SetFont

기존 글꼴을 해제 하 고 연결 합니다 `CFontHolder` 개체는 `IFont` 인터페이스입니다.

```
void SetFont(LPFONT pNewFont);
```

### <a name="parameters"></a>매개 변수

*pNewFont*<br/>
새 포인터 `IFont` 인터페이스입니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CPropExchange 클래스](../../mfc/reference/cpropexchange-class.md)
