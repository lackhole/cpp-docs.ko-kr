---
title: CMFCShellTreeCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCShellTreeCtrl
- AFXSHELLTREECTRL/CMFCShellTreeCtrl
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::EnableShellContextMenu
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetFlags
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetItemPath
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetRelatedList
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnChildNotify
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnGetItemIcon
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnGetItemText
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::Refresh
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SelectPath
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SetFlags
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SetRelatedList
helpviewer_keywords:
- CMFCShellTreeCtrl [MFC], EnableShellContextMenu
- CMFCShellTreeCtrl [MFC], GetFlags
- CMFCShellTreeCtrl [MFC], GetItemPath
- CMFCShellTreeCtrl [MFC], GetRelatedList
- CMFCShellTreeCtrl [MFC], OnChildNotify
- CMFCShellTreeCtrl [MFC], OnGetItemIcon
- CMFCShellTreeCtrl [MFC], OnGetItemText
- CMFCShellTreeCtrl [MFC], Refresh
- CMFCShellTreeCtrl [MFC], SelectPath
- CMFCShellTreeCtrl [MFC], SetFlags
- CMFCShellTreeCtrl [MFC], SetRelatedList
ms.assetid: 3d1da715-9554-4ed7-968c-055c48146267
ms.openlocfilehash: 1fc422c3aca3efe1fb177e7a3567530d70c27119
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58779757"
---
# <a name="cmfcshelltreectrl-class"></a>CMFCShellTreeCtrl 클래스

합니다 `CMFCShellTreeCtrl` 클래스를 확장 [CTreeCtrl 클래스](../../mfc/reference/ctreectrl-class.md) 셸 항목의 계층 구조를 표시 하 여 기능 합니다.

더 자세한 내용은 Visual Studio 설치의 **VC\\atlmfc\\src\\mfc** 폴더에 있는 소스 코드를 참조하세요.
## <a name="syntax"></a>구문

```
class CMFCShellTreeCtrl : public CTreeCtrl
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCShellTreeCtrl::EnableShellContextMenu](#enableshellcontextmenu)|사용 하거나 바로 가기 메뉴를 사용 하지 않도록 설정 합니다.|
|[CMFCShellTreeCtrl::GetFlags](#getflags)|에 전달 되는 플래그의 조합을 반환 [IShellFolder::EnumObjects](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects)합니다.|
|[CMFCShellTreeCtrl::GetItemPath](#getitempath)|항목에 대 한 경로 검색합니다.|
|[CMFCShellTreeCtrl::GetRelatedList](#getrelatedlist)|에 대 한 포인터를 반환 합니다는 [CMFCShellListCtrl 클래스](../../mfc/reference/cmfcshelllistctrl-class.md) 이 함께 사용 되는 개체 `CMFCShellTreeCtrl` 개체는 탐색기와 유사한 창을 만들 수 있습니다.|
|[CMFCShellTreeCtrl::OnChildNotify](#onchildnotify)|이 멤버 함수는이 창에 적용 되는 알림 메시지를 받으면이 창의 부모 창에서 호출 됩니다. (재정의 [cwnd:: Onchildnotify](../../mfc/reference/cwnd-class.md#onchildnotify).)|
|[CMFCShellTreeCtrl::OnGetItemIcon](#ongetitemicon)||
|[CMFCShellTreeCtrl::OnGetItemText](#ongetitemtext)||
|[CMFCShellTreeCtrl::Refresh](#refresh)|현재 다시 표시를 새로 고치고 `CMFCShellTreeCtrl` 개체입니다.|
|[CMFCShellTreeCtrl::SelectPath](#selectpath)|제공 된 PIDL 또는 문자열 경로에 따라 적절 한 트리 컨트롤 항목을 선택 합니다.|
|[CMFCShellTreeCtrl::SetFlags](#setflags)|트리에서 컨텍스트를 필터링 하는 플래그를 설정 합니다 (사용 하는 플래그 비슷합니다 `IShellFolder::EnumObjects`).|
|[CMFCShellTreeCtrl::SetRelatedList](#setrelatedlist)|현재 간에 관계를 설정 `CMFCShellTreeCtrl` 개체 및 `CMFCShellListCtrl` 개체입니다.|

## <a name="remarks"></a>설명

이 클래스는 확장 된 `CTreeCtrl` 트리에서 Windows 셸 항목을 포함 하도록 프로그램을 사용 하 여 클래스입니다. 이 클래스와 연결 될 수는 `CMFCShellListCtrl` 전체 탐색기 창을 만드는 개체입니다. 그런 다음 트리에서 항목을 선택 하면 관련된 된 목록에서 Windows 셸 항목의 목록이 표시 됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CTreeCtrl](../../mfc/reference/ctreectrl-class.md)

`CMFCShellTreeCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxshelltreeCtrl.h

## <a name="example"></a>예제

다음 예제에서는 `CMFCShellTreeCtrl` 클래스의 개체를 만드는 방법을 보여 줍니다. 이 코드 조각은의 일부인 합니다 [탐색기 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_Explorer#4](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_1.h)]
[!code-cpp[NVC_MFC_Explorer#5](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_2.cpp)]

##  <a name="enableshellcontextmenu"></a>  CMFCShellTreeCtrl::EnableShellContextMenu

바로 가기 메뉴를 사용 하도록 설정 합니다.

```
void EnableShellContextMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
[in] 바로 가기 메뉴를 사용 하도록 설정 여부를 지정 하는 부울입니다.

##  <a name="getflags"></a>  CMFCShellTreeCtrl::GetFlags

에 대 한 설정 된 플래그를 반환 합니다 [CMFCShellTreeCtrl 클래스](../../mfc/reference/cmfcshelltreectrl-class.md) 개체입니다.

```
DWORD GetFlags() const;
```

### <a name="return-value"></a>반환 값

현재 플래그의 조합을 지정 하는 DWORD 값을 설정 합니다.

### <a name="remarks"></a>설명

플래그를 설정 합니다 `CMFCShellTreeCtrl` 메서드에 전송 됩니다 [IShellFolder::EnumObjects](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects) 때마다 개체가 새로 고쳐집니다. 플래그를 변경할 수 있습니다 합니다 [CMFCShellTreeCtrl::SetFlags](#setflags) 메서드.

##  <a name="getitempath"></a>  CMFCShellTreeCtrl::GetItemPath

에 있는 항목의 경로 검색 합니다 [CMFCShellTreeCtrl 클래스](../../mfc/reference/cmfcshelltreectrl-class.md) 개체입니다.

```
BOOL GetItemPath(
    CString& strPath,
    HTREEITEM htreeItem = NULL) const;
```

### <a name="parameters"></a>매개 변수

*strPath*<br/>
[out] 문자열 매개 변수 참조입니다. 메서드는이 매개 변수를 항목의 경로 씁니다.

*htreeItem*<br/>
[in] 메서드는이 트리 컨트롤 항목에 대 한 경로 검색합니다.

### <a name="return-value"></a>반환 값

성공하는 경우 0이 아닌 값입니다. 그렇지 않은 경우 0입니다.

### <a name="remarks"></a>설명

이 방법이 실패 하면 *strPath* 빈 문자열이 포함 됩니다.

지정 하지 않는 경우 *hTreeItem*,이 메서드는 현재 선택된 된 항목에 대 한 문자열을 가져오려고 시도 합니다. 이 경우 및 *hTreeItem* 가 null 인 경우이 메서드는 실패 합니다.

##  <a name="getrelatedlist"></a>  CMFCShellTreeCtrl::GetRelatedList

에 대 한 포인터를 반환 합니다 [CMFCShellListCtrl 클래스](../../mfc/reference/cmfcshelllistctrl-class.md) 이 사용 하 여 연결 된 개체 [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) 개체입니다.

```
CMFCShellListCtrl* GetRelatedList() const;
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `CMFCShellListCtrl` 이 트리 컨트롤 개체와 연결 된 개체입니다.

### <a name="remarks"></a>설명

사용 하 여는 `CMFCShellListCtrl` 와 함께 개체를 `CMFCShellTreeCtrl` 개체는 탐색기와 유사한 창을 만들 수 있습니다. 메서드를 사용 하 여 [CMFCShellTreeCtrl::SetRelatedList](#setrelatedlist) 두 클래스를 연결 합니다. 프레임 워크를 자동으로 업데이트 연결을 `CMFCShellListCtrl` 경우에서 선택 항목을 `CMFCShellTreeCtrl` 변경 합니다.

##  <a name="onchildnotify"></a>  CMFCShellTreeCtrl::OnChildNotify

```
virtual BOOL OnChildNotify(
    UINT message,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT* pLResult);
```

### <a name="parameters"></a>매개 변수

[in] *message*<br/>
[in] *wParam*<br/>
[in] *lParam*<br/>
[in] *pLResult*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="ongetitemicon"></a>  CMFCShellTreeCtrl::OnGetItemIcon

```
virtual int OnGetItemIcon(
    LPAFX_SHELLITEMINFO pItem,
    BOOL bSelected);
```

### <a name="parameters"></a>매개 변수

[in] *pItem*<br/>
[in] *bSelected*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="ongetitemtext"></a>  CMFCShellTreeCtrl::OnGetItemText

```
virtual CString OnGetItemText(LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>매개 변수

[in] *pItem*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="refresh"></a>  CMFCShellTreeCtrl::Refresh

새로 고쳐지고 다시 표시 합니다 [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md)합니다.

```
void Refresh();
```

### <a name="remarks"></a>설명

에 표시 된 항목의 계층 구조를 새로 고치려면이 메서드를 호출 합니다 `CMFCShellTreeCtrl`합니다.

##  <a name="selectpath"></a>  CMFCShellTreeCtrl::SelectPath

항목을 선택 합니다 [CMFCShellTreeCtrl 클래스](../../mfc/reference/cmfcshelltreectrl-class.md) 제공 된 경로 기반으로 합니다.

```
BOOL SelectPath(LPCTSTR lpszPath);
BOOL SelectPath(LPCITEMIDLIST lpidl);
```

### <a name="parameters"></a>매개 변수

*lpszPath*<br/>
[in] 항목의 경로 지정 하는 문자열입니다.

*lpidl*<br/>
[in] 항목을 지정 하는 PIDL

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고 그렇지 않으면 E_FAIL입니다.

##  <a name="setflags"></a>  CMFCShellTreeCtrl::SetFlags

트리에서 컨텍스트를 필터링 하는 플래그를 설정 합니다.

```
void SetFlags(
    DWORD dwFlags,
    BOOL bRefresh = TRUE);
```

### <a name="parameters"></a>매개 변수

*dwFlags*<br/>
[in] 플래그 설정입니다.

*bRefresh*<br/>
[in] 지정 하는 부울 여부는 `CMFCShellTreeCtrl` 즉시 새로 고쳐져 야 합니다.

### <a name="remarks"></a>설명

합니다 `CMFCShellTreeCtrl` 플래그를 설정할 모든 패스 [IShellFolder::EnumObjects](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects)합니다. 다른 플래그의 값에 대 한 자세한 내용은 참조 [IShellFolder::EnumObjects](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects)합니다.

##  <a name="setrelatedlist"></a>  CMFCShellTreeCtrl::SetRelatedList

연결 된 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) 개체를 [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) 개체입니다.

```
void SetRelatedList(CMFCShellListCtrl* pShellList);
```

### <a name="parameters"></a>매개 변수

*pShellList*<br/>
[in] 에 대 한 포인터를 `CMFCShellListCtrl` 개체입니다.

### <a name="remarks"></a>설명

이 메서드는 `CMFCShellListCtrl` 사용 하 여는 `CMFCShellTreeCtrl`합니다. 이러한 개체는 탐색기와 유사한 창으로 표시 될 수 있습니다: 사용자의 개체를 선택 하는 경우는 `CMFCShellTreeCtrl`의 연결 된 항목에는 `CMFCShellListCtrl` 자동 업데이트 됩니다.

메서드를 사용 [CMFCShellTreeCtrl::GetRelatedList](#getrelatedlist) 검색 하는 `CMFCShellListCtrl` 연관는 `CMFCShellTreeCtrl`합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CTreeCtrl Class](../../mfc/reference/ctreectrl-class.md)<br/>
[CMFCShellListCtrl 클래스](../../mfc/reference/cmfcshelllistctrl-class.md)
