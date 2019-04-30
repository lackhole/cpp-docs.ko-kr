---
title: CSmartDockingInfo 클래스
ms.date: 11/19/2018
f1_keywords:
- CSmartDockingInfo
- AFXDOCKINGMANAGER/CSmartDockingInfo
- AFXDOCKINGMANAGER/CSmartDockingInfo::CopyTo
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_bUseThemeColorInShading
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrBaseBackground
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrToneDest
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrToneSrc
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrTransparent
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_nCentralGroupOffset
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_sizeTotal
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_uiMarkerBmpResID
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_uiMarkerLightBmpResID
helpviewer_keywords:
- CSmartDockingInfo [MFC], CopyTo
- CSmartDockingInfo [MFC], m_bUseThemeColorInShading
- CSmartDockingInfo [MFC], m_clrBaseBackground
- CSmartDockingInfo [MFC], m_clrToneDest
- CSmartDockingInfo [MFC], m_clrToneSrc
- CSmartDockingInfo [MFC], m_clrTransparent
- CSmartDockingInfo [MFC], m_nCentralGroupOffset
- CSmartDockingInfo [MFC], m_sizeTotal
- CSmartDockingInfo [MFC], m_uiMarkerBmpResID
- CSmartDockingInfo [MFC], m_uiMarkerLightBmpResID
ms.assetid: cab04f38-4bc1-4378-9337-c56fc87fbd68
ms.openlocfilehash: d5f918b591e1db9ff67288a8761f7554698fa761
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324007"
---
# <a name="csmartdockinginfo-class"></a>CSmartDockingInfo 클래스

스마트 도킹 표식의 모양을 정의합니다.

## <a name="syntax"></a>구문

```
class CSmartDockingInfo : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|`CSmartDockingInfo::CSmartDockingInfo`|기본 생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CSmartDockingInfo::CopyTo](#copyto)|현재 스마트 도킹 정보 매개 변수를 제공 된 복사 [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) 개체입니다.|

### <a name="data-members"></a>데이터 멤버

|이름|설명|
|----------|-----------------|
|[CSmartDockingInfo::m_bUseThemeColorInShading](#m_busethemecolorinshading)|프레임 워크 스마트 도킹 표식 표시 되 면 현재 테마 색을 사용할지 여부를 지정 합니다.|
|[CSmartDockingInfo::m_clrBaseBackground](#m_clrbasebackground)|스마트 도킹 표식의 기본 배경색을 지정 합니다.|
|[CSmartDockingInfo::m_clrToneDest](#m_clrtonedest)|대체 하는 색을 지정 `m_clrToneSrc` 스마트 도킹 표식 비트맵에서입니다.|
|[CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc)|스마트 도킹 표식 비트맵의 색을 지정 합니다.|
|[CSmartDockingInfo::m_clrTransparent](#m_clrtransparent)|투명 한 경우 스마트 도킹 표식 비트맵의 색을 지정 합니다.|
|[CSmartDockingInfo::m_nCentralGroupOffset](#m_ncentralgroupoffset)|스마트 도킹 표식 중앙 그룹 직사각형의 경계에서 중앙 그룹의 오프셋을 지정합니다.|
|[CSmartDockingInfo::m_sizeTotal](#m_sizetotal)|그룹의 모든 스마트 도킹 표식의 총 크기를 지정합니다.|
|[CSmartDockingInfo::m_uiMarkerBmpResID](#m_uimarkerbmpresid)|강조 표시 되지 않는 스마트 도킹 표식에 대 한 프레임 워크를 사용 하는 비트맵의 리소스 Id를 정의 합니다.|
|[CSmartDockingInfo::m_uiMarkerLightBmpResID](#m_uimarkerlightbmpresid)|강조 표시 되는 스마트 도킹 표식에 대 한 프레임 워크를 사용 하는 비트맵의 리소스 Id를 정의 합니다.|

## <a name="remarks"></a>설명

프레임 워크 처리는 내부적으로 도킹 표식 스마트합니다. 다음 그림에서는 표준 스마트 도킹 표식 보여 줍니다.

![스마트 도킹의 표준 마커](../../mfc/reference/media/nextsdmarkers.png "스마트 도킹의 표준 마커")

이 그림에서 왼쪽에서 이미지를 사용 하도록 설정 하는 탭으로 도킹 되지 않은 중앙 그룹 스마트 도킹 표식 보여 줍니다. 가운데에서 이미지에는 오른쪽 가장자리 스마트 도킹 표식을 보여 줍니다. 오른쪽에서 이미지를 사용 하도록 설정 하는 탭으로 도킹 없는 중앙 그룹 스마트 도킹 표식 보여 줍니다. 중앙 그룹 스마트 도킹 표식의 주 비트맵 및 5 스마트 도킹 표식 비트맵입니다.

스마트 도킹 표식의 다음 매개 변수를 사용자 지정할 수 있습니다.

- 색 예를 들어, 사용자 정의 색을 사용 하 여 표식 그림에서의 파란색을 바꿀 수 있습니다.

- 투명도 색입니다.

- 경계 사각형의 테두리에서 중앙 그룹의 스마트 도킹 표식의 오프셋입니다.

- 중앙 그룹을 나타내는 기본 비트맵입니다.

- 일반 및 강조 표시 된 스마트 도킹 표식 나타내는 비트맵입니다.

다음 그림에서는 사용자 지정 된 스마트 도킹 표식의 예를 보여 줍니다.

![스마트 도킹의 사용자 지정 마커](../../mfc/reference/media/nextsdmarkerscustom.png "스마트 도킹의 사용자 지정 마커")

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxDockingManager.h

##  <a name="copyto"></a>  CSmartDockingInfo::CopyTo

현재 스마트 도킹 매개 변수에 제공 된 복사 [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) 개체입니다.

```
void CopyTo(CSmartDockingInfo& params);
```

### <a name="parameters"></a>매개 변수

*params*<br/>
[out] 형식의 개체 `CSmartDockingInfo` 는 현재 스마트 도킹 매개 변수를 사용 하 여 채워집니다.

##  <a name="m_busethemecolorinshading"></a>  CSmartDockingInfo::m_bUseThemeColorInShading

프레임 워크 스마트 도킹 표식 표시 되 면 현재 테마 색을 사용할지 여부를 지정 합니다.

```
BOOL m_bUseThemeColorInShading;
```

### <a name="remarks"></a>설명

표식; 현재 테마 색을 사용 하 여 그려지는 TRUE 인 경우 그렇지 않은 경우 표식 밝은 파란색으로 그려집니다.

기본값은 FALSE입니다.

##  <a name="m_clrbasebackground"></a>  CSmartDockingInfo::m_clrBaseBackground

스마트 도킹 표식의 기본 배경색을 지정 합니다.

```
COLORREF m_clrBaseBackground;
```

##  <a name="m_clrtonedest"></a>  CSmartDockingInfo::m_clrToneDest

대체 하는 색을 지정 `m_clrToneSrc` 스마트 도킹 표식 비트맵에서입니다.

```
COLORREF m_clrToneDest;
```

### <a name="remarks"></a>설명

프로그래밍 방식으로 표식 비트맵의 색을 변경 하려면이 값을 설정 합니다. 예를 들어, 프레임 워크를 사용 하 여 제공 된 표준 표식의 색을 변경 하려는 경우이 값을 원하는 색으로 설정 합니다. 기본적으로 [CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc) RGB (61, 123, 241)로 설정 됩니다 (파랑 추가 색).

사용자 지정 표식 색을 변경 하려면 모두 지정 해야 `m_clrToneDest` 고 `m_clrToneSrc`입니다.

##  <a name="m_clrtonesrc"></a>  CSmartDockingInfo::m_clrToneSrc

스마트 도킹 표식 비트맵의 색을 지정 합니다.

```
COLORREF m_clrToneSrc;
```

### <a name="remarks"></a>설명

사용자 지정 비트맵의 색 다른 색으로 대체 하려는 경우에이 값을 설정 합니다. 표준 (제공 된 프레임 워크)의 색을 변경 하는 경우이 값을 설정할 필요가 없습니다 표식입니다.

사용 하 여 `(COLORREF)-1` 에 스마트 도킹 그룹의 멤버를 비워 둡니다.

##  <a name="m_clrtransparent"></a>  CSmartDockingInfo::m_clrTransparent

투명 한 경우 스마트 도킹 표식 비트맵의 색을 지정 합니다.

```
COLORREF m_clrTransparent;
```

### <a name="remarks"></a>설명

도킹 된 그룹에 사용자 지정 표식 및 사용자 지정 비트맵을 표시 하는 경우에이 값을 설정 해야 합니다.

##  <a name="m_ncentralgroupoffset"></a>  CSmartDockingInfo::m_nCentralGroupOffset

스마트 도킹 표식의 중앙 그룹과 중앙 그룹 직사각형의 경계 사이의 오프셋을 지정 합니다.

```
int m_nCentralGroupOffset;
```

### <a name="remarks"></a>설명

사용자 지정 표식 및 스마트 도킹 표식의 중앙 그룹의 경계 간에 기본 오프셋을 변경 하려는 경우이 값을 지정 합니다. 기본 오프셋은 5 픽셀입니다.

##  <a name="m_sizetotal"></a>  CSmartDockingInfo::m_sizeTotal

중앙 그룹에서 모든 스마트 도킹 표식을 둘러싸는 경계 사각형의 전체 크기를 지정 합니다.

```
CSize m_sizeTotal;
```

### <a name="remarks"></a>설명

설정 `m_sizeTotal` 중앙 그룹 표식의 경계 사각형의 크기입니다. 표식에 대 한 사용자 지정 비트맵을 사용 하는 경우이 값을 지정 해야 합니다.

##  <a name="m_uimarkerbmpresid"></a>  CSmartDockingInfo::m_uiMarkerBmpResID

강조 표시 되지 않은 사용자 지정 스마트 도킹 표식에 사용 되는 비트맵의 리소스 Id를 정의 합니다.

```
UINT m_uiMarkerBmpResID[AFX_SD_MARKERS_NUM];
```

### <a name="remarks"></a>설명

스마트 도킹 표식 나타내는 비트맵의 리소스 Id 사용 하 여이 배열을 채웁니다. AFX_SD_MARKERS_NUM는 현재 5로 정의 됩니다. 배열을 다음과 같이 입력합니다.

```cpp
params.m_uiMarkerBmpResID[0] = IDB_MARKER_LEFT;
params.m_uiMarkerBmpResID[1] = IDB_MARKER_RIGHT;
params.m_uiMarkerBmpResID[2] = IDB_MARKER_TOP;
params.m_uiMarkerBmpResID[3] = IDB_MARKER_BOTTOM;
params.m_uiMarkerBmpResID[4] = IDB_MARKER_CENTER;
```

##  <a name="m_uimarkerlightbmpresid"></a>  CSmartDockingInfo::m_uiMarkerLightBmpResID

강조 표시 된 사용자 지정 스마트 도킹 표식에 사용 되는 비트맵의 리소스 Id를 정의 합니다.

```
UINT m_uiMarkerLightBmpResID[AFX_SD_MARKERS_NUM];
```

### <a name="remarks"></a>설명

강조 표시 된 스마트 도킹 표식 나타내는 비트맵의 리소스 Id 사용 하 여이 배열을 채웁니다. AFX_SD_MARKERS_NUM는 현재 5로 정의 됩니다. 배열을 다음과 같이 입력합니다.

```cpp
params.m_uiMarkerLightBmpResID[0] = IDB_MARKER_LEFT_LIGHT;
params.m_uiMarkerLightBmpResID[1] = IDB_MARKER_RIGHT_LIGHT;
params.m_uiMarkerLightBmpResID[2] = IDB_MARKER_TOP_LIGHT;
params.m_uiMarkerLightBmpResID[3] = IDB_MARKER_BOTTOM_LIGHT;
params.m_uiMarkerLightBmpResID[4] = IDB_MARKER_CENTER_LIGHT;
```

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)
