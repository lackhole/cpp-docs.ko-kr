---
title: CMFCBaseVisualManager 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager::CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawCheckBox
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawComboBorder
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawComboDropButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawPushButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawRadioButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawStatusBarProgress
- AFXVISUALMANAGER/CMFCBaseVisualManager::FillReBarPane
- AFXVISUALMANAGER/CMFCBaseVisualManager::GetStandardWindowsTheme
- AFXVISUALMANAGER/CMFCBaseVisualManager::CleanUpThemes
- AFXVISUALMANAGER/CMFCBaseVisualManager::UpdateSystemColors
helpviewer_keywords:
- CMFCBaseVisualManager [MFC], CMFCBaseVisualManager
- CMFCBaseVisualManager [MFC], DrawCheckBox
- CMFCBaseVisualManager [MFC], DrawComboBorder
- CMFCBaseVisualManager [MFC], DrawComboDropButton
- CMFCBaseVisualManager [MFC], DrawPushButton
- CMFCBaseVisualManager [MFC], DrawRadioButton
- CMFCBaseVisualManager [MFC], DrawStatusBarProgress
- CMFCBaseVisualManager [MFC], FillReBarPane
- CMFCBaseVisualManager [MFC], GetStandardWindowsTheme
- CMFCBaseVisualManager [MFC], CleanUpThemes
- CMFCBaseVisualManager [MFC], UpdateSystemColors
ms.assetid: d56f3afc-cdea-4de1-825a-a08999c571e0
ms.openlocfilehash: 0c26c0c9c9026f8312218b2ac15f83a50a67be79
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403856"
---
# <a name="cmfcbasevisualmanager-class"></a>CMFCBaseVisualManager 클래스

Windows 테마 API 파생된 비주얼 관리자 사이의 계층입니다.

`CMFCBaseVisualManager` 사용 가능한 경우 UxTheme.dll을 로드 하 고 Windows 테마 API 메서드에 대 한 액세스를 관리 합니다.

이 클래스는 내부 전용입니다.

## <a name="syntax"></a>구문

```
class CMFCBaseVisualManager: public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|||
|-|-|
|이름|설명|
|[CMFCBaseVisualManager::CMFCBaseVisualManager](#cmfcbasevisualmanager)|`CMFCBaseVisualManager` 개체를 생성하고 초기화합니다.|
|`CMFCBaseVisualManager::~CMFCBaseVisualManager`|소멸자|

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|이름|설명|
|[CMFCBaseVisualManager::DrawCheckBox](#drawcheckbox)|현재 Windows 테마를 사용 하 여 확인란 컨트롤을 그립니다.|
|[CMFCBaseVisualManager::DrawComboBorder](#drawcomboborder)|현재 Windows 테마를 사용 하 여 콤보 상자 테두리를 그립니다.|
|[CMFCBaseVisualManager::DrawComboDropButton](#drawcombodropbutton)|현재 Windows 테마를 사용 하 여 콤보 상자 드롭다운 단추를 그립니다.|
|[CMFCBaseVisualManager::DrawPushButton](#drawpushbutton)|현재 Windows 테마를 사용 하 여 푸시 단추를 그립니다.|
|[CMFCBaseVisualManager::DrawRadioButton](#drawradiobutton)|현재 Windows 테마를 사용 하 여 라디오 단추 컨트롤을 그립니다.|
|[CMFCBaseVisualManager::DrawStatusBarProgress](#drawstatusbarprogress)|진행률 표시줄 상태 표시줄 컨트롤을 그립니다 ( [CMFCStatusBar 클래스](../../mfc/reference/cmfcstatusbar-class.md))은 현재 Windows 테마를 사용 하 여 합니다.|
|[CMFCBaseVisualManager::FillReBarPane](#fillrebarpane)|현재 Windows 테마를 사용 하 여 rebar 컨트롤의 배경을 채웁니다.|
|[CMFCBaseVisualManager::GetStandardWindowsTheme](#getstandardwindowstheme)|현재 Windows 테마를 가져옵니다.|

### <a name="protected-methods"></a>Protected 메서드

|||
|-|-|
|이름|설명|
|[CMFCBaseVisualManager::CleanUpThemes](#cleanupthemes)|호출 `CloseThemeData` 에서 얻은 모든 핸들에 대 한 `UpdateSystemColors`합니다.|
|[CMFCBaseVisualManager::UpdateSystemColors](#updatesystemcolors)|호출 `OpenThemeData` 다양 한 컨트롤 그리기에 대 한 핸들을 가져오는 데: windows, 도구 모음, 단추 및 등입니다.|

## <a name="remarks"></a>설명

이 클래스의 개체를 직접 인스턴스화할 필요가 없습니다.

호출 하기만 하면 모든 비주얼 관리자에 대 한 기본 클래스 이므로 [CMFCVisualManager::GetInstance](../../mfc/reference/cmfcvisualmanager-class.md#getinstance)대 한 포인터에는 현재 비주얼 관리자를 가져오고에 대 한 메서드에 액세스할 `CMFCBaseVisualManager` 해당 포인터를 사용 하 여 합니다. 그러나 현재 Windows 테마를 사용 하 여 컨트롤을 표시 해야 할 경우 것이 좋습니다 사용 하 여 `CMFCVisualManagerWindows` 인터페이스.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxvisualmanager.h

##  <a name="cleanupthemes"></a>  CMFCBaseVisualManager::CleanUpThemes

호출 `CloseThemeData` 에서 얻은 모든 핸들에 대 한 `UpdateSystemColors`합니다.

```
void CleanUpThemes();
```

### <a name="remarks"></a>설명

내부 전용입니다.

##  <a name="cmfcbasevisualmanager"></a>  CMFCBaseVisualManager::CMFCBaseVisualManager

`CMFCBaseVisualManager` 개체를 생성하고 초기화합니다.

```
CMFCBaseVisualManager();
```

##  <a name="drawcheckbox"></a>  CMFCBaseVisualManager::DrawCheckBox

현재 Windows 테마를 사용 하 여 확인란 컨트롤을 그립니다.

```
virtual BOOL DrawCheckBox(
    CDC* pDC,
    CRect rect,
    BOOL bHighlighted,
    int nState,
    BOOL bEnabled,
    BOOL bPressed);

);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터

*rect*<br/>
[in] 확인란의 경계 사각형입니다.

*bHighlighted*<br/>
[in] 확인란은 강조 표시 여부를 지정 합니다.

*nState*<br/>
[in] 0 확인 된 정상에 대 한 옵션을 선택 취소 1

보통의 혼합 2입니다.

*bEnabled*<br/>
[in] 확인란 사용 되는지 여부를 지정 합니다.

*bPressed*<br/>
[in] 확인란을 눌렀는지 여부를 지정 합니다.

### <a name="return-value"></a>반환 값

테마 API를 사용 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

값 *nState* 확인란 스타일에 해당 합니다.

|nState|확인란 스타일|
|------------|---------------------|
|0|CBS_UNCHECKEDNORMAL|
|1|CBS_CHECKEDNORMAL|
|2|CBS_MIXEDNORMAL|

##  <a name="drawcomboborder"></a>  CMFCBaseVisualManager::DrawComboBorder

현재 Windows 테마를 사용 하 여 콤보 상자 테두리를 그립니다.

```
virtual BOOL DrawComboBorder(
    CDC* pDC,
    CRect rect,
    BOOL bDisabled,
    BOOL bIsDropped,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터입니다.

*rect*<br/>
[in] 콤보 상자 테두리의 경계 사각형입니다.

*bDisabled*<br/>
[in] 콤보 상자 테두리 비활성화 되었는지 여부를 지정 합니다.

*bIsDropped*<br/>
[in] 콤보 상자 테두리를 삭제할지 여부를 지정 합니다.

*bIsHighlighted*<br/>
[in] 콤보 상자 테두리에 강조 표시 되어 있는지 여부를 지정 합니다.

### <a name="return-value"></a>반환 값

테마 API를 사용 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="drawcombodropbutton"></a>  CMFCBaseVisualManager::DrawComboDropButton

현재 Windows 테마를 사용 하 여 콤보 상자 드롭다운 단추를 그립니다.

```
virtual BOOL DrawComboDropButton(
    CDC* pDC,
    CRect rect,
    BOOL bDisabled,
    BOOL bIsDropped,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*pDC*|[in] 장치 컨텍스트에 대 한 포인터입니다.|
|*rect*|[in] 콤보 상자 드롭다운 단추의 경계 사각형입니다.|
|*bDisabled*|[in] 콤보 상자 드롭다운 단추를 사용할 수 있는지 여부를 지정 합니다.|
|*bIsDropped*|[in] 콤보 상자 드롭다운 단추를 삭제할지 여부를 지정 합니다.|
|*bIsHighlighted*|[in] 콤보 상자 드롭다운 단추를 강조 표시 되어 있는지 여부를 지정 합니다.|

### <a name="return-value"></a>반환 값

테마 API를 사용 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="drawpushbutton"></a>  CMFCBaseVisualManager::DrawPushButton

현재 Windows 테마를 사용 하 여 푸시 단추를 그립니다.

```
virtual BOOL DrawPushButton(
    CDC* pDC,
    CRect rect,
    CMFCButton* pButton,
    UINT uiState);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터입니다.

*rect*<br/>
[in] 누름 단추의 경계 사각형입니다.

*pButton*<br/>
[in] 에 대 한 포인터를 [CMFCButton 클래스](../../mfc/reference/cmfcbutton-class.md) 그릴 개체입니다.

*uiState*<br/>
[in] Ignored. 상태를 가져옵니다 *pButton*합니다.

### <a name="return-value"></a>반환 값

테마 API를 사용 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="drawradiobutton"></a>  CMFCBaseVisualManager::DrawRadioButton

현재 Windows 테마를 사용 하 여 라디오 단추 컨트롤을 그립니다.

```
virtual BOOL DrawRadioButton(
    CDC* pDC,
    CRect rect,
    BOOL bHighlighted,
    BOOL bChecked,
    BOOL bEnabled,
    BOOL bPressed);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터입니다.

*rect*<br/>
[in] 라디오 단추의 경계 사각형입니다.

*bHighlighted*<br/>
[in] 라디오 단추가 강조 표시 하는지 여부를 지정 합니다.

*bChecked*<br/>
[in] 라디오 단추가 선택 되었는지 여부를 지정 합니다.

*bEnabled*<br/>
[in] 라디오 단추를 사용할 수 있는지 여부를 지정 합니다.

*bPressed*<br/>
[in] 라디오 단추를 눌렀는지 여부를 지정 합니다.

### <a name="return-value"></a>반환 값

테마 API를 사용 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="drawstatusbarprogress"></a>  CMFCBaseVisualManager::DrawStatusBarProgress

상태 표시줄 컨트롤에서 진행률 표시줄을 그리는 ( [CMFCStatusBar 클래스](../../mfc/reference/cmfcstatusbar-class.md))은 현재 Windows 테마를 사용 하 여 합니다.

```
virtual BOOL DrawStatusBarProgress(
    CDC* pDC,
    CMFCStatusBar* pStatusBar,
    CRect rectProgress,
    int nProgressTotal,
    int nProgressCurr,
    COLORREF clrBar,
    COLORREF clrProgressBarDest,
    COLORREF clrProgressText,
    BOOL bProgressText);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터입니다.

*pStatusBar*<br/>
[in] 상태 표시줄에 대 한 포인터입니다. 이 값은 무시됩니다.

*rectProgress*<br/>
[in] 진행률 표시줄의 경계 사각형 *pDC* 좌표입니다.

*nProgressTotal*<br/>
[in] 총 진행률 값입니다.

*nProgressCurr*<br/>
[in] 현재 진행률 값입니다.

*clrBar*<br/>
[in] 시작 색입니다. `CMFCBaseVisualManager` 이 무시합니다. 파생된 클래스 색 그라데이션에 사용할 수 있습니다.

*clrProgressBarDest*<br/>
[in] 마지막 색입니다. `CMFCBaseVisualManager` 이 무시합니다. 파생된 클래스 색 그라데이션에 사용할 수 있습니다.

*clrProgressText*<br/>
[in] 진행률 텍스트 색입니다. `CMFCBaseVisualManager` 이 무시합니다. 텍스트 색을 정의한 `afxGlobalData.clrBtnText`합니다.

*bProgressText*<br/>
[in] 진행률 텍스트를 표시할지 여부를 지정 합니다.

### <a name="return-value"></a>반환 값

테마 API를 사용 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="fillrebarpane"></a>  CMFCBaseVisualManager::FillReBarPane

현재 Windows 테마를 사용 하 여 rebar 컨트롤의 배경을 채웁니다.

```
virtual void FillReBarPane(
    CDC* pDC,
    CBasePane* pBar,
    CRect rectClient);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터입니다.

*pBar*<br/>
[in] 해당 배경을 그려야 하는 창에 대 한 포인터입니다.

*rectClient*<br/>
[in] 채워질 영역 경계 사각형입니다.

### <a name="return-value"></a>반환 값

테마 API를 사용 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="getstandardwindowstheme"></a>  CMFCBaseVisualManager::GetStandardWindowsTheme

현재 Windows 테마를 가져옵니다.

```
virtual WinXpTheme GetStandardWindowsTheme();
```

### <a name="return-value"></a>반환 값

현재 선택한 Windows 테마 색입니다. 다음 열거형된 값 중 하나일 수 있습니다.

- `WinXpTheme_None` -는 테마를 사용할 수 없음.

- `WinXpTheme_NonStandard` -(테마는 선택 되어, 있지만 아래 목록에서 없음을 의미) 비표준 테마를 선택 합니다.

- `WinXpTheme_Blue` -파랑 테마 (Luna).

- `WinXpTheme_Olive` -올리브색 테마입니다.

- `WinXpTheme_Silver` -은색 테마입니다.

##  <a name="updatesystemcolors"></a>  CMFCBaseVisualManager::UpdateSystemColors

호출 `OpenThemeData` 다양 한 컨트롤 그리기에 대 한 핸들을 가져오는 데: windows, 도구 모음, 단추 및 등입니다.

```
void UpdateSystemColors();
```

### <a name="remarks"></a>설명

내부 전용입니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)
