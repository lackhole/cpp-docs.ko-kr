---
title: CDockablePaneAdapter 클래스
ms.date: 11/04/2016
f1_keywords:
- CDockablePaneAdapter
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::GetWrappedWnd
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::LoadState
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::SaveState
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::SetWrappedWnd
helpviewer_keywords:
- CDockablePaneAdapter [MFC], GetWrappedWnd
- CDockablePaneAdapter [MFC], LoadState
- CDockablePaneAdapter [MFC], SaveState
- CDockablePaneAdapter [MFC], SetWrappedWnd
ms.assetid: 6ed6cf82-f39c-4d0c-bf7c-8641495cf8f3
ms.openlocfilehash: 8f184bab564b4867138608b735c67b328e1a21cc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391246"
---
# <a name="cdockablepaneadapter-class"></a>CDockablePaneAdapter 클래스

`CWnd`파생 창에 대해 도킹 지원을 제공합니다.

## <a name="syntax"></a>구문

```
class CDockablePaneAdapter : public CDockablePane
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CDockablePaneAdapter::GetWrappedWnd](#getwrappedwnd)|래핑된 창을 반환합니다.|
|[CDockablePaneAdapter::LoadState](#loadstate)|(재정의 [cdockablepane:: Loadstate](cdockablepane-class.md#loadstate).)|
|[CDockablePaneAdapter::SaveState](#savestate)|(재정의 [cdockablepane:: Savestate](cdockablepane-class.md).)|
|[CDockablePaneAdapter::SetWrappedWnd](#setwrappedwnd)||

## <a name="remarks"></a>설명

사용 하는 경우 프레임 워크가이 클래스의 개체를 인스턴스화하는 일반적으로 [cmfcbasetabctrl:: Addtab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) 하거나 [cmfcbasetabctrl:: Inserttab](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab) 메서드.

사용자 지정 하려는 경우는 `CDockablePaneAdapter` 동작을 방금에서 새 클래스를 파생 하 고 런타임 클래스 정보를 사용 하 여 탭된 창에 설정할 [cmfcbasetabctrl:: Setdockingbarwrapperrtc](../../mfc/reference/cmfcbasetabctrl-class.md#setdockingbarwrapperrtc)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CDockablePane](../../mfc/reference/cdockablepane-class.md)

[CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxDockablePaneAdapter.h

##  <a name="getwrappedwnd"></a>  CDockablePaneAdapter::GetWrappedWnd

도킹 가능한 창 어댑터에 대 한 기본 창을 반환합니다.

```
virtual CWnd* GetWrappedWnd() const;
```

### <a name="return-value"></a>반환 값

래핑된 창에 대 한 포인터입니다.

### <a name="remarks"></a>설명

래핑된 창에 액세스 하려면이 함수를 사용 합니다.

##  <a name="loadstate"></a>  CDockablePaneAdapter::LoadState

레지스트리에서 창의 상태를 로드합니다.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
[in] 프로필 이름입니다.

*nIndex*<br/>
[in] 프로필 인덱스입니다.

*uiID*<br/>
[in] 창 ID

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="savestate"></a>  CDockablePaneAdapter::SaveState

레지스트리에 창의 상태를 저장합니다.

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
[in] 프로필 이름입니다.

*nIndex*<br/>
[in] 프로필 인덱스 (기본값은 창의 컨트롤 ID)입니다.

*uiID*<br/>
[in] 창 ID

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="setwrappedwnd"></a>  CDockablePaneAdapter::SetWrappedWnd

도킹 가능한 창 어댑터에 대 한 기본 창을 설정합니다.

```
virtual BOOL SetWrappedWnd(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
[in] 래핑할 창 어댑터에 대 한 창에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane Class](../../mfc/reference/cdockablepane-class.md)
