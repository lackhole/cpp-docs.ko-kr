---
title: CRecentDockSiteInfo 클래스
ms.date: 11/04/2016
f1_keywords:
- CRecentDockSiteInfo
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::CleanUp
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentDefaultPaneDivider
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentDockedPercent
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentDockedRect
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentListOfPanes
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentPaneContainer
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentTabContainer
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::Init
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::IsRecentLeftPane
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::SaveListOfRecentPanes
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::SetInfo
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::StoreDockInfo
helpviewer_keywords:
- CRecentDockSiteInfo [MFC], CleanUp
- CRecentDockSiteInfo [MFC], GetRecentDefaultPaneDivider
- CRecentDockSiteInfo [MFC], GetRecentDockedPercent
- CRecentDockSiteInfo [MFC], GetRecentDockedRect
- CRecentDockSiteInfo [MFC], GetRecentListOfPanes
- CRecentDockSiteInfo [MFC], GetRecentPaneContainer
- CRecentDockSiteInfo [MFC], GetRecentTabContainer
- CRecentDockSiteInfo [MFC], Init
- CRecentDockSiteInfo [MFC], IsRecentLeftPane
- CRecentDockSiteInfo [MFC], SaveListOfRecentPanes
- CRecentDockSiteInfo [MFC], SetInfo
- CRecentDockSiteInfo [MFC], StoreDockInfo
ms.assetid: 2dd14f95-d5a2-4461-a7a5-2c6c36a3a165
ms.openlocfilehash: 4a522d4dc88e7d1937ffa5b859aec32615939f21
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372168"
---
# <a name="crecentdocksiteinfo-class"></a>CRecentDockSiteInfo 클래스

합니다 `CRecentDockSiteInfo` 클래스는에 대 한 최신 상태 정보를 저장 하는 도우미 클래스를 [CPane 클래스](../../mfc/reference/cpane-class.md)합니다.

## <a name="syntax"></a>구문

```
class CRecentDockSiteInfo : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|`CRecentDockSiteInfo::CRecentDockSiteInfo`|기본 생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CRecentDockSiteInfo::CleanUp](#cleanup)||
|[CRecentDockSiteInfo::GetRecentDefaultPaneDivider](#getrecentdefaultpanedivider)||
|[CRecentDockSiteInfo::GetRecentDockedPercent](#getrecentdockedpercent)||
|[CRecentDockSiteInfo::GetRecentDockedRect](#getrecentdockedrect)||
|[CRecentDockSiteInfo::GetRecentListOfPanes](#getrecentlistofpanes)||
|[CRecentDockSiteInfo::GetRecentPaneContainer](#getrecentpanecontainer)||
|[CRecentDockSiteInfo::GetRecentTabContainer](#getrecenttabcontainer)||
|[CRecentDockSiteInfo::Init](#init)||
|[CRecentDockSiteInfo::IsRecentLeftPane](#isrecentleftpane)||
|[CRecentDockSiteInfo::operator =](#operator_eq)||
|[CRecentDockSiteInfo::SaveListOfRecentPanes](#savelistofrecentpanes)||
|[CRecentDockSiteInfo::SetInfo](#setinfo)||
|[CRecentDockSiteInfo::StoreDockInfo](#storedockinfo)||

## <a name="remarks"></a>설명

`CRecentDockSiteInfo` 클래스는 데이터 관리 클래스입니다. 이 클래스는 도킹과 부동 간에 전환될 때 `CPane`의 마지막 상태를 추적합니다. 사용자가 도킹 가능한 부동 창을 두 번 클릭하면 도킹됩니다. 도킹된 창을 두 번 클릭하면 이전 위치, 크기 및 상태로 돌아갑니다. 마찬가지로 창이 다시 도킹되면 이전 도킹 위치로 돌아갑니다. 이 데이터 클래스를 통해 이 작업을 수행할 수 있습니다. 이 클래스의 멤버는 도킹된 창에 대한 상태 정보를 저장하므로 애플리케이션에서 직접 수정할 수 없습니다.

`CRecentDockSiteInfo` 개체는 창을 만들 때마다 생성됩니다. 각 `CPane` 개체에는 멤버 변수 [M_recentdockinfo](../../mfc/reference/cpane-class.md#m_recentdockinfo),이 정보를 저장 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CRecentDockSiteInfo](../../mfc/reference/crecentdocksiteinfo-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxrecentDockSiteInfo.h

##  <a name="cleanup"></a>  CRecentDockSiteInfo::CleanUp

```
void CleanUp();
```

### <a name="remarks"></a>설명

##  <a name="crecentdocksiteinfo"></a>  CRecentDockSiteInfo::CRecentDockSiteInfo

```
CRecentDockSiteInfo(CPane* pBar);
```

### <a name="parameters"></a>매개 변수

[in] *pBar*<br/>

### <a name="remarks"></a>설명

##  <a name="getrecentdefaultpanedivider"></a>  CRecentDockSiteInfo::GetRecentDefaultPaneDivider

```
CPaneDivider* GetRecentDefaultPaneDivider();
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getrecentdockedpercent"></a>  CRecentDockSiteInfo::GetRecentDockedPercent

```
int GetRecentDockedPercent(BOOL bForSlider);
```

### <a name="parameters"></a>매개 변수

[in] *bForSlider*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getrecentdockedrect"></a>  CRecentDockSiteInfo::GetRecentDockedRect

```
CRect& GetRecentDockedRect(BOOL bForSlider);
```

### <a name="parameters"></a>매개 변수

[in] *bForSlider*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getrecentlistofpanes"></a>  CRecentDockSiteInfo::GetRecentListOfPanes

```
CList<HWND, HWND>& GetRecentListOfPanes(BOOL bForSlider);
```

### <a name="parameters"></a>매개 변수

[in] *bForSlider*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getrecentpanecontainer"></a>  CRecentDockSiteInfo::GetRecentPaneContainer

```
CPaneContainer* GetRecentPaneContainer(BOOL bForSlider);
```

### <a name="parameters"></a>매개 변수

[in] *bForSlider*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getrecenttabcontainer"></a>  CRecentDockSiteInfo::GetRecentTabContainer

```
CPaneContainer* GetRecentTabContainer(BOOL bForSlider);
```

### <a name="parameters"></a>매개 변수

[in] *bForSlider*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="init"></a>  CRecentDockSiteInfo::Init

```
void Init();
```

### <a name="remarks"></a>설명

##  <a name="isrecentleftpane"></a>  CRecentDockSiteInfo::IsRecentLeftPane

```
BOOL IsRecentLeftPane(BOOL bForSlider);
```

### <a name="parameters"></a>매개 변수

[in] *bForSlider*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="operator_eq"></a>  CRecentDockSiteInfo::operator =

```
CRecentDockSiteInfo& operator=(CRecentDockSiteInfo& src);
```

### <a name="parameters"></a>매개 변수

[in] *src*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="savelistofrecentpanes"></a>  CRecentDockSiteInfo::SaveListOfRecentPanes

```
void SaveListOfRecentPanes(CList<HWND,
    HWND>& lstOrg,
    BOOL bForSlider);
```

### <a name="parameters"></a>매개 변수

[in] *CList<HWND*<br/>
[in] *lstOrg*<br/>
[in] *bForSlider*<br/>

### <a name="remarks"></a>설명

##  <a name="setinfo"></a>  CRecentDockSiteInfo::SetInfo

```
virtual void SetInfo(
    BOOL bForSlider,
    CRecentDockSiteInfo& srcInfo);
```

### <a name="parameters"></a>매개 변수

[in] *bForSlider*<br/>
[in] *srcInfo*<br/>

### <a name="remarks"></a>설명

##  <a name="storedockinfo"></a>  CRecentDockSiteInfo::StoreDockInfo

```
virtual void StoreDockInfo(
    CPaneContainer* pRecentContainer,
    CDockablePane* pTabbedBar = NULL);
```

### <a name="parameters"></a>매개 변수

[in] *pRecentContainer*<br/>
[in] *pTabbedBar*<br/>

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CDockSite Class](../../mfc/reference/cdocksite-class.md)
