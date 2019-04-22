---
title: CShellManager 클래스
ms.date: 11/04/2016
f1_keywords:
- CShellManager
- AFXSHELLMANAGER/CShellManager
- AFXSHELLMANAGER/CShellManager::CShellManager
- AFXSHELLMANAGER/CShellManager::BrowseForFolder
- AFXSHELLMANAGER/CShellManager::ConcatenateItem
- AFXSHELLMANAGER/CShellManager::CopyItem
- AFXSHELLMANAGER/CShellManager::CreateItem
- AFXSHELLMANAGER/CShellManager::FreeItem
- AFXSHELLMANAGER/CShellManager::GetItemCount
- AFXSHELLMANAGER/CShellManager::GetItemSize
- AFXSHELLMANAGER/CShellManager::GetNextItem
- AFXSHELLMANAGER/CShellManager::GetParentItem
- AFXSHELLMANAGER/CShellManager::ItemFromPath
helpviewer_keywords:
- CShellManager [MFC], CShellManager
- CShellManager [MFC], BrowseForFolder
- CShellManager [MFC], ConcatenateItem
- CShellManager [MFC], CopyItem
- CShellManager [MFC], CreateItem
- CShellManager [MFC], FreeItem
- CShellManager [MFC], GetItemCount
- CShellManager [MFC], GetItemSize
- CShellManager [MFC], GetNextItem
- CShellManager [MFC], GetParentItem
- CShellManager [MFC], ItemFromPath
ms.assetid: f15c4c1a-6fae-487d-9913-9b7369b33da0
ms.openlocfilehash: ec2abf243e7f3865609f81fa4f3bf81e1b4c3d92
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58769988"
---
# <a name="cshellmanager-class"></a>CShellManager 클래스

PIDL(식별자 포인터 목록)에 대한 포인터를 사용하여 작업할 수 있는 몇 가지 메서드를 구현합니다.

## <a name="syntax"></a>구문

```
class CShellManager : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CShellManager::CShellManager](#cshellmanager)|`CShellManager` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CShellManager::BrowseForFolder](#browseforfolder)|사용자가 셸 폴더를 선택할 수 있는 대화 상자가 표시 됩니다.|
|[CShellManager::ConcatenateItem](#concatenateitem)|두 Pidl를 연결합니다.|
|[CShellManager::CopyItem](#copyitem)|새 PIDL 만들고 제공 된 PIDL을 복사 합니다.|
|[CShellManager::CreateItem](#createitem)|지정된 된 크기의 새 PIDL를 만듭니다.|
|[CShellManager::FreeItem](#freeitem)|제공 된 PIDL를 삭제합니다.|
|[CShellManager::GetItemCount](#getitemcount)|제공 된 PIDL의 항목 수를 반환합니다.|
|[CShellManager::GetItemSize](#getitemsize)|제공 된 PIDL의 크기를 반환합니다.|
|[CShellManager::GetNextItem](#getnextitem)|PIDL에서 다음 항목을 반환합니다.|
|[CShellManager::GetParentItem](#getparentitem)|제공 된 항목의 부모 항목을 검색합니다.|
|[CShellManager::ItemFromPath](#itemfrompath)|제공 된 경로 의해 식별 되는 항목에 대 한 PIDL를 검색 합니다.|

## <a name="remarks"></a>설명

메서드는 `CShellManager` 모든 다루는 Pidl 클래스입니다. PIDL는 셸 개체에 대 한 고유 식별자입니다.

만들어야 합니다를 `CShellManager` 수동으로 개체입니다. 응용 프로그램의 프레임 워크에서 자동으로 만들 수 됩니다. 하지만 호출 해야 [CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager) 응용 프로그램의 초기화 프로세스 동안. 응용 프로그램에 대 한 셸 관리자에 대 한 포인터를 가져오려면, 호출 [CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CShellManager](../../mfc/reference/cshellmanager-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxshellmanager.h

##  <a name="browseforfolder"></a>  CShellManager::BrowseForFolder

사용자가 셸 폴더를 선택할 수 있는 대화 상자가 표시 됩니다.

```
BOOL BrowseForFolder(
    CString& strOutFolder,
    CWnd* pWndParent = NULL,
    LPCTSTR lplszInitialFolder = NULL,
    LPCTSTR lpszTitle = NULL,
    UINT ulFlags = BIF_RETURNONLYFSDIRS,
    LPINT piFolderImage = NULL);
```

### <a name="parameters"></a>매개 변수

*strOutFolder*<br/>
[out] 메서드에서 사용 하 여 선택한 폴더의 경로를 저장 하는 문자열입니다.

*pWndParent*<br/>
[in] 부모 창에 대 한 포인터입니다.

*lplszInitialFolder*<br/>
[in] 대화 상자가 표시 되 면 기본적으로 선택 되어 있는 폴더를 포함 하는 문자열입니다.

*lpszTitle*<br/>
[in] 대화 상자의 제목입니다.

*ulFlags*<br/>
[in] 대화 상자에 대 한 옵션을 지정 하는 플래그입니다. 참조 [BROWSEINFO](/windows/desktop/api/shlobj_core/ns-shlobj_core-_browseinfoa) 자세한 설명입니다.

*piFolderImage*<br/>
[out] 메서드를 선택한 폴더의 이미지 인덱스를 기록 하는 위치는 정수 값에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

사용자는 대화 상자에서 폴더를 선택 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 메서드를 호출할 때 응용 프로그램 만들고 사용자가 폴더를 선택할 수 있는 대화 상자를 표시 합니다. 메서드는 폴더의 경로 기록 합니다는 *strOutFolder* 매개 변수입니다.

### <a name="example"></a>예제

다음 예제에 대 한 참조를 검색 하는 방법에 설명를 `CShellManager` 사용 하 여 개체를 `CWinAppEx::GetShellManager` 메서드 및 사용 방법에는 `BrowseForFolder` 메서드. 이 코드 조각은의 일부인 합니다 [탐색기 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_Explorer#6](../../mfc/reference/codesnippet/cpp/cshellmanager-class_1.cpp)]

##  <a name="concatenateitem"></a>  CShellManager::ConcatenateItem

두 Pidl 포함 된 새 목록을 만듭니다.

```
LPITEMIDLIST ConcatenateItem(
    LPCITEMIDLIST pidl1,
    LPCITEMIDLIST pidl2);
```

### <a name="parameters"></a>매개 변수

*pidl1*<br/>
[in] 첫 번째 항목입니다.

*pidl2*<br/>
[in] 두 번째 항목입니다.

### <a name="return-value"></a>반환 값

함수가 성공할 경우 새 항목 목록에 대 한 포인터를 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

이 메서드를 만듭니다 [ITEMIDLIST](/windows/desktop/api/shtypes/ns-shtypes-_itemidlist) 둘 다를 포함할 만큼 충분히 큰지 *pidl1* 하 고 *pidl2*합니다. 그런 다음 복사 *pidl1* 하 고 *pidl2* 새 목록에 있습니다.

##  <a name="copyitem"></a>  CShellManager::CopyItem

항목 목록에 복사합니다.

```
LPITEMIDLIST CopyItem(LPCITEMIDLIST pidlSource);
```

### <a name="parameters"></a>매개 변수

*pidlSource*<br/>
[in] 원래 항목 목록입니다.

### <a name="return-value"></a>반환 값

성공할 경우 새로 만든된 항목 목록에 대 한 포인터 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

새로 만든된 항목 목록에는 소스 항목 목록 동일한 크기에 있습니다.

##  <a name="createitem"></a>  CShellManager::CreateItem

새 PIDL를 만듭니다.

```
LPITEMIDLIST CreateItem(UINT cbSize);
```

### <a name="parameters"></a>매개 변수

*cbSize*<br/>
[in] 항목 목록의 크기입니다.

### <a name="return-value"></a>반환 값

성공할 경우 만든된 항목 목록에 대 한 포인터 그렇지 않으면 NULL입니다.

##  <a name="cshellmanager"></a>  CShellManager::CShellManager

`CShellManager` 개체를 생성합니다.

```
CShellManager();
```

### <a name="remarks"></a>설명

대부분의 경우에서 필요가 없습니다 만들려면는 `CShellManager` 직접. 기본적으로 프레임 워크를 만듭니다. 에 대 한 포인터를 가져오려고 합니다 `CShellManager`, 호출 [CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager)합니다. 만드는 경우는 `CShellManager` 수동으로 메서드를 사용 하 여 초기화 해야 합니다 [CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager)합니다.

##  <a name="freeitem"></a>  CShellManager::FreeItem

항목 목록을 삭제합니다.

```
void FreeItem(LPITEMIDLIST pidl);
```

### <a name="parameters"></a>매개 변수

*pidl*<br/>
[in] 삭제 하는 항목 목록입니다.

##  <a name="getitemcount"></a>  CShellManager::GetItemCount

항목 목록의 항목 개수를 반환합니다.

```
UINT GetItemCount(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>매개 변수

*pidl*<br/>
[in] 항목 목록에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

항목 목록의 항목 개수입니다.

##  <a name="getitemsize"></a>  CShellManager::GetItemSize

항목 목록의 크기를 반환합니다.

```
UINT GetItemSize(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>매개 변수

*pidl*<br/>
[in] 항목 목록에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

항목 목록의 크기입니다.

##  <a name="getnextitem"></a>  CShellManager::GetNextItem

항목 식별자 목록 (PIDL)에 대 한 포인터에서 다음 항목을 검색합니다.

```
LPITEMIDLIST GetNextItem(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>매개 변수

*pidl*<br/>
[in] 목록 반복 하는 항목입니다.

### <a name="return-value"></a>반환 값

목록에서 다음 항목에 대 한 포인터입니다.

### <a name="remarks"></a>설명

목록에 더 이상 항목이 없으면이 메서드는 NULL을 반환 합니다.

##  <a name="getparentitem"></a>  CShellManager::GetParentItem

항목 식별자 목록 (PIDL)에 대 한 포인터의 부모를 검색 합니다.

```
int GetParentItem(
    LPCITEMIDLIST lpidl,
    LPITEMIDLIST& lpidlParent);
```

### <a name="parameters"></a>매개 변수

*lpidl*<br/>
[in] PIDL 부모가 검색 됩니다.

*lpidlParent*<br/>
[out] 메서드는 결과 저장 하는 위치를 PIDL 참조입니다.

### <a name="return-value"></a>반환 값

PIDL 부모 수준입니다.

### <a name="remarks"></a>설명

PIDL 수준을 바탕 화면에 상대적입니다. 데스크톱 PIDL 수준이 0으로 간주 됩니다.

##  <a name="itemfrompath"></a>  CShellManager::ItemFromPath

문자열 경로 식별 되는 항목에서 항목 식별자 목록 (PIDL)에 대 한 포인터를 검색 합니다.

```
HRESULT ItemFromPath(
    LPCTSTR lpszPath,
    LPITEMIDLIST& pidl);
```

### <a name="parameters"></a>매개 변수

*lpszPath*<br/>
[in] 항목에 대 한 경로 지정 하는 문자열입니다.

*pidl*<br/>
[out] PIDL 참조입니다. 메서드 반환 값에 대 한 포인터를 저장 하려면이 PIDL를 사용 합니다.

### <a name="return-value"></a>반환 값

성공할 경우 NOERROR 반환 OLE 정의 오류 값입니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)
