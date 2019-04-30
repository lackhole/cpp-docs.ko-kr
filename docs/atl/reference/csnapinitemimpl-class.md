---
title: CSnapInItemImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- CSnapInItemImpl
- ATLSNAP/ATL::CSnapInItemImpl
- ATLSNAP/ATL::CSnapInItemImpl::CSnapInItemImpl
- ATLSNAP/ATL::CSnapInItemImpl::AddMenuItems
- ATLSNAP/ATL::CSnapInItemImpl::Command
- ATLSNAP/ATL::CSnapInItemImpl::CreatePropertyPages
- ATLSNAP/ATL::CSnapInItemImpl::FillData
- ATLSNAP/ATL::CSnapInItemImpl::GetResultPaneInfo
- ATLSNAP/ATL::CSnapInItemImpl::GetResultViewType
- ATLSNAP/ATL::CSnapInItemImpl::GetScopePaneInfo
- ATLSNAP/ATL::CSnapInItemImpl::Notify
- ATLSNAP/ATL::CSnapInItemImpl::QueryPagesFor
- ATLSNAP/ATL::CSnapInItemImpl::SetMenuInsertionFlags
- ATLSNAP/ATL::CSnapInItemImpl::SetToolbarButtonInfo
- ATLSNAP/ATL::CSnapInItemImpl::UpdateMenuState
- ATLSNAP/ATL::CSnapInItemImpl::UpdateToolbarButton
- ATLSNAP/ATL::CSnapInItemImpl::m_bstrDisplayName
- ATLSNAP/ATL::CSnapInItemImpl::m_resultDataItem
- ATLSNAP/ATL::CSnapInItemImpl::m_scopeDataItem
helpviewer_keywords:
- snap-ins, data items
- snap-ins, ATL support for
- CSnapInItemImpl class
- snap-ins
ms.assetid: 52caefbd-9eae-49b0-add2-d55524271aa7
ms.openlocfilehash: 27f3e8a17a9538a72a6592177a88a9b415b1a27c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62277710"
---
# <a name="csnapinitemimpl-class"></a>CSnapInItemImpl 클래스

이 클래스는 스냅인 노드 개체를 구현 하기 위한 메서드를 제공 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class T, BOOL bIsExtension = FALSE>
class ATL_NO_VTABLE CSnapInItemImpl : public CSnapInItem
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `CSnapInItemImpl`합니다.

*bIsExtension*<br/>
TRUE 이면 개체는 스냅인 확장; 그렇지 않으면 FALSE입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CSnapInItemImpl::CSnapInItemImpl](#csnapinitemimpl)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CSnapInItemImpl::AddMenuItems](#addmenuitems)|상황에 맞는 메뉴에 메뉴 항목을 추가합니다.|
|[CSnapInItemImpl::Command](#command)|사용자 지정 메뉴 항목이 선택 될 때 콘솔에서 호출 됩니다.|
|[CSnapInItemImpl::CreatePropertyPages](#createpropertypages)|스냅인의 속성 시트에 페이지를 추가합니다.|
|[CSnapInItemImpl::FillData](#filldata)|스냅인 개체에서 지정 된 스트림으로 정보를 복사본입니다.|
|[CSnapInItemImpl::GetResultPaneInfo](#getresultpaneinfo)|검색 된 `RESULTDATAITEM` 스냅인의 구조입니다.|
|[CSnapInItemImpl::GetResultViewType](#getresultviewtype)|결과 창에서 사용 되는 보기의 유형을 결정 합니다.|
|[CSnapInItemImpl::GetScopePaneInfo](#getscopepaneinfo)|검색 된 `SCOPEDATAITEM` 스냅인의 구조입니다.|
|[CSnapInItemImpl::Notify](#notify)|사용자가 수행한 작업의 스냅인에 알리기 위해 콘솔에서 호출 됩니다.|
|[CSnapInItemImpl::QueryPagesFor](#querypagesfor)|스냅인에서 노드 속성 페이지 지원 하기 위해 호출 됩니다.|
|[CSnapInItemImpl::SetMenuInsertionFlags](#setmenuinsertionflags)|스냅인 개체 메뉴 삽입 플래그를 수정합니다.|
|[CSnapInItemImpl::SetToolbarButtonInfo](#settoolbarbuttoninfo)|지정 된 도구 모음 단추 정보를 설정합니다.|
|[CSnapInItemImpl::UpdateMenuState](#updatemenustate)|상황에 맞는 메뉴 항목의 상태를 업데이트합니다.|
|[CSnapInItemImpl::UpdateToolbarButton](#updatetoolbarbutton)|지정 된 도구 모음 단추의 상태를 업데이트합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CSnapInItemImpl::m_bstrDisplayName](#m_bstrdisplayname)|스냅인 개체의 이름입니다.|
|[CSnapInItemImpl::m_resultDataItem](#m_resultdataitem)|Windows `RESULTDATAITEM` 사용 되는 구조는 `CSnapInItemImpl` 개체입니다.|
|[CSnapInItemImpl::m_scopeDataItem](#m_scopedataitem)|Windows `SCOPEDATAITEM` 사용 되는 구조는 `CSnapInItemImpl` 개체입니다.|

## <a name="remarks"></a>설명

`CSnapInItemImpl` 메뉴 항목 및 도구 모음을 추가 하 고 적절 한 처리기 함수에 스냅인에서 노드에 대 한 명령을 전달 등 스냅인 노드 개체에 대 한 기본 구현을 제공 합니다. 이러한 기능 몇 가지 다른 인터페이스를 사용 하 여 구현 됩니다 및 형식을 매핑합니다. 파생된 클래스의 올바른 인스턴스를 확인 하 고 다음 올바른 인스턴스로 메시지를 전달 하 여 노드 개체를 전송 하는 알림을 처리 하는 기본 구현 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CSnapInItem`

`CSnapInItemImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlsnap.h

##  <a name="addmenuitems"></a>  CSnapInItemImpl::AddMenuItems

이 메서드 구현 Win32 함수 [IExtendContextMenu::AddMenuItems](/windows/desktop/api/mmc/nf-mmc-iextendcontextmenu-addmenuitems)합니다.

```
AddMenuItems(
    LPCONTEXTMENUCALLBACK piCallback,
    long* pInsertionAllowed,
    DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>매개 변수

*piCallback*<br/>
[in] 에 대 한 포인터를 `IContextMenuCallback` 상황에 맞는 메뉴에 항목을 추가할 수는 있습니다.

*pInsertionAllowed*<br/>
[out에서] 식별 Microsoft 관리 콘솔 MMC 정의 메뉴 항목 삽입 지점을 사용할 수 있는 합니다. 다음 플래그의 조합일 수 있습니다.

- 상황에 맞는 메뉴의 맨 위에 있는 CCM_INSERTIONALLOWED_TOP 항목을 삽입할 수 있습니다.

- 새로 만들기 메뉴에서 CCM_INSERTIONALLOWED_NEW 항목을 삽입할 수 있습니다.

- 작업 하위 메뉴에 CCM_INSERTIONALLOWED_TASK 항목을 삽입할 수 있습니다.

- 결과 창 상황에 맞는 메뉴 보기 하위 메뉴 또는 도구 모음 보기 메뉴에서 CCM_INSERTIONALLOWED_VIEW 항목을 삽입할 수 있습니다.

*type*<br/>
[in] 개체의 형식을 지정합니다. 다음 값 중 하나일 수 있습니다.

- 범위 창 컨텍스트에 대해 CCT_SCOPE 데이터 개체입니다.

- 결과 창 컨텍스트에 대해 CCT_RESULT 데이터 개체입니다.

- 스냅인 관리자 컨텍스트에 대 한 CCT_SNAPIN_MANAGER 데이터 개체입니다.

- CCT_UNINITIALIZED 데이터 개체 유형이 잘못 되었습니다.

##  <a name="command"></a>  CSnapInItemImpl::Command

이 메서드 구현 Win32 함수 [IExtendContextMenu::Command](/windows/desktop/api/mmc/nf-mmc-iextendcontextmenu-command)합니다.

```
Command(long lCommandID, DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>매개 변수

*lCommandID*<br/>
[in] 메뉴 항목의 명령 식별자를 지정합니다.

*type*<br/>
[in] 개체의 형식을 지정합니다. 다음 값 중 하나일 수 있습니다.

- 범위 창 컨텍스트에 대해 CCT_SCOPE 데이터 개체입니다.

- 결과 창 컨텍스트에 대해 CCT_RESULT 데이터 개체입니다.

- 스냅인 관리자 컨텍스트에 대 한 CCT_SNAPIN_MANAGER 데이터 개체입니다.

- CCT_UNINITIALIZED 데이터 개체 유형이 잘못 되었습니다.

##  <a name="createpropertypages"></a>  CSnapInItemImpl::CreatePropertyPages

이 메서드 구현 Win32 함수 [IExtendPropertySheet::CreatePropertyPages](/windows/desktop/api/mmc/nn-mmc-iextendpropertysheet2)합니다.

```
CreatePropertyPages(
    LPPROPERTYSHEETCALLBACK lpProvider,
    long handle,
    IUnknown* pUnk,
    DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>매개 변수

*lpProvider*<br/>
[in] 에 대 한 포인터를 `IPropertySheetCallback` 인터페이스입니다.

*handle*<br/>
[in] 적절 한 데이터 클래스에 MMCN_PROPERTY_CHANGE 알림 메시지를 라우팅하는 데 핸들을 지정 합니다.

*pUnk*<br/>
[in] 에 대 한 포인터를 `IExtendPropertySheet` 노드에 대 한 컨텍스트 정보를 포함 하는 개체의 인터페이스입니다.

*type*<br/>
[in] 개체의 형식을 지정합니다. 다음 값 중 하나일 수 있습니다.

- 범위 창 컨텍스트에 대해 CCT_SCOPE 데이터 개체입니다.

- 결과 창 컨텍스트에 대해 CCT_RESULT 데이터 개체입니다.

- 스냅인 관리자 컨텍스트에 대 한 CCT_SNAPIN_MANAGER 데이터 개체입니다.

- CCT_UNINITIALIZED 데이터 개체 유형이 잘못 되었습니다.

##  <a name="csnapinitemimpl"></a>  CSnapInItemImpl::CSnapInItemImpl

`CSnapInItemImpl` 개체를 생성합니다.

```
CSnapInItemImpl();
```

##  <a name="filldata"></a>  CSnapInItemImpl::FillData

이 함수는 항목에 대 한 정보를 검색 하 라고 합니다.

```
FillData(CLIPFORMAT cf, LPSTREAM pStream);
```

### <a name="parameters"></a>매개 변수

*cf*<br/>
[in] 형식 (텍스트, 서식 있는 텍스트 또는 OLE 항목을 사용 하 여 서식 있는 텍스트) 클립보드의입니다.

*pStream*<br/>
[in] 개체 데이터를 포함 하는 스트림 포인터입니다.

### <a name="remarks"></a>설명

이 함수를 제대로 구현 하려면 올바른 정보를 스트림으로 복사 합니다 (*pStream*)에 지정 된 클립보드 형식에 따라 *cf*합니다.

##  <a name="getresultviewtype"></a>  CSnapInItemImpl::GetResultViewType

스냅인 개체의 결과 창에 대 한 보기의 유형을 검색 하려면이 함수를 호출 합니다.

```
GetResultViewType(
    LPOLESTR* ppViewType,
    long* pViewOptions);
```

### <a name="parameters"></a>매개 변수

*ppViewType*<br/>
[out] 반환 된 뷰 유형의 주소에 대 한 포인터입니다.

*pViewOptions*<br/>
[out] 소유 스냅인에서 지정 된 옵션을 사용 하 여 콘솔을 제공 하는 MMC_VIEW_OPTIONS 열거형에 대 한 포인터입니다. 이 값 중 하나일 수 있습니다.

- MMC_VIEW_OPTIONS_NOLISTVIEWS = 0x00000001 콘솔에서 표준 목록 보기 옵션을 제공 하지 않는 것을 지시 합니다 **보기** 메뉴. 스냅인만 결과 뷰 창에서에서 자체 사용자 지정 보기를 표시할 수 있습니다. 이 이번에 정의 된 유일한 옵션 플래그입니다.

- MMC_VIEW_OPTIONS_NONE = 0 허용 기본 보기 옵션입니다.

##  <a name="getscopepaneinfo"></a>  CSnapInItemImpl::GetScopePaneInfo

검색 하려면이 함수를 호출 합니다 `SCOPEDATAITEM` 스냅인의 구조입니다.

```
GetScopePaneInfo (SCOPEDATAITEM* pScopeDataItem);
```

### <a name="parameters"></a>매개 변수

*pScopeDataItem*<br/>
[out] 에 대 한 포인터를 `SCOPEDATAITEM` 구조는 `CSnapInItemImpl` 개체입니다.

##  <a name="getresultpaneinfo"></a>  CSnapInItemImpl::GetResultPaneInfo

검색 하려면이 함수를 호출 합니다 `RESULTDATAITEM` 스냅인의 구조입니다.

```
GetResultPaneInfo (RESULTDATAITEM* pResultDataItem);
```

### <a name="parameters"></a>매개 변수

*pResultDataItem*<br/>
[out] 에 대 한 포인터를 `RESULTDATAITEM` 구조는 `CSnapInItemImpl` 개체입니다.

##  <a name="m_bstrdisplayname"></a>  CSnapInItemImpl::m_bstrDisplayName

노드 항목에 대 한 표시 문자열을 포함 합니다.

```
CComBSTR m_bstrDisplayName;
```

##  <a name="m_scopedataitem"></a>  CSnapInItemImpl::m_scopeDataItem

`SCOPEDATAITEM` 스냅인 데이터 개체의 구조가 있습니다.

```
SCOPEDATAITEM m_scopeDataItem;
```

##  <a name="m_resultdataitem"></a>  CSnapInItemImpl::m_resultDataItem

합니다 [RESULTDATAITEM](/windows/desktop/api/mmc/ns-mmc-resultdataitem) 스냅인 데이터 개체의 구조가 있습니다.

```
RESULTDATAITEM m_resultDataItem;
```

##  <a name="notify"></a>  CSnapInItemImpl::Notify

스냅인 개체는 사용자가 취해야 하는 경우 호출 됩니다.

```
STDMETHOD(Notify)(
    MMC_NOTIFY_TYPE event,
    long arg,
    long param,
    IComponentData* pComponentData,
    IComponent* pComponent,
    DATA_OBJECT_TYPES type) = 0;
```

### <a name="parameters"></a>매개 변수

*event*<br/>
[in] 사용자가 수행한 작업을 식별 합니다. 다음과 같은 알림이 나타날 수 있습니다.

- MMCN_ACTIVATE 전송 창이 될 때 활성화 및 비활성화 합니다.

- 결과 창에 이미지를 추가할 MMCN_ADD_IMAGES 전송 합니다.

- MMCN_BTN_CLICK 사용자가 도구 모음 단추 중 하나를 클릭할 때 보냅니다.

- MMCN_CLICK 목록 보기 항목에는 마우스 단추를 클릭할 때 보냅니다.

- MMCN_DBLCLICK 목록 보기 항목의 마우스 단추를 두 번 클릭할 때 보냅니다.

- 개체를 해야 하는 스냅인에 알림을 보내야 MMCN_DELETE 전송 삭제 합니다.

- MMCN_EXPAND 폴더 수 해야 하는 경우에 전송 합니다.

- MMCN_MINIMIZED 전송 창이 최소화 또는 최대화 합니다.

- 스냅인 개체의 뷰를 변경 하려고 하는 스냅인 개체에 알리기 위해 MMCN_PROPERTY_CHANGE 전송 합니다.

- MMCN_REMOVE_CHILDREN 스냅인에서 지정된 된 노드 아래에 추가 하는 전체 하위 트리를 삭제 해야 하는 경우에 전송 합니다.

- MMCN_RENAME 이름 바꾸기에 대 한 쿼리에 대 한 첫 번째 시간 및 이름 바꾸기 작업을 수행 하는 두 번째 시간에 전송 합니다.

- MMCN_SELECT 범위 또는 결과 뷰 창에서 항목을 선택 하는 경우에 전송 합니다.

- MMCN_SHOW 범위 항목을 선택 또는 처음으로 선택 취소 하는 경우에 전송 합니다.

- MMCN_VIEW_CHANGE 스냅인 수를 업데이트할 때 모든 보기 변경 될 때 전송 합니다.

*arg*<br/>
[in] 알림 유형에 따라 다릅니다.

*param*<br/>
[in] 알림 유형에 따라 다릅니다.

*pComponentData*<br/>
[out] 구현 하는 개체에 대 한 포인터 `IComponentData`합니다. 알림이 전달 되지 않고는 경우이 매개 변수는 NULL `IComponentData::Notify`합니다.

*pComponent*<br/>
[out] 구현 하는 개체에 대 한 포인터 `IComponent`합니다. 알림이 전달 되지 않고는 경우이 매개 변수는 NULL `IComponent::Notify`합니다.

*type*<br/>
[in] 개체의 형식을 지정합니다. 다음 값 중 하나일 수 있습니다.

- 범위 창 컨텍스트에 대해 CCT_SCOPE 데이터 개체입니다.

- 결과 창 컨텍스트에 대해 CCT_RESULT 데이터 개체입니다.

- 스냅인 관리자 컨텍스트에 대 한 CCT_SNAPIN_MANAGER 데이터 개체입니다.

- CCT_UNINITIALIZED 데이터 개체 유형이 잘못 되었습니다.

##  <a name="querypagesfor"></a>  CSnapInItemImpl::QueryPagesFor

스냅인에서 노드 속성 페이지 지원 하기 위해 호출 됩니다.

```
QueryPagesFor(DATA_OBJECT_TYPES type);
```

##  <a name="setmenuinsertionflags"></a>  CSnapInItemImpl::SetMenuInsertionFlags

지정 된 메뉴 삽입 플래그를 수정 하려면이 함수를 호출 *pInsertionAllowed*, 스냅인 개체에 대 한 합니다.

```
void SetMenuInsertionFlags(
    bool bBeforeInsertion,
    long* pInsertionAllowed);
```

### <a name="parameters"></a>매개 변수

*bBeforeInsertion*<br/>
[in] 항목의 상황에 맞는 메뉴에 추가 되기 전에 함수를 호출 해야 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

*pInsertionAllowed*<br/>
[out에서] 식별 Microsoft 관리 콘솔 MMC 정의 메뉴 항목 삽입 지점을 사용할 수 있는 합니다. 다음 플래그의 조합일 수 있습니다.

- 상황에 맞는 메뉴의 맨 위에 있는 CCM_INSERTIONALLOWED_TOP 항목을 삽입할 수 있습니다.

- 새로 만들기 메뉴에서 CCM_INSERTIONALLOWED_NEW 항목을 삽입할 수 있습니다.

- 작업 하위 메뉴에 CCM_INSERTIONALLOWED_TASK 항목을 삽입할 수 있습니다.

- 결과 창 상황에 맞는 메뉴 보기 하위 메뉴 또는 도구 모음 보기 메뉴에서 CCM_INSERTIONALLOWED_VIEW 항목을 삽입할 수 있습니다.

### <a name="remarks"></a>설명

기본 스냅인을 개발 하는 경우에 타사 확장을 추가할 수 있는 메뉴 항목의 종류를 제한 하는 방법으로 삽입 플래그를 재설정할 수 있습니다. 예를 들어, 기본 스냅인 확장 자신의 새로 만들기 메뉴 항목을 추가 하지 않도록 하려면 CCM_INSERTIONALLOWED_NEW 플래그를 지우려면 수 있습니다.

비트를 설정 하지 않아야 *pInsertionAllowed* 원래 지우지입니다. 이후 버전의 MMC는 현재 정의 되지 않은 비트를 변경 하지 않아야 하므로 현재 정의 된 비트를 사용할 수 있습니다.

##  <a name="settoolbarbuttoninfo"></a>  CSnapInItemImpl::SetToolbarButtonInfo

도구 모음을 만들기 전에 스냅인 개체의 모든 도구 모음 단추 스타일을 수정 하려면이 함수를 호출 합니다.

```
void SetToolbarButtonInfo(
    UINT id,
    BYTE* fsState,
    BYTE* fsType);
```

### <a name="parameters"></a>매개 변수

*ID*<br/>
[in] ID를 설정할 도구 모음 단추입니다.

*fsState*<br/>
[in] 단추 상태 플래그입니다. 다음 중 하나 이상의 수 있습니다.

- TBSTATE_CHECKED 단추 TBSTYLE_CHECKED 스타일 있으며입니다.

- TBSTATE_ENABLED 단추 사용자 입력을 허용합니다. 이 상태 없는 단추 사용자 입력을 허용 하지 않습니다 및 회색으로 나타납니다.

- TBSTATE_HIDDEN 단추가 표시 되지 않으며 사용자 입력을 받을 수 없습니다.

- TBSTATE_INDETERMINATE 단추가 흐리게 표시 됩니다.

- 단추를 눌렀는지 TBSTATE_PRESSED 합니다.

- 줄 바꿈을 TBSTATE_WRAP 단추는 다음과 같습니다. 단추는 TBSTATE_ENABLED 있어야 합니다.

*fsType*<br/>
[in] 단추 상태 플래그입니다. 다음 중 하나 이상의 수 있습니다.

- TBSTYLE_BUTTON 표준 누름 단추를 만듭니다.

- 누름 및 not 누른 상태로 될 때마다 사용자를 전환 하는 단추 클릭 TBSTYLE_CHECK 만듭니다. 누름 상태의 경우 단추가 다른 배경색을 됩니다.

- TBSTYLE_CHECKGROUP 그룹의 다른 단추를 누를 때까지 유지 되는 확인 단추 누름을 만듭니다.

- TBSTYLE_GROUP 그룹의 다른 단추를 누를 때까지 유지 되는 단추 누름을 만듭니다.

- TBSTYLE_SEP 단추 그룹 사이의 작은 간격을 제공 하는 구분 기호를 만듭니다. 이 스타일에 있는 단추는 사용자 입력을 받지 않습니다.

##  <a name="updatemenustate"></a>  CSnapInItemImpl::UpdateMenuState

스냅인 개체의 상황에 맞는 메뉴에 삽입 하기 전에 메뉴 항목을 수정 하려면이 함수를 호출 합니다.

```
void UpdateMenuState(
    UINT id,
    LPTSTR pBuf,
    UINT* flags);
```

### <a name="parameters"></a>매개 변수

*ID*<br/>
[in] 설정 메뉴 항목의 ID입니다.

*pBuf*<br/>
[in] 업데이트 메뉴 항목에 대 한 문자열에 대 한 포인터입니다.

*flags*<br/>
[in] 새 상태 플래그를 지정합니다. 다음 플래그의 조합일 수 있습니다.

- MF_POPUP 상황에 맞는 메뉴 내에서 하위 메뉴 임을 지정 합니다. 메뉴 항목, 삽입 지점 및 추가 하위 메뉴를 사용 하 여이 하위 메뉴에 추가할 수 있습니다 해당 `lCommandID` 로 해당 `IInsertionPointID`합니다.

- MF_BITMAP 및 MF_OWNERDRAW 이러한 플래그는 사용할 수 없으며 E_INVALIDARG의 값이 반환 됩니다.

- MF_SEPARATOR 가로 구분선을 그립니다. 만 `IContextMenuProvider` MF_SEPARATOR 집합을 사용 하 여 메뉴 항목을 추가할 수 있습니다.

- MF_CHECKED 메뉴 항목 옆에 있는 확인 표시를 배치합니다.

- MF_DISABLED 사용 하지 않도록 설정 메뉴 항목을 선택할 수 없도록 하지만 플래그 않습니다 하지 회색 것입니다.

- 선택할 수 있습니다, 회색으로 표시 된 상태에서 복원 되므로 MF_ENABLED 메뉴 항목을 수 있습니다.

- MF_GRAYED 사용 하지 않도록 설정 메뉴 항목을 선택할 수 없도록 표시 합니다.

- 메뉴 모음에 대 한 플래그를 MF_MENUBREAK 동일 MF_MENUBARBREAK 함수입니다. 드롭다운 메뉴, 하위 메뉴 또는 바로 가기 메뉴를 세로 선으로 기존 열에서 새 열 구분 됩니다.

- MF_MENUBREAK (메뉴 모음)에 대 한 새 줄에 항목을 배치 하거나 열을 구분 하지 않고 (드롭다운 메뉴, 하위 메뉴 또는 바로 가기 메뉴)에 새 열에 있습니다.

- (기본값) 항목 옆에 있는 확인 표시를 배치 하지 MF_UNCHECKED 않습니다.

플래그의 다음 그룹은 함께 사용할 수 없습니다.

- MF_DISABLED MF_ENABLED, 하며 MF_GRAYED 합니다.

- MF_MENUBARBREAK 및 MF_MENUBREAK 합니다.

- MF_CHECKED 및 MF_UNCHECKED 합니다.

##  <a name="updatetoolbarbutton"></a>  CSnapInItemImpl::UpdateToolbarButton

표시 하기 전에 스냅인 개체의 도구 모음 단추를 수정 하려면이 함수를 호출 합니다.

```
BOOL UpdateToolbarButton(UINT id, BYTE fsState);
```

### <a name="parameters"></a>매개 변수

*ID*<br/>
업데이트할 도구 모음 단추의 단추 ID를 지정 합니다.

*fsState*<br/>
도구 모음 단추 상태를 지정합니다. 이 상태를 설정할 경우 TRUE를 반환 합니다. 다음 플래그의 조합일 수 있습니다.

- 사용자 입력을 허용 하는 단추를 사용 합니다. 이 상태 없는 단추 사용자 입력을 허용 하지 않습니다 및 회색으로 나타납니다.

- 단추에 스타일을 선택된 및 눌렀는지 확인 합니다.

- HIDDEN 단추가 표시 되지 않으며 사용자 입력을 받을 수 없습니다.

- 비활성화 된 단추는 흐리게 표시 합니다.

- 단추를 눌렀는지 BUTTONPRESSED 합니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)
