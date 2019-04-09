---
title: CTooltipManager 클래스
ms.date: 11/04/2016
f1_keywords:
- CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager::CreateToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::DeleteToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipParams
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipText
- AFXTOOLTIPMANAGER/CTooltipManager::UpdateTooltips
helpviewer_keywords:
- CTooltipManager [MFC], CreateToolTip
- CTooltipManager [MFC], DeleteToolTip
- CTooltipManager [MFC], SetTooltipParams
- CTooltipManager [MFC], SetTooltipText
- CTooltipManager [MFC], UpdateTooltips
ms.assetid: c71779d7-8b6e-47ef-8500-d4552731fe86
ms.openlocfilehash: e8b88f2722f5a4379276f13c2ef159aa4d120533
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58776507"
---
# <a name="ctooltipmanager-class"></a>CTooltipManager 클래스

도구 설명에 대한 런타임 정보를 유지합니다. `CTooltipManager` 클래스는 응용 프로그램당 한 번씩 인스턴스화됩니다.

## <a name="syntax"></a>구문

```
class CTooltipManager : public CObject
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CTooltipManager::CreateToolTip](#createtooltip)|지정된 Windows 컨트롤 형식에 대한 도구 설명 컨트롤을 만듭니다.|
|[CTooltipManager::DeleteToolTip](#deletetooltip)|도구 설명 컨트롤을 삭제합니다.|
|[CTooltipManager::SetTooltipParams](#settooltipparams)|지정된 Windows 컨트롤 형식에 대한 도구 설명 컨트롤의 시각적 모양을 사용자 지정합니다.|
|[CTooltipManager::SetTooltipText](#settooltiptext)|도구 설명 컨트롤에 대한 텍스트 및 설명을 설정합니다.|
|[CTooltipManager::UpdateTooltips](#updatetooltips)||

## <a name="remarks"></a>설명

사용 하 여 [CMFCToolTipCtrl 클래스](../../mfc/reference/cmfctooltipctrl-class.md)하십시오 `CMFCToolTipInfo`, 및 `CTooltipManager` 응용 프로그램에서 사용자 지정된 도구 설명을 구현 하 합니다. 이러한 도구 설명 클래스를 사용 하는 방법의 예제를 참조 합니다 [CMFCToolTipCtrl 클래스](../../mfc/reference/cmfctooltipctrl-class.md) 항목입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxtooltipmanager.h

##  <a name="createtooltip"></a>  CTooltipManager::CreateToolTip

도구 설명 컨트롤을 만듭니다.

```
static BOOL CreateToolTip(
    CToolTipCtrl*& pToolTip,
    CWnd* pWndParent,
    UINT nType);
```

### <a name="parameters"></a>매개 변수

*pToolTip*<br/>
[out] 도구 설명 포인터에 대 한 참조입니다. 함수는 반환 될 때 새로 만든된 도구 설명이를 가리키도록 설정 됩니다.

*pWndParent*<br/>
[in] 도구 설명의 부모입니다.

*nType*<br/>
[in] 도구 설명의 형식입니다.

### <a name="return-value"></a>반환 값

도구 설명에 0이 아닌 경우 성공적으로 만들었습니다.

### <a name="remarks"></a>설명

호출 해야 합니다 [CTooltipManager::DeleteToolTip](#deletetooltip) 다시 전달 되는 도구 설명 컨트롤을 삭제 하려면 *pToolTip*합니다.

합니다 [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) 도구 설명에 따라 생성 하는 각 도구 설명의 시각적 표시 매개 변수 집합을 입력 하는 *n 형식* 지정 합니다. 하나 이상의 도구 설명 형식에 대 한 매개 변수를 변경 하려면 호출 [ctooltipmanager:: Settooltipparams](#settooltipparams)합니다.

올바른 도구 설명 유형이 다음 표에 나와 있습니다.

|Tooltip 형식|컨트롤 범주|예제 형식|
|------------------|----------------------|-------------------|
|AFX_TOOLTIP_TYPE_BUTTON|단추입니다.|CMFCButton|
|AFX_TOOLTIP_TYPE_CAPTIONBAR|캡션 표시줄입니다.|CMFCCaptionBar|
|AFX_TOOLTIP_TYPE_DEFAULT|다른 범주에 맞지 않는 모든 컨트롤입니다.|없음|
|AFX_TOOLTIP_TYPE_DOCKBAR|도킹 가능한 창입니다.|CDockablePane|
|AFX_TOOLTIP_TYPE_EDIT|텍스트 상자입니다.|없음|
|AFX_TOOLTIP_TYPE_MINIFRAME|미니 프레임을 합니다.|CPaneFrameWnd|
|AFX_TOOLTIP_TYPE_PLANNER|Planner 합니다.|없음|
|AFX_TOOLTIP_TYPE_RIBBON|리본 표시줄입니다.|CMFCRibbonBar, CMFCRibbonPanelMenuBar|
|AFX_TOOLTIP_TYPE_TAB|탭 컨트롤입니다.|CMFCTabCtrl|
|AFX_TOOLTIP_TYPE_TOOLBAR|도구 모음입니다.|CMFCToolBar, CMFCPopupMenuBar|
|AFX_TOOLTIP_TYPE_TOOLBOX|도구 상자입니다.|없음|

##  <a name="deletetooltip"></a>  CTooltipManager::DeleteToolTip

도구 설명 컨트롤을 삭제합니다.

```
static void DeleteToolTip(CToolTipCtrl*& pToolTip);
```

### <a name="parameters"></a>매개 변수

*pToolTip*<br/>
[out에서] 제거할 도구 설명에 대 한 포인터에 대 한 참조입니다.

### <a name="remarks"></a>설명

각각에 대해이 메서드를 호출 [CToolTipCtrl 클래스](../../mfc/reference/ctooltipctrl-class.md) 하 여 만들어진 [CTooltipManager::CreateToolTip](#createtooltip)합니다. 부모 컨트롤에서이 메서드를 호출 해야 해당 `OnDestroy` 처리기입니다. 이 프레임 워크에서 도구 설명을 제대로 제거 해야 합니다. 이 메서드를 설정 *pToolTip* 반환 하기 전에 NULL로 합니다.

##  <a name="settooltipparams"></a>  CTooltipManager::SetTooltipParams

지정된 된 Windows 컨트롤 형식에 대 한 도구 설명 컨트롤의 모양을 사용자 지정합니다.

```
void SetTooltipParams(
    UINT nTypes,
    CRuntimeClass* pRTC=RUNTIME_CLASS(CMFCToolTipCtrl),
    CMFCToolTipInfo* pParams=NULL);
```

### <a name="parameters"></a>매개 변수

*nTypes*<br/>
[in] 컨트롤 형식을 지정합니다.

*pRTC*<br/>
[in] 사용자 지정 도구 설명의 런타임 클래스입니다.

*pParams*<br/>
[in] 도구 설명 매개 변수입니다.

### <a name="remarks"></a>설명

이 메서드는 런타임 클래스 및 초기 매개 변수는 설정 된 [CToolTipManager](../../mfc/reference/ctooltipmanager-class.md) 도구 설명을 만들 때 사용 합니다. 컨트롤을 호출 하는 경우 [CTooltipManager::CreateToolTip](#createtooltip) 도구 설명에 전달 하 여 지정 된 형식 중 하나는 입력 *nTypes*, 도구 설명 관리자의 인스턴스는 도구 설명 컨트롤을 만듭니다는 지정 된 런타임 클래스 *pRTC* 로 지정 된 매개 변수 전달 *pParams* 새 도구 설명으로 합니다.

이 메서드를 호출 하 고 모든 기존 도구 설명 소유자 AFX_WM_UPDATETOOLTIPS 메시지가 해당 도구 설명이 사용 하 여 다시 만들어야 하는 경우 [CTooltipManager::CreateToolTip](#createtooltip)합니다.

*nTypes* 유형에 유효한 도구 설명의 조합 수 [CTooltipManager::CreateToolTip](#createtooltip) 사용 하거나 AFX_TOOLTIP_TYPE_ALL 될 수 있습니다. AFX_TOOLTIP_TYPE_ALL를 전달 하는 경우 도구 설명 유형도 영향을 받습니다.

### <a name="example"></a>예제

다음 예제에서는 사용 하는 방법에 설명 합니다 `SetTooltipParams` 메서드는 `CTooltipManager` 클래스입니다. 이 코드 조각은 [클라이언트 그리기 샘플](../../overview/visual-cpp-samples.md)의 일부입니다.

[!code-cpp[NVC_MFC_DrawClient#11](../../mfc/reference/codesnippet/cpp/ctooltipmanager-class_1.cpp)]

##  <a name="settooltiptext"></a>  CTooltipManager::SetTooltipText

텍스트 및 도구 설명에 대 한 설명을 설정합니다.

```
static void SetTooltipText(
    TOOLINFO* pTI,
    CToolTipCtrl* pToolTip,
    UINT nType,
    const CString strText,
    LPCTSTR lpszDescr=NULL);
```

### <a name="parameters"></a>매개 변수

*pTI*<br/>
[in] TOOLINFO 개체에 대 한 포인터입니다.

*pToolTip*<br/>
[out에서] 텍스트 및 설명을 설정 하는 도구 설명 컨트롤에 대 한 포인터입니다.

*nType*<br/>
[in] 이 도구 설명과 연결 된 컨트롤의 형식을 지정 합니다.

*strText*<br/>
[in] 텍스트 도구 설명 텍스트를 설정입니다.

*lpszDescr*<br/>
[in] 도구 설명에 대 한 포인터입니다. NULL 일 수 있습니다.

### <a name="remarks"></a>설명

변수의 *n 형식* 와 같은 값 이어야 합니다는 *n 형식* 의 매개 변수 [CTooltipManager::CreateToolTip](#createtooltip) 도구 설명을 만들 때.

##  <a name="updatetooltips"></a>  CTooltipManager::UpdateTooltips

더 자세한 내용은 Visual Studio 설치의 **VC\\atlmfc\\src\\mfc** 폴더에 있는 소스 코드를 참조하세요.

```
void UpdateTooltips();
```

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolTipCtrl 클래스](../../mfc/reference/cmfctooltipctrl-class.md)<br/>
[CMFCToolTipInfo 클래스](../../mfc/reference/cmfctooltipinfo-class.md)
