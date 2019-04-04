---
title: CMFCShellListCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCShellListCtrl
- AFXSHELLLISTCTRL/CMFCShellListCtrl
- AFXSHELLLISTCTRL/CMFCShellListCtrl::DisplayFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::DisplayParentFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::EnableShellContextMenu
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentFolderName
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentItemIdList
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentShellFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetItemPath
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetItemTypes
- AFXSHELLLISTCTRL/CMFCShellListCtrl::IsDesktop
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnCompareItems
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnFormatFileDate
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnFormatFileSize
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnGetItemIcon
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnGetItemText
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnSetColumns
- AFXSHELLLISTCTRL/CMFCShellListCtrl::Refresh
- AFXSHELLLISTCTRL/CMFCShellListCtrl::SetItemTypes
helpviewer_keywords:
- CMFCShellListCtrl [MFC], DisplayFolder
- CMFCShellListCtrl [MFC], DisplayParentFolder
- CMFCShellListCtrl [MFC], EnableShellContextMenu
- CMFCShellListCtrl [MFC], GetCurrentFolder
- CMFCShellListCtrl [MFC], GetCurrentFolderName
- CMFCShellListCtrl [MFC], GetCurrentItemIdList
- CMFCShellListCtrl [MFC], GetCurrentShellFolder
- CMFCShellListCtrl [MFC], GetItemPath
- CMFCShellListCtrl [MFC], GetItemTypes
- CMFCShellListCtrl [MFC], IsDesktop
- CMFCShellListCtrl [MFC], OnCompareItems
- CMFCShellListCtrl [MFC], OnFormatFileDate
- CMFCShellListCtrl [MFC], OnFormatFileSize
- CMFCShellListCtrl [MFC], OnGetItemIcon
- CMFCShellListCtrl [MFC], OnGetItemText
- CMFCShellListCtrl [MFC], OnSetColumns
- CMFCShellListCtrl [MFC], Refresh
- CMFCShellListCtrl [MFC], SetItemTypes
ms.assetid: ad472958-5586-4c50-aadf-1844c30bf6e7
ms.openlocfilehash: a513a5e85ae5cf00f7ea874967a709245e016b34
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58772113"
---
# <a name="cmfcshelllistctrl-class"></a>CMFCShellListCtrl 클래스

`CMFCShellListCtrl` 클래스 Windows 목록 컨트롤 기능을 제공 하 고 셸 항목의 목록을 표시 하는 기능을 포함 하 여 확장 합니다.

## <a name="syntax"></a>구문

```
class CMFCShellListCtrl : public CMFCListCtrl
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCShellListCtrl::DisplayFolder](#displayfolder)|제공 된 폴더에 포함 된 항목의 목록을 표시 합니다.|
|[CMFCShellListCtrl::DisplayParentFolder](#displayparentfolder)|현재 표시 된 폴더의 부모 폴더에 포함 된 항목의 목록을 표시 합니다.|
|[CMFCShellListCtrl::EnableShellContextMenu](#enableshellcontextmenu)|사용 하거나 바로 가기 메뉴를 사용 하지 않도록 설정 합니다.|
|[CMFCShellListCtrl::GetCurrentFolder](#getcurrentfolder)|현재 폴더의 경로 검색합니다.|
|[CMFCShellListCtrl::GetCurrentFolderName](#getcurrentfoldername)|현재 폴더의 이름을 검색합니다.|
|[CMFCShellListCtrl::GetCurrentItemIdList](#getcurrentitemidlist)|현재 목록 컨트롤 항목의 PIDL를 반환합니다.|
|[CMFCShellListCtrl::GetCurrentShellFolder](#getcurrentshellfolder)|현재 셸 폴더에 대 한 포인터를 반환합니다.|
|[CMFCShellListCtrl::GetItemPath](#getitempath)|항목의 텍스트 경로 반환 합니다.|
|[CMFCShellListCtrl::GetItemTypes](#getitemtypes)|목록 컨트롤에 표시 되는 셸 항목 형식을 반환 합니다.|
|[CMFCShellListCtrl::IsDesktop](#isdesktop)|현재 선택한 폴더 바탕 화면 폴더 인지 확인 합니다.|
|[CMFCShellListCtrl::OnCompareItems](#oncompareitems)|두 항목을 비교 하는 경우이 메서드를 호출 하는 프레임 워크입니다. (재정의 [CMFCListCtrl::OnCompareItems](../../mfc/reference/cmfclistctrl-class.md#oncompareitems).)|
|[CMFCShellListCtrl::OnFormatFileDate](#onformatfiledate)|프레임 워크 목록 컨트롤에서 표시 되는 파일 날짜를 검색 하는 경우 호출 됩니다.|
|[CMFCShellListCtrl::OnFormatFileSize](#onformatfilesize)|프레임 워크 목록 컨트롤의 파일 크기를 변환 하는 경우 호출 됩니다.|
|[CMFCShellListCtrl::OnGetItemIcon](#ongetitemicon)|프레임 워크 목록 컨트롤 항목의 아이콘을 검색 하는 경우 호출 됩니다.|
|[CMFCShellListCtrl::OnGetItemText](#ongetitemtext)|프레임 워크 목록 컨트롤 항목의 텍스트를 변환 하는 경우 호출 됩니다.|
|[CMFCShellListCtrl::OnSetColumns](#onsetcolumns)|열의 이름을 설정 하는 경우 프레임 워크에서 호출 됩니다.|
|[CMFCShellListCtrl::Refresh](#refresh)|새로 고침 및 목록 컨트롤을 다시 그립니다.|
|[CMFCShellListCtrl::SetItemTypes](#setitemtypes)|목록 컨트롤에서 표시 되는 항목의 유형을 설정 합니다.|

## <a name="remarks"></a>설명

합니다 `CMFCShellListCtrl` 클래스의 기능을 확장 합니다 [CMFCListCtrl 클래스](../../mfc/reference/cmfclistctrl-class.md) Windows 셸 항목을 나열 하려면 프로그램을 사용 하 여 합니다. 탐색기 창에 대 한 목록 보기의 표시 형식을 사용 하는 경우

A [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) 개체와 연결 될 수는 `CMFCShellListCtrl` 전체 탐색기 창을 만드는 개체입니다. 그런 다음에서 항목을 선택 합니다 `CMFCShellTreeCtrl` 하면는 `CMFCShellListCtrl` 선택한 항목의 콘텐츠를 나열 하는 개체입니다.

## <a name="example"></a>예제

다음 예제에서는 개체를 만드는 방법의 `CMFCShellListCtrl` 클래스 및 현재 표시 된 폴더의 상위 폴더를 표시 하는 방법입니다. 이 코드 조각은의 일부인 합니다 [탐색기 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_Explorer#1](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_1.h)]
[!code-cpp[NVC_MFC_Explorer#2](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_2.cpp)]
[!code-cpp[NVC_MFC_Explorer#3](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_3.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListCtrl](../../mfc/reference/clistctrl-class.md)

[CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)

`CMFCShellListCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxshelllistCtrl.h

##  <a name="displayfolder"></a>  CMFCShellListCtrl::DisplayFolder

제공 된 폴더에 포함 된 항목의 목록을 표시 합니다.

```
virtual HRESULT DisplayFolder(LPCTSTR lpszPath);
virtual HRESULT DisplayFolder(LPAFX_SHELLITEMINFO lpItemInfo);
```

### <a name="parameters"></a>매개 변수

*lpszPath*<br/>
[in] 폴더의 경로 포함 하는 문자열입니다.

*lpItemInfo*<br/>
[in] 에 대 한 포인터를 `LPAFX_SHELLITEMINFO` 표시할 폴더를 설명 하는 구조입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고 그렇지 않으면 E_FAIL입니다.

##  <a name="displayparentfolder"></a>  CMFCShellListCtrl::DisplayParentFolder

업데이트를 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) 현재 표시 된 폴더의 상위 폴더를 표시 하는 개체입니다.

```
virtual HRESULT DisplayParentFolder();
```

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고 그렇지 않으면 E_FAIL입니다.

##  <a name="enableshellcontextmenu"></a>  CMFCShellListCtrl::EnableShellContextMenu

바로 가기 메뉴를 사용 하도록 설정 합니다.

```
void EnableShellContextMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
[in] 프레임 워크 바로 가기 메뉴를 활성화 하는지 여부를 지정 하는 부울입니다.

##  <a name="getcurrentfolder"></a>  CMFCShellListCtrl::GetCurrentFolder

현재 선택한 폴더의 경로 검색 합니다 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) 개체입니다.

```
BOOL GetCurrentFolder(CString& strPath) const;
```

### <a name="parameters"></a>매개 변수

*strPath*<br/>
[out] 메서드는 경로 기록 하는 위치 문자열 매개 변수 참조입니다.

### <a name="return-value"></a>반환 값

성공하는 경우 0이 아닌 값입니다. 그렇지 않은 경우 0입니다.

### <a name="remarks"></a>설명

선택한 폴더가 있는 경우이 메서드는 `CMFCShellListCtrl`합니다.

##  <a name="getcurrentfoldername"></a>  CMFCShellListCtrl::GetCurrentFolderName

현재 선택한 폴더의 이름을 검색 합니다 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) 개체입니다.

```
BOOL GetCurrentFolderName(CString& strName) const;
```

### <a name="parameters"></a>매개 변수

*strName*<br/>
[out] 문자열 매개 변수는 메서드 이름을 기록 하는 위치에 대 한 참조입니다.

### <a name="return-value"></a>반환 값

성공하는 경우 0이 아닌 값입니다. 그렇지 않은 경우 0입니다.

### <a name="remarks"></a>설명

선택한 폴더가 있는 경우이 메서드는 `CMFCShellListCtrl`합니다.

##  <a name="getcurrentitemidlist"></a>  CMFCShellListCtrl::GetCurrentItemIdList

현재 선택한 항목의 PIDL를 반환합니다.

```
LPITEMIDLIST GetCurrentItemIdList() const;
```

### <a name="return-value"></a>반환 값

현재 항목의 PIDL 합니다.

##  <a name="getcurrentshellfolder"></a>  CMFCShellListCtrl::GetCurrentShellFolder

현재 선택한 항목에 대 한 포인터를 가져옵니다 합니다 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) 개체입니다.

```
const IShellFolder* GetCurrentShellFolder() const;
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [IShellFolder 인터페이스](/windows/desktop/api/shobjidl_core/nn-shobjidl_core-ishellfolder) 선택한 개체에 대 한 합니다.

### <a name="remarks"></a>설명

이 메서드는 개체가 없습니다. 현재 선택 되어 있으면 NULL을 반환 합니다.

##  <a name="getitempath"></a>  CMFCShellListCtrl::GetItemPath

항목에 대 한 경로 검색합니다.

```
BOOL GetItemPath(
    CString& strPath,
    int iItem) const;
```

### <a name="parameters"></a>매개 변수

*strPath*<br/>
[out] 경로 수신 하는 문자열에 대 한 참조입니다.

*iItem*<br/>
[in] 목록 항목의 인덱스입니다.

### <a name="return-value"></a>반환 값

성공하면 TRUE이고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

제공한 인덱스 *iItem* 하 여 현재 표시 된 항목을 기반으로 합니다 [CMFCShellListCtrl 클래스](../../mfc/reference/cmfcshelllistctrl-class.md) 개체입니다.

##  <a name="getitemtypes"></a>  CMFCShellListCtrl::GetItemTypes

표시 되는 항목의 형식을 반환 합니다 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) 개체입니다.

```
SHCONTF GetItemTypes() const;
```

### <a name="return-value"></a>반환 값

A [SHCONTF](/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_shcontf) 에 나열 된 항목의 형식을 포함 하는 값은 `CMFCShellListCtrl`합니다.

### <a name="remarks"></a>설명

에 나열 된 항목의 유형을 설정 하는 `CMFCShellListCtrl`, 호출 [CMFCShellListCtrl::SetItemTypes](#setitemtypes)합니다.

##  <a name="isdesktop"></a>  CMFCShellListCtrl::IsDesktop

결정 되는 폴더에 표시 합니다 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) 개체가 바탕 화면 폴더입니다.

```
BOOL IsDesktop() const;
```

### <a name="return-value"></a>반환 값

표시 폴더는 데스크톱 폴더에 있으면 TRUE FALSE이 고, 그렇지 합니다.

##  <a name="oncompareitems"></a>  CMFCShellListCtrl::OnCompareItems

더 자세한 내용은 Visual Studio 설치의 **VC\\atlmfc\\src\\mfc** 폴더에 있는 소스 코드를 참조하세요.

```
virtual int OnCompareItems(
    LPARAM lParam1,
    LPARAM lParam2,
    int iColumn);
```

### <a name="parameters"></a>매개 변수

[in] *lParam1*<br/>
[in] *lParam2*<br/>
[in] *iColumn*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="onformatfiledate"></a>  CMFCShellListCtrl::OnFormatFileDate

프레임 워크는 개체에 연결 된 문자열로 날짜를 변환 해야 하는 경우이 메서드를 호출 합니다.

```
virtual void OnFormatFileDate(
    const CTime& tmFile,
    CString& str);
```

### <a name="parameters"></a>매개 변수

*tmFile*<br/>
[in] 파일과 연결 된 날짜입니다.

*str*<br/>
[out] 서식이 지정 된 파일 날짜를 포함 하는 문자열입니다.

### <a name="remarks"></a>설명

경우는 [CMFCShellListCtrl 클래스](../../mfc/reference/cmfcshelllistctrl-class.md) 파일과 연결 된 날짜를 표시 하는 개체, 해당 날짜를 문자열 형식으로 변환 해야 합니다. `CMFCShellListCtrl` 이 메서드를 사용 하 여 해당 변환을 수행 합니다. 기본적으로이 메서드는 날짜 문자열로 서식을 지정 하려면 현재 로캘을 사용 합니다.

##  <a name="onformatfilesize"></a>  CMFCShellListCtrl::OnFormatFileSize

프레임 워크는 개체의 크기를 문자열로 변환할 때이 메서드를 호출 합니다.

```
virtual void OnFormatFileSize(
    long lFileSize,
    CString& str);
```

### <a name="parameters"></a>매개 변수

*lFileSize*<br/>
[in] 프레임 워크를 표시 하는 파일의 크기입니다.

*str*<br/>
[out] 서식이 지정 된 파일 크기를 포함 하는 문자열입니다.

### <a name="remarks"></a>설명

경우는 [CMFCShellListCtrl 클래스](../../mfc/reference/cmfcshelllistctrl-class.md) 개체 파일의 크기를 표시 해야 하는 경우, 파일 크기를 문자열 형식으로 변환 해야 합니다. `CMFCShellListCtrl` 이 메서드를 사용 하 여 해당 변환을 수행 합니다. 기본적으로이 메서드 파일 크기를 킬로바이트 바이트에서 변환 하 고 현재 로캘을 사용 하 여 문자열로 크기를 지정 합니다.

##  <a name="ongetitemicon"></a>  CMFCShellListCtrl::OnGetItemIcon

프레임 워크가 셸 목록 항목과 연결 된 아이콘을 검색 하려면이 메서드를 호출 합니다.

```
virtual int OnGetItemIcon(
    int iItem,
    LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>매개 변수

*iItem*<br/>
[in] 항목 인덱스입니다.

*pItem*<br/>
[in] 항목을 설명 하는 LPAFX_SHELLITEMINFO 매개 변수입니다.

### <a name="return-value"></a>반환 값

성공할 경우 아이콘 이미지의 인덱스 함수가 실패 한 경우-1입니다.

### <a name="remarks"></a>설명

아이콘 이미지 인덱스 시스템 이미지 목록을 기반으로 합니다.

기본적으로이 방법은에 의존 합니다 *pItem* 매개 변수입니다. 변수의 *iItem* 기본 구현에서 사용 되지 않습니다. 사용할 수 있습니다 *iItem* 사용자 지정 동작을 구현 합니다.

##  <a name="ongetitemtext"></a>  CMFCShellListCtrl::OnGetItemText

셸 항목의 텍스트를 검색 해야 하는 경우이 메서드를 호출 하는 프레임 워크입니다.

```
virtual CString OnGetItemText(
    int iItem,
    int iColumn,
    LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>매개 변수

*iItem*<br/>
[in] 항목 인덱스입니다.

*iColumn*<br/>
[in] 관련 열입니다.

*pItem*<br/>
[in] 항목을 설명 하는 LPAFX_SHELLITEMINFO 매개 변수입니다.

### <a name="return-value"></a>반환 값

`CString` 항목과 연결 된 텍스트를 포함 하는 합니다.

### <a name="remarks"></a>설명

각 항목에는 `CMFCShellListCtrl` 개체 하나 이상의 열에 텍스트를 있을 수 있습니다. 프레임 워크에서이 메서드를 호출 하면 관심 있는 열을 지정 합니다. 이 함수를 수동으로 호출 하는 경우에 관심 있는 열을 지정 해야 합니다.

기본적으로이 방법은에 의존 합니다 *pItem* 매개 변수를 프로세스에는 항목을 확인 합니다. 변수의 *iItem* 기본 구현에서 사용 되지 않습니다.

##  <a name="onsetcolumns"></a>  CMFCShellListCtrl::OnSetColumns

프레임 워크는 열의 이름을 설정 하는 경우이 메서드를 호출 합니다.

```
virtual void OnSetColumns();
```

### <a name="remarks"></a>설명

기본적으로 프레임 워크에서 네 개의 열을 만듭니다는 `CMFCShellListCtrl` 개체입니다. 이러한 열 이름은 **이름을**, **크기**, **형식**, 및 **Modified**합니다. 열 및 해당 이름의 수를 사용자 지정 하려면이 메서드를 재정의할 수 있습니다.

##  <a name="refresh"></a>  CMFCShellListCtrl::Refresh

새로 고쳐지고 다시 표시 합니다 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) 개체입니다.

```
virtual HRESULT Refresh();
```

### <a name="return-value"></a>반환 값

`S_OK` 성공할 경우 그렇지 않으면 오류 값입니다.

### <a name="remarks"></a>설명

표시 되는 항목 목록을 새로 고치려면이 메서드를 호출 합니다 `CMFCShellListCtrl` 개체입니다.

##  <a name="setitemtypes"></a>  CMFCShellListCtrl::SetItemTypes

에 나열 된 항목의 형식을 가져오거나 설정 합니다 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) 개체입니다.

```
void SetItemTypes(SHCONTF nTypes);
```

### <a name="parameters"></a>매개 변수

*nTypes*<br/>
[in] 목록 항목의 형식에 `CMFCShellListCtrl` 개체 지원 합니다.

### <a name="remarks"></a>설명

항목 형식 목록에 대 한 자세한 내용은 참조 [SHCONTF](/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_shcontf)합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCListCtrl 클래스](../../mfc/reference/cmfclistctrl-class.md)<br/>
[CMFCShellTreeCtrl 클래스](../../mfc/reference/cmfcshelltreectrl-class.md)
