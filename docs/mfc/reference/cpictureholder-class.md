---
title: CPictureHolder 클래스
ms.date: 11/04/2016
f1_keywords:
- CPictureHolder
- AFXCTL/CPictureHolder
- AFXCTL/CPictureHolder::CPictureHolder
- AFXCTL/CPictureHolder::CreateEmpty
- AFXCTL/CPictureHolder::CreateFromBitmap
- AFXCTL/CPictureHolder::CreateFromIcon
- AFXCTL/CPictureHolder::CreateFromMetafile
- AFXCTL/CPictureHolder::GetDisplayString
- AFXCTL/CPictureHolder::GetPictureDispatch
- AFXCTL/CPictureHolder::GetType
- AFXCTL/CPictureHolder::Render
- AFXCTL/CPictureHolder::SetPictureDispatch
- AFXCTL/CPictureHolder::m_pPict
helpviewer_keywords:
- CPictureHolder [MFC], CPictureHolder
- CPictureHolder [MFC], CreateEmpty
- CPictureHolder [MFC], CreateFromBitmap
- CPictureHolder [MFC], CreateFromIcon
- CPictureHolder [MFC], CreateFromMetafile
- CPictureHolder [MFC], GetDisplayString
- CPictureHolder [MFC], GetPictureDispatch
- CPictureHolder [MFC], GetType
- CPictureHolder [MFC], Render
- CPictureHolder [MFC], SetPictureDispatch
- CPictureHolder [MFC], m_pPict
ms.assetid: a4f59775-704a-41dd-b5bd-2e531c95127a
ms.openlocfilehash: 5386240114550826e4bf557b63310a91590afb55
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372883"
---
# <a name="cpictureholder-class"></a>CPictureHolder 클래스

컨트롤에서 그림을 표시할 수 있도록 하는 그림 속성을 구현 합니다.

## <a name="syntax"></a>구문

```
class CPictureHolder
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CPictureHolder::CPictureHolder](#cpictureholder)|`CPictureHolder` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CPictureHolder::CreateEmpty](#createempty)|빈 `CPictureHolder` 개체를 만듭니다.|
|[CPictureHolder::CreateFromBitmap](#createfrombitmap)|만듭니다는 `CPictureHolder` 비트맵에서 개체입니다.|
|[CPictureHolder::CreateFromIcon](#createfromicon)|만듭니다는 `CPictureHolder` 아이콘 개체입니다.|
|[CPictureHolder::CreateFromMetafile](#createfrommetafile)|만듭니다는 `CPictureHolder` 메타 파일에서 개체입니다.|
|[CPictureHolder::GetDisplayString](#getdisplaystring)|컨트롤 컨테이너의 속성 브라우저에 표시 되는 문자열을 검색 합니다.|
|[CPictureHolder::GetPictureDispatch](#getpicturedispatch)|반환 된 `CPictureHolder` 개체의 `IDispatch` 인터페이스입니다.|
|[CPictureHolder::GetType](#gettype)|지시 여부는 `CPictureHolder` 개체가 메타 파일, 비트맵, 아이콘입니다.|
|[CPictureHolder::Render](#render)|그림을 렌더링합니다.|
|[CPictureHolder::SetPictureDispatch](#setpicturedispatch)|설정 된 `CPictureHolder` 개체의 `IDispatch` 인터페이스입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CPictureHolder::m_pPict](#m_ppict)|그림 개체에 대 한 포인터입니다.|

## <a name="remarks"></a>설명

`CPictureHolder` 기본 클래스는 없습니다.

스톡 그림 속성에 비트맵, 아이콘 또는 메타 파일 표시에 대 한 개발자 지정할 수 있습니다.

사용자 지정 그림 속성 만들기에 대 한 내용은 문서를 참고 [MFC ActiveX 컨트롤: ActiveX 컨트롤에서 그림을 사용 하 여](../../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md)입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CPictureHolder`

## <a name="requirements"></a>요구 사항

**헤더:** afxctl.h

##  <a name="cpictureholder"></a>  CPictureHolder::CPictureHolder

`CPictureHolder` 개체를 생성합니다.

```
CPictureHolder();
```

##  <a name="createempty"></a>  CPictureHolder::CreateEmpty

빈 만듭니다 `CPictureHolder` 개체와 연결 하는 `IPicture` 인터페이스입니다.

```
BOOL CreateEmpty();
```

### <a name="return-value"></a>반환 값

0이 아닌 개체를 성공적으로 만들어지면; 그렇지 않으면 0입니다.

##  <a name="createfrombitmap"></a>  CPictureHolder::CreateFromBitmap

비트맵을 사용 하 여 그림 개체를 초기화 하는 `CPictureHolder`합니다.

```
BOOL CreateFromBitmap(
    UINT idResource);

BOOL CreateFromBitmap(
    CBitmap* pBitmap,
    CPalette* pPal = NULL,
    BOOL bTransferOwnership = TRUE);

BOOL CreateFromBitmap(
    HBITMAP hbm,
    HPALETTE hpal = NULL,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>매개 변수

*idResource*<br/>
비트맵 리소스의 리소스 ID입니다.

*pBitmap*<br/>
에 대 한 포인터를 [CBitmap](../../mfc/reference/cbitmap-class.md) 개체입니다.

*pPal*<br/>
에 대 한 포인터를 [CPalette](../../mfc/reference/cpalette-class.md) 개체입니다.

*bTransferOwnership*<br/>
그림 개체 비트맵 및 색상표 개체의 소유권은 있는지 여부를 나타냅니다.

*hbm*<br/>
비트맵에 대 한 핸들을 `CPictureHolder` 개체가 만들어집니다.

*hpal*<br/>
비트맵을 렌더링 하는 데 사용 되는 팔레트에 대 한 핸들입니다.

### <a name="return-value"></a>반환 값

0이 아닌 개체를 성공적으로 만들어지면; 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

하는 경우 *bTransferOwnership* TRUE, 호출자에 게 비트맵을 사용 하지 않아야 또는이 호출 후에 어떤 방식으로든에서 색상표 개체를 반환 합니다. 하는 경우 *bTransferOwnership* FALSE는 호출자가 비트맵 및 색상표 개체 그림 개체의 수명 동안 유효한 상태로 유지 하는 일을 담당 합니다.

##  <a name="createfromicon"></a>  CPictureHolder::CreateFromIcon

아이콘을 사용 하 여 그림 개체를 초기화 한 `CPictureHolder`합니다.

```
BOOL CreateFromIcon(
    UINT idResource);

BOOL CreateFromIcon(
    HICON hIcon,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>매개 변수

*idResource*<br/>
비트맵 리소스의 리소스 ID입니다.

*hIcon*<br/>
올 아이콘에 대 한 핸들을 `CPictureHolder` 개체가 만들어집니다.

*bTransferOwnership*<br/>
그림 개체 아이콘 개체의 소유권은 있는지 여부를 나타냅니다.

### <a name="return-value"></a>반환 값

0이 아닌 개체를 성공적으로 만들어지면; 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

하는 경우 *bTransferOwnership* 가 TRUE 이면이 호출에서 반환 된 후 호출자에 게 어떤 방식으로든에서 하지 아이콘 개체를 사용 해야 합니다. 경우 *bTransferOwnership* FALSE는 호출자가는 icon 개체를 계속 유효한 그림 개체의 수명을 담당 합니다.

##  <a name="createfrommetafile"></a>  CPictureHolder::CreateFromMetafile

메타 파일을 사용 하 여 그림 개체를 초기화 하는 `CPictureHolder`합니다.

```
BOOL CreateFromMetafile(
    HMETAFILE hmf,
    int xExt,
    int yExt,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>매개 변수

*hmf*<br/>
만드는 데 사용 하 여 메타 파일에 대 한 핸들을 `CPictureHolder` 개체입니다.

*xExt*<br/>
그림의 익스텐트 X입니다.

*yExt*<br/>
그림의 Y 범위입니다.

*bTransferOwnership*<br/>
그림 개체 메타 파일 개체의 소유권은 있는지 여부를 나타냅니다.

### <a name="return-value"></a>반환 값

0이 아닌 개체를 성공적으로 만들어지면; 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

하는 경우 *bTransferOwnership* 가 TRUE 이면이 호출에서 반환 된 후 호출자에 게 어떤 방식으로든에서 하지 메타 파일 개체를 사용 해야 합니다. 경우 *bTransferOwnership* FALSE는 호출자가 메타 파일 개체가 그림 개체의 수명 동안에 유효한 상태로 유지 하는 일을 담당 합니다.

##  <a name="getdisplaystring"></a>  CPictureHolder::GetDisplayString

컨테이너의 속성 브라우저에 표시 되는 문자열을 검색 합니다.

```
BOOL GetDisplayString(CString& strValue);
```

### <a name="parameters"></a>매개 변수

*strValue*<br/>
에 대 한 참조를 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 표시 문자열을 보유 하는 것입니다.

### <a name="return-value"></a>반환 값

문자열; 검색 된 경우 0이 아닌 값 그렇지 않으면 0입니다.

##  <a name="getpicturedispatch"></a>  CPictureHolder::GetPictureDispatch

이 함수에 대 한 포인터를 반환 합니다 `CPictureHolder` 개체의 `IPictureDisp` 인터페이스입니다.

```
LPPICTUREDISP GetPictureDispatch();
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `CPictureHolder` 개체의 `IPictureDisp` 인터페이스입니다.

### <a name="remarks"></a>설명

호출자에 게 호출 해야 `Release` 사용이 끝나면이 포인터에 대 한 합니다.

##  <a name="gettype"></a>  CPictureHolder::GetType

아이콘, 비트맵 또는 메타 파일 그림 인지 여부를 나타냅니다.

```
short GetType();
```

### <a name="return-value"></a>반환 값

그림의 형식을 나타내는 값입니다. 가능한 값과 해당 의미는 다음과 같습니다.

|값|의미|
|-----------|-------------|
|PICTYPE_UNINITIALIZED|`CPictureHolder` 개체 unititialized 됩니다.|
|PICTYPE_NONE|`CPictureHolder` 개체가 비어 있습니다.|
|PICTYPE_BITMAP|그림이 비트맵입니다.|
|PICTYPE_METAFILE|그림이 메타 파일입니다.|
|PICTYPE_ICON|그림이 아이콘입니다.|

##  <a name="m_ppict"></a>  CPictureHolder::m_pPict

에 대 한 포인터를 `CPictureHolder` 개체의 `IPicture` 인터페이스입니다.

```
LPPICTURE m_pPict;
```

##  <a name="render"></a>  CPictureHolder::Render

참조 하는 사각형을 그림 렌더링 *rcRender*합니다.

```
void Render(
    CDC* pDC,
    const CRect& rcRender,
    const CRect& rcWBounds);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
그림 렌더링 되어야 하는 디스플레이 컨텍스트 포인터입니다.

*rcRender*<br/>
그림을 렌더링할의 사각형입니다.

*rcWBounds*<br/>
그림을 렌더링 하는 개체의 경계 사각형을 나타내는 사각형입니다. 이 사각형은 컨트롤의 경우는 *rcBounds* 매개 변수 재정의에 전달 [COleControl::OnDraw](../../mfc/reference/colecontrol-class.md#ondraw)합니다.

##  <a name="setpicturedispatch"></a>  CPictureHolder::SetPictureDispatch

연결 된 `CPictureHolder` 개체를 `IPictureDisp` 인터페이스입니다.

```
void SetPictureDispatch(LPPICTUREDISP pDisp);
```

### <a name="parameters"></a>매개 변수

*pDisp*<br/>
새 포인터 `IPictureDisp` 인터페이스입니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CFontHolder 클래스](../../mfc/reference/cfontholder-class.md)
