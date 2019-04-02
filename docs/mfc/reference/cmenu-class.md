---
title: CMenu 클래스
ms.date: 11/04/2016
f1_keywords:
- CMenu
- AFXWIN/CMenu
- AFXWIN/CMenu::CMenu
- AFXWIN/CMenu::AppendMenu
- AFXWIN/CMenu::Attach
- AFXWIN/CMenu::CheckMenuItem
- AFXWIN/CMenu::CheckMenuRadioItem
- AFXWIN/CMenu::CreateMenu
- AFXWIN/CMenu::CreatePopupMenu
- AFXWIN/CMenu::DeleteMenu
- AFXWIN/CMenu::DeleteTempMap
- AFXWIN/CMenu::DestroyMenu
- AFXWIN/CMenu::Detach
- AFXWIN/CMenu::DrawItem
- AFXWIN/CMenu::EnableMenuItem
- AFXWIN/CMenu::FromHandle
- AFXWIN/CMenu::GetDefaultItem
- AFXWIN/CMenu::GetMenuContextHelpId
- AFXWIN/CMenu::GetMenuInfo
- AFXWIN/CMenu::GetMenuItemCount
- AFXWIN/CMenu::GetMenuItemID
- AFXWIN/CMenu::GetMenuItemInfo
- AFXWIN/CMenu::GetMenuState
- AFXWIN/CMenu::GetMenuString
- AFXWIN/CMenu::GetSafeHmenu
- AFXWIN/CMenu::GetSubMenu
- AFXWIN/CMenu::InsertMenu
- AFXWIN/CMenu::InsertMenuItem
- AFXWIN/CMenu::LoadMenu
- AFXWIN/CMenu::LoadMenuIndirect
- AFXWIN/CMenu::MeasureItem
- AFXWIN/CMenu::ModifyMenu
- AFXWIN/CMenu::RemoveMenu
- AFXWIN/CMenu::SetDefaultItem
- AFXWIN/CMenu::SetMenuContextHelpId
- AFXWIN/CMenu::SetMenuInfo
- AFXWIN/CMenu::SetMenuItemBitmaps
- AFXWIN/CMenu::SetMenuItemInfo
- AFXWIN/CMenu::TrackPopupMenu
- AFXWIN/CMenu::TrackPopupMenuEx
- AFXWIN/CMenu::m_hMenu
helpviewer_keywords:
- CMenu [MFC], CMenu
- CMenu [MFC], AppendMenu
- CMenu [MFC], Attach
- CMenu [MFC], CheckMenuItem
- CMenu [MFC], CheckMenuRadioItem
- CMenu [MFC], CreateMenu
- CMenu [MFC], CreatePopupMenu
- CMenu [MFC], DeleteMenu
- CMenu [MFC], DeleteTempMap
- CMenu [MFC], DestroyMenu
- CMenu [MFC], Detach
- CMenu [MFC], DrawItem
- CMenu [MFC], EnableMenuItem
- CMenu [MFC], FromHandle
- CMenu [MFC], GetDefaultItem
- CMenu [MFC], GetMenuContextHelpId
- CMenu [MFC], GetMenuInfo
- CMenu [MFC], GetMenuItemCount
- CMenu [MFC], GetMenuItemID
- CMenu [MFC], GetMenuItemInfo
- CMenu [MFC], GetMenuState
- CMenu [MFC], GetMenuString
- CMenu [MFC], GetSafeHmenu
- CMenu [MFC], GetSubMenu
- CMenu [MFC], InsertMenu
- CMenu [MFC], InsertMenuItem
- CMenu [MFC], LoadMenu
- CMenu [MFC], LoadMenuIndirect
- CMenu [MFC], MeasureItem
- CMenu [MFC], ModifyMenu
- CMenu [MFC], RemoveMenu
- CMenu [MFC], SetDefaultItem
- CMenu [MFC], SetMenuContextHelpId
- CMenu [MFC], SetMenuInfo
- CMenu [MFC], SetMenuItemBitmaps
- CMenu [MFC], SetMenuItemInfo
- CMenu [MFC], TrackPopupMenu
- CMenu [MFC], TrackPopupMenuEx
- CMenu [MFC], m_hMenu
ms.assetid: 40cacfdc-d45c-4ec7-bf28-991c72812499
ms.openlocfilehash: 464b59f7e598ea1901cf88c47c5887cbbf308607
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58770852"
---
# <a name="cmenu-class"></a>CMenu 클래스

Windows `HMENU`의 캡슐화입니다.

## <a name="syntax"></a>구문

```
class CMenu : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMenu::CMenu](#cmenu)|`CMenu` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMenu::AppendMenu](#appendmenu)|이 메뉴의 끝에 새 항목을 추가합니다.|
|[CMenu::Attach](#attach)|연결에 대 한 Windows 메뉴 핸들을 `CMenu` 개체입니다.|
|[CMenu::CheckMenuItem](#checkmenuitem)|옆에 확인 표시를 배치 또는 팝업 메뉴에서 메뉴 항목에서 확인 표시를 제거 합니다.|
|[CMenu::CheckMenuRadioItem](#checkmenuradioitem)|메뉴 항목 옆에 있는 라디오 단추를 배치 하 고 라디오 단추 그룹의 다른 메뉴 항목을 모두 제거 합니다.|
|[CMenu::CreateMenu](#createmenu)|빈 메뉴를 만들고 연결 하는 `CMenu` 개체입니다.|
|[CMenu::CreatePopupMenu](#createpopupmenu)|빈 팝업 메뉴를 만들고 연결 하는 `CMenu` 개체입니다.|
|[CMenu::DeleteMenu](#deletemenu)|메뉴에서 지정된 된 항목을 삭제합니다. 메뉴 항목에는 연결 된 팝업 메뉴를 팝업 메뉴에 대 한 핸들을 소멸 하 고 사용 된 메모리를 해제 합니다.|
|[CMenu::DeleteTempMap](#deletetempmap)|임시 삭제 `CMenu` 개체에 의해 생성 된 `FromHandle` 멤버 함수입니다.|
|[CMenu::DestroyMenu](#destroymenu)|에 연결 하는 메뉴를 소멸을 `CMenu` 개체 및 메뉴 차지한 메모리를 해제 합니다.|
|[CMenu::Detach](#detach)|Windows 메뉴 핸들을 분리는 `CMenu` 개체 핸들을 반환 합니다.|
|[CMenu::DrawItem](#drawitem)|소유자가 그린 메뉴 변경 시각적 측면이 때 프레임 워크에서 호출 됩니다.|
|[CMenu::EnableMenuItem](#enablemenuitem)|사용 하지 않도록 설정, 사용 하거나 (회색)을 흐리게 표시 메뉴 항목입니다.|
|[CMenu::FromHandle](#fromhandle)|에 대 한 포인터를 반환 합니다.는 `CMenu` Windows 메뉴 핸들을 지정 된 개체입니다.|
|[CMenu::GetDefaultItem](#getdefaultitem)|지정 된 메뉴의 기본 메뉴 항목을 결정합니다.|
|[CMenu::GetMenuContextHelpId](#getmenucontexthelpid)|메뉴를 사용 하 여 연결 된 도움말 컨텍스트 ID를 검색 합니다.|
|[CMenu::GetMenuInfo](#getmenuinfo)|특정 메뉴에 대 한 정보를 검색합니다.|
|[CMenu::GetMenuItemCount](#getmenuitemcount)|팝업 또는 최상위 메뉴에서 항목의 수를 결정합니다.|
|[CMenu::GetMenuItemID](#getmenuitemid)|지정된 된 위치에 있는 메뉴 항목에 대 한 메뉴 항목 식별자를 가져옵니다.|
|[CMenu::GetMenuItemInfo](#getmenuiteminfo)|메뉴 항목에 대 한 정보를 검색합니다.|
|[CMenu::GetMenuState](#getmenustate)|팝업 메뉴의 항목 수가 지정 된 메뉴 항목의 상태를 반환합니다.|
|[CMenu::GetMenuString](#getmenustring)|지정한 메뉴 항목의 레이블을 검색합니다.|
|[CMenu::GetSafeHmenu](#getsafehmenu)|반환 된 `m_hMenu` 이 래핑한 `CMenu` 개체입니다.|
|[CMenu::GetSubMenu](#getsubmenu)|팝업 메뉴에 대 한 포인터를 검색합니다.|
|[CMenu::InsertMenu](#insertmenu)|드롭다운 메뉴는 다른 항목을 이동 하면서 지정된 된 위치에 새 메뉴 항목을 삽입 합니다.|
|[CMenu::InsertMenuItem](#insertmenuitem)|메뉴의 지정된 된 위치에 새 메뉴 항목을 삽입합니다.|
|[CMenu::LoadMenu](#loadmenu)|실행 파일에서 메뉴 리소스를 로드 하 고 연결 하는 `CMenu` 개체입니다.|
|[CMenu::LoadMenuIndirect](#loadmenuindirect)|메모리의 메뉴 템플릿에서 메뉴를 로드 하 고 연결 하는 `CMenu` 개체입니다.|
|[CMenu::MeasureItem](#measureitem)|소유자가 그린 메뉴는 만들어질 때 메뉴 크기를 결정 하기 위해 프레임 워크에서 호출 됩니다.|
|[CMenu::ModifyMenu](#modifymenu)|지정된 된 위치에 기존 메뉴 항목을 변경합니다.|
|[CMenu::RemoveMenu](#removemenu)|지정된 된 메뉴에서 연결 된 팝업 메뉴를 사용 하 여 메뉴 항목을 삭제합니다.|
|[CMenu::SetDefaultItem](#setdefaultitem)|지정된 된 메뉴의 기본 메뉴 항목을 설정합니다.|
|[CMenu::SetMenuContextHelpId](#setmenucontexthelpid)|메뉴와 연결할 도움말 컨텍스트 ID를 설정 합니다.|
|[CMenu::SetMenuInfo](#setmenuinfo)|특정 메뉴에 정보를 설정합니다.|
|[CMenu::SetMenuItemBitmaps](#setmenuitembitmaps)|메뉴 항목을 사용 하 여 지정 된 확인 표시 비트맵에 연결합니다.|
|[CMenu::SetMenuItemInfo](#setmenuiteminfo)|메뉴 항목에 대 한 정보를 변경합니다.|
|[CMenu::TrackPopupMenu](#trackpopupmenu)|지정된 된 위치에 부동 팝업 메뉴를 표시 하 고 팝업 메뉴에서 항목의 선택 집합을 추적 합니다.|
|[CMenu::TrackPopupMenuEx](#trackpopupmenuex)|지정된 된 위치에 부동 팝업 메뉴를 표시 하 고 팝업 메뉴에서 항목의 선택 집합을 추적 합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CMenu::operator HMENU](#operator_hmenu)|메뉴 개체의 핸들을 검색 합니다.|
|[CMenu::operator !=](#operator_neq)|두 개의 메뉴 개체가 같은지 여부를 결정 합니다.|
|[CMenu::operator = =](#operator_eq_eq)|두 개의 메뉴 개체가 같은지 여부를 결정 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CMenu::m_hMenu](#m_hmenu)|에 연결 된 Windows 메뉴에 대 한 핸들을 지정 합니다 `CMenu` 개체입니다.|

## <a name="remarks"></a>설명

만들기, 추적, 업데이트 및 제거 메뉴에 대 한 멤버 함수를 제공 합니다.

만들기는 `CMenu` 개체는 로컬 스택 프레임에서 호출 `CMenu`의 필요에 따라 새 메뉴를 조작 하는 멤버 함수입니다. 그런 다음 호출 [CWnd::SetMenu](../../mfc/reference/cwnd-class.md#setmenu) 창 메뉴 설정에 대 한 호출 바로 뒤의 `CMenu` 개체의 [분리](#detach) 멤버 함수입니다. `CWnd::SetMenu` 멤버 함수 새 메뉴에 창의 메뉴를 설정 하면 창 메뉴 변경 내용을 적용 하려면 다시 그려져 야 하 고 또한 창 메뉴의 소유권을 전달 합니다. 에 대 한 호출 `Detach` 에서 HMENU를 분리 합니다 `CMenu` 개체를 때 로컬 `CMenu` 변수 범위 밖으로 전달는 `CMenu` 개체 소멸자가 더 이상 소유 하 고 메뉴를 제거 하려고 시도 하지 않습니다. 메뉴 자체 창을 소멸 될 때 자동으로 제거 됩니다.

사용할 수는 [LoadMenuIndirect](#loadmenuindirect) 멤버 함수를 호출 하 여 리소스에서 생성 하는 메뉴 제외 하 고 메모리에 템플릿에서 메뉴를 만드는 [LoadMenu](#loadmenu) 더 쉽게 유지 관리 및 자체 메뉴 리소스 만들고 메뉴 편집기에서 수정할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CMenu`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="appendmenu"></a>  CMenu::AppendMenu

메뉴의 끝에 새 항목을 추가합니다.

```
BOOL AppendMenu(
    UINT nFlags,
    UINT_PTR nIDNewItem = 0,
    LPCTSTR lpszNewItem = NULL);

BOOL AppendMenu(
    UINT nFlags,
    UINT_PTR nIDNewItem,
    const CBitmap* pBmp);
```

### <a name="parameters"></a>매개 변수

*nFlags*<br/>
메뉴에 추가 될 때 새 메뉴 항목의 상태에 대 한 정보를 지정 합니다. 주의 섹션에 나열 된 값 중 하나 이상이 구성 됩니다.

*nIDNewItem*<br/>
새 메뉴 항목의 명령 ID를 지정 합니다. 또는 *nFlags* MF_POPUP, 메뉴 핸들으로 설정 됩니다 ( `HMENU`) 팝업 메뉴의 합니다. 합니다 *nIDNewItem* 매개 변수는 (필요 하지 않게) *nFlags* MF_SEPARATOR로 설정 됩니다.

*lpszNewItem*<br/>
새 메뉴 항목의 콘텐츠를 지정합니다. 합니다 *nFlags* 매개 변수를 해석 하 되 *lpszNewItem* 다음과 같은 방식:

|nFlags|LpszNewItem 해석|
|------------|-----------------------------------|
|MF_OWNERDRAW|응용 프로그램 메뉴 항목과 연결 된 추가 데이터를 유지 하는 데 사용할 수 있는 응용 프로그램에서 제공한 32 비트 값을 포함 합니다. 이 32 비트 값은 WM_MEASUREITEM 및 WM_DRAWITEM 메시지를 처리할 때 응용 프로그램에 사용할 수 있습니다. 값에 저장 되는 `itemData` 해당 메시지와 함께 제공 되는 구조체의 멤버입니다.|
|MF_STRING|Null로 끝나는 문자열에 대 한 포인터를 포함합니다. 기본 해석입니다.|
|MF_SEPARATOR|합니다 *lpszNewItem* (필요 없음) 매개 변수가 무시 됩니다.|

*pBmp*<br/>
가리키는 `CBitmap` 메뉴 항목으로 사용할 개체입니다.

### <a name="return-value"></a>반환 값

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

응용 프로그램에서 값을 설정 하 여 메뉴 항목의 상태를 지정할 수 *nFlags*합니다. 때 *nIDNewItem* 팝업 메뉴를 지정 합니다. 추가 되는 메뉴의 일부가 됩니다. 해당 메뉴 손상 되 면 추가 된 메뉴가 제거 됩니다. 추가 메뉴에서 분리 해야는 `CMenu` 충돌을 피하기 위해 개체입니다. MF_STRING와 MF_OWNERDRAW의 비트맵 버전에 대해 유효한는 `AppendMenu`합니다.

다음 목록에서 설정할 수 있는 플래그를 설명 합니다. *nFlags*:

- 기본 배치 MF_UNCHECKED 사용 하 여 MF_CHECKED 역할도 토글 항목 옆에 표시를 확인 합니다. 응용 프로그램에서 확인 표시 비트맵을 제공 하는 경우 (참조를 [SetMenuItemBitmaps](#setmenuitembitmaps) 멤버 함수), "에 확인 표시" 비트맵 표시 됩니다.

- 확인을 제거 하려면 MF_CHECKED 사용 하 여 MF_UNCHECKED 역할도 토글 항목 옆에 표시 합니다. 응용 프로그램에서 확인 표시 비트맵을 제공 하는 경우 (참조는 `SetMenuItemBitmaps` 멤버 함수)를 "끄기 확인 표시" 비트맵 표시 됩니다.

- MF_DISABLED를 선택할 수 없습니다. 하지만 해당 흐리게 표시 하지 않습니다 메뉴 항목을 사용 하지 않도록 설정 합니다.

- MF_ENABLED 있도록 메뉴 항목을 선택 하 고 흐리게 상태에서 복원 합니다.

- MF_GRAYED 메뉴 항목을 선택할 수 없습니다 하 고이 흐리게 표시 되도록 사용 하지 않도록 설정 합니다.

- MF_MENUBARBREAK 정적 메뉴 또는 팝업 메뉴에 새 열에 새 줄에 항목을 배치합니다. 새 팝업 메뉴 열 세로 줄을 구분 하 여 이전 열에서 구분 됩니다.

- MF_MENUBREAK 정적 메뉴 또는 팝업 메뉴에 새 열에 새 줄에 항목을 배치합니다. 열 사이의 구분선이 없이 배치 됩니다.

- MF_OWNERDRAW 항목 소유자 그리기 항목 임을 지정 합니다. 메뉴는 처음으로 표시 되 면 메뉴를 소유 하는 창 메뉴 항목의 너비와 높이 검색 하는 WM_MEASUREITEM 메시지를 받으면 합니다. WM_DRAWITEM 메시지 소유자는 메뉴 항목의 모양을 업데이트 해야 될 때마다 전송 됩니다. 이 옵션을 최상위 메뉴 항목에 대해 올바르지 않습니다.

- 메뉴 항목에 연결 된 팝업 메뉴가 MF_POPUP 지정 합니다. ID 매개 변수는 항목과 연결 되는 팝업 메뉴에 대 한 핸들을 지정 합니다. 팝업 메뉴 항목에는 최상위 팝업 메뉴 또는 팝업 메뉴 계층 구조를 추가 하는 것에 대 한 사용 됩니다.

- MF_SEPARATOR 가로 구분선을 그립니다. 팝업 메뉴에만 사용할 수 있습니다. 이 줄을 흐리게 표시, 비활성화 하거나 강조 표시 될 수 없습니다. 다른 매개 변수는 무시 됩니다.

- MF_STRING 메뉴 항목을 문자열로 지정 합니다.

다음 그룹의 각 상호 배타적인를 함께 사용할 수 없는 플래그를 나열 합니다.

- MF_DISABLED, MF_ENABLED, 및 MF_GRAYED

- MF_STRING, MF_OWNERDRAW, MF_SEPARATOR, 및 비트맵 버전

- MF_MENUBARBREAK 및 MF_MENUBREAK

- MF_CHECKED 및 MF_UNCHECKED

(여부 창 표시 됨)는 창이 변경 될 때마다에 상주 하는 메뉴, 응용 프로그램을 호출 해야 [CWnd::DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar)합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CMenu::CreateMenu](#createmenu)합니다.

##  <a name="attach"></a>  CMenu::Attach

기존 Windows 메뉴에 연결 된 `CMenu` 개체입니다.

```
BOOL Attach(HMENU hMenu);
```

### <a name="parameters"></a>매개 변수

*hMenu*<br/>
Windows 메뉴에 대 한 핸들을 지정합니다.

### <a name="return-value"></a>반환 값

작업에 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

메뉴에 이미 연결 되어 있으면이 함수를 호출할 수 해야는 `CMenu` 개체입니다. 메뉴 핸들에 저장 되는 `m_hMenu` 데이터 멤버입니다.

조작 하려는 메뉴 이미 창에 연결 하는 경우 사용할 수 있습니다 합니다 [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu) 메뉴에 대 한 핸들을 가져오는 함수를 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]

##  <a name="checkmenuitem"></a>  CMenu::CheckMenuItem

확인 표시를 추가 또는 팝업 메뉴에서 메뉴 항목에서 확인 표시를 제거 합니다.

```
UINT CheckMenuItem(
    UINT nIDCheckItem,
    UINT nCheck);
```

### <a name="parameters"></a>매개 변수

*nIDCheckItem*<br/>
기준으로 검사할 메뉴 항목을 지정 *nCheck*합니다.

*nCheck*<br/>
메뉴 항목을 확인 하는 방법 및 메뉴에서 항목의 위치를 확인 하는 방법을 지정 합니다. 합니다 *nCheck* 매개 변수는 MF_BYPOSITION 또는 MF_BYCOMMAND 플래그로 MF_CHECKED MF_UNCHECKED의 조합 수 있습니다. 이러한 플래그는 비트 OR 연산자를 사용 하 여 결합할 수 있습니다. 다음과 같은 의미가 있습니다.

- MF_BYCOMMAND 지정 매개 변수는 기존 메뉴 항목의 명령 ID를 제공 합니다. 이 값이 기본값입니다.

- MF_BYPOSITION 매개 변수가 기존 메뉴 항목의 위치를 제공 하는 것을 지정 합니다. 위치 0의 첫 번째 항목이 표시 됩니다.

- 기본 배치 MF_UNCHECKED 사용 하 여 MF_CHECKED 역할도 토글 항목 옆에 표시를 확인 합니다.

- 확인을 제거 하려면 MF_CHECKED 사용 하 여 MF_UNCHECKED 역할도 토글 항목 옆에 표시 합니다.

### <a name="return-value"></a>반환 값

항목의 이전 상태: MF_CHECKED MF_UNCHECKED, 또는 메뉴 항목을 존재 하지 않은 경우에 0xFFFFFFFF입니다.

### <a name="remarks"></a>설명

합니다 *nIDCheckItem* 수정할 항목을 지정 하는 매개 변수입니다.

합니다 *nIDCheckItem* 매개 변수는 메뉴 항목 뿐만 아니라 팝업 메뉴 항목을 식별할 수 있습니다. 특수 단계 없이 팝업 메뉴 항목을 확인 해야 합니다. 최상위 메뉴 항목을 확인할 수 없습니다. 팝업 메뉴 항목을 연결 된 메뉴 항목 식별자를 없으므로 위치 여 확인할 수 있어야 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CMenu::GetMenuState](#getmenustate)합니다.

##  <a name="checkmenuradioitem"></a>  CMenu::CheckMenuRadioItem

지정 된 메뉴 항목을 확인 하 고 라디오 항목을 만듭니다.

```
BOOL CheckMenuRadioItem(
    UINT nIDFirst,
    UINT nIDLast,
    UINT nIDItem,
    UINT nFlags);
```

### <a name="parameters"></a>매개 변수

*nIDFirst*<br/>
지정 (ID 또는 값에 따라 오프셋 *nFlags*) 라디오 단추 그룹에서 첫 번째 메뉴 항목입니다.

*nIDLast*<br/>
지정 (ID 또는 값에 따라 오프셋 *nFlags*) 라디오 단추 그룹의 마지막 메뉴 항목입니다.

*nIDItem*<br/>
지정 (ID 또는 값에 따라 오프셋 *nFlags*) 라디오 단추를 사용 하 여 확인 되는 그룹에 있는 항목입니다.

*nFlags*<br/>
해석은 지정 *nIDFirst*하십시오 *nIDLast*, 및 *nIDItem* 다음과 같은 방식:

|nFlags|해석|
|------------|--------------------|
|MF_BYCOMMAND|매개 변수 제공 기존 메뉴 항목의 명령 ID를 지정 합니다. MF_BYCOMMAND 아니고 MF_BYPOSITION 설정 된 경우 이것이 기본값입니다.|
|MF_BYPOSITION|기존 메뉴 항목의 위치를 제공 하는 매개 변수는 지정 합니다. 위치 0의 첫 번째 항목이 표시 됩니다.|

### <a name="return-value"></a>반환 값

성공 하면 0이 아닌 값 그렇지 않은 0

### <a name="remarks"></a>설명

동시에, 함수는 연결된 된 그룹의 다른 모든 메뉴 항목을 선택 하거나 선택 취소 하 고 해당 항목에 대 한 라디오 항목 형식 플래그를 지웁니다. 선택한 항목은 비트맵을 확인 표시 대신 라디오 단추 (또는 글머리 기호) 비트맵을 사용 하 여 표시 됩니다.

### <a name="example"></a>예제

  예를 참조 하세요 [ON_COMMAND_RANGE](message-map-macros-mfc.md#on_command_range)합니다.

##  <a name="cmenu"></a>  CMenu::CMenu

빈 메뉴를 만들고 연결 하는 `CMenu` 개체입니다.

```
CMenu();
```

### <a name="remarks"></a>설명

메뉴는 만들기 중 하나를 호출 하거나의 멤버 함수를 로드할 때까지 만들어지지 않습니다. `CMenu:`

- [CreateMenu](#createmenu)

- [CreatePopupMenu](#createpopupmenu)

- [LoadMenu](#loadmenu)

- [LoadMenuIndirect](#loadmenuindirect)

- [Attach](#attach)

##  <a name="createmenu"></a>  CMenu::CreateMenu

메뉴를 만들고 연결 하는 `CMenu` 개체입니다.

```
BOOL CreateMenu();
```

### <a name="return-value"></a>반환 값

메뉴 성공적으로 만들어진 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

메뉴 처음에 비어 있습니다. 사용 하 여 메뉴 항목을 추가할 수는 `AppendMenu` 또는 `InsertMenu` 멤버 함수입니다.

창 메뉴에 할당 된 경우 창이 소멸 될 때 자동으로 제거 됩니다 것입니다.

를 종료 하기 전에 응용 프로그램 메뉴 창에 할당 되지 않은 경우 메뉴를 사용 하 여 연결 된 시스템 리소스를 해제 해야 합니다. 응용 프로그램 메뉴를 호출 하 여 해제 합니다 [DestroyMenu](#destroymenu) 멤버 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#22](../../mfc/reference/codesnippet/cpp/cmenu-class_2.cpp)]

##  <a name="createpopupmenu"></a>  CMenu::CreatePopupMenu

팝업 메뉴를 만들고 연결 하는 `CMenu` 개체입니다.

```
BOOL CreatePopupMenu();
```

### <a name="return-value"></a>반환 값

팝업 메뉴 성공적으로 만들어진 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

메뉴 처음에 비어 있습니다. 사용 하 여 메뉴 항목을 추가할 수는 `AppendMenu` 또는 `InsertMenu` 멤버 함수입니다. 응용 프로그램 기존 메뉴 또는 팝업 메뉴에 팝업 메뉴를 추가할 수 있습니다. `TrackPopupMenu` 부동 팝업 메뉴로이 메뉴를 표시 하 고 팝업 메뉴에서 선택 항목을 추적 하는 멤버 함수를 사용할 수 있습니다.

창 메뉴에 할당 된 경우 창이 소멸 될 때 자동으로 제거 됩니다 것입니다. 기존 메뉴에 메뉴 추가 되 면 해당 메뉴 소멸 될 때 자동으로 제거 됩니다 것입니다.

를 종료 하기 전에 응용 프로그램 메뉴 창에 할당 되지 않은 경우 팝업 메뉴를 사용 하 여 연결 된 시스템 리소스를 해제 해야 합니다. 응용 프로그램 메뉴를 호출 하 여 해제 합니다 [DestroyMenu](#destroymenu) 멤버 함수입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CMenu::CreateMenu](#createmenu)합니다.

##  <a name="deletemenu"></a>  CMenu::DeleteMenu

메뉴에서 항목을 삭제합니다.

```
BOOL DeleteMenu(
    UINT nPosition,
    UINT nFlags);
```

### <a name="parameters"></a>매개 변수

*nPosition*<br/>
기준으로 삭제할 수에 있는 메뉴 항목을 지정 *nFlags*합니다.

*nFlags*<br/>
해석 하는 데 사용 됩니다 *찾기를* 다음과 같은 방법으로:

|nFlags|찾기 해석|
|------------|---------------------------------|
|MF_BYCOMMAND|매개 변수 제공 기존 메뉴 항목의 명령 ID를 지정 합니다. MF_BYCOMMAND 아니고 MF_BYPOSITION 설정 된 경우 이것이 기본값입니다.|
|MF_BYPOSITION|기존 메뉴 항목의 위치를 제공 하는 매개 변수는 지정 합니다. 위치 0의 첫 번째 항목이 표시 됩니다.|

### <a name="return-value"></a>반환 값

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

메뉴 항목에는 연결 된 팝업 메뉴 `DeleteMenu` 팝업 메뉴에 대 한 핸들을 소멸 시킵니다 및 팝업 메뉴에서 사용 하는 메모리를 해제 합니다.

(여부 창 표시 됨)는 창이 변경 될 때마다에 상주 하는 메뉴, 응용 프로그램을 호출 해야 합니다 [CWnd::DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar)합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu)합니다.

##  <a name="deletetempmap"></a>  CMenu::DeleteTempMap

자동으로 호출 합니다 `CWinApp` 유휴 시간 처리기 삭제 임시 `CMenu` 가 만든 개체를 [FromHandle](#fromhandle) 멤버 함수입니다.

```
static void PASCAL DeleteTempMap();
```

### <a name="remarks"></a>설명

`DeleteTempMap` 임시에 연결 된 Windows 메뉴 개체를 분리 `CMenu` 개체를 삭제 하기 전에 `CMenu` 개체입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#23](../../mfc/reference/codesnippet/cpp/cmenu-class_3.cpp)]

##  <a name="destroymenu"></a>  CMenu::DestroyMenu

메뉴 및 사용 된 모든 Windows 리소스를 제거 합니다.

```
BOOL DestroyMenu();
```

### <a name="return-value"></a>반환 값

0이 아닌 메뉴 소멸 됩니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

메뉴에서 분리 되는 `CMenu` 제거 되기 전에 개체입니다. Windows `DestroyMenu` 함수에서 자동으로 호출 되는 `CMenu` 소멸자입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CMenu::CreateMenu](#createmenu)합니다.

##  <a name="detach"></a>  CMenu::Detach

Windows 메뉴에서 분리를 `CMenu` 개체 핸들을 반환 합니다.

```
HMENU Detach();
```

### <a name="return-value"></a>반환 값

Windows 메뉴에 성공할 경우 HMENU, 형식의 핸들을 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

`m_hMenu` 데이터 멤버는 NULL로 설정 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]

##  <a name="drawitem"></a>  CMenu::DrawItem

소유자가 그린 메뉴 변경 시각적 측면이 때 프레임 워크에서 호출 됩니다.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpDrawItemStruct*<br/>
에 대 한 포인터를 [DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct) 필요한 드로잉의 종류에 대 한 정보를 포함 하는 구조입니다.

### <a name="remarks"></a>설명

합니다 `itemAction` 의 멤버는 `DRAWITEMSTRUCT` 구조 정의 그리기 작업 수행 수입니다. 소유자 그리기에 대 한 그리기를 구현 하려면이 멤버 함수를 재정의 `CMenu` 개체입니다. 응용 프로그램에 제공 된 디스플레이 컨텍스트를 위해 선택한 모든 그래픽 장치 GDI (인터페이스) 개체를 복원 해야 *lpDrawItemStruct* 이 멤버 함수 종료 전에 합니다.

참조 [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) 에 대 한 설명은 `DRAWITEMSTRUCT` 구조입니다.

### <a name="example"></a>예제

MFC에서 다음 코드는 [CTRLTEST](../../overview/visual-cpp-samples.md) 샘플:

[!code-cpp[NVC_MFCWindowing#24](../../mfc/reference/codesnippet/cpp/cmenu-class_4.cpp)]

##  <a name="enablemenuitem"></a>  CMenu::EnableMenuItem

사용 하도록 설정, 사용 하지 않도록 설정, 또는 메뉴 항목을 흐리게 표시 합니다.

```
UINT EnableMenuItem(
    UINT nIDEnableItem,
    UINT nEnable);
```

### <a name="parameters"></a>매개 변수

*nIDEnableItem*<br/>
기준으로 사용 하도록 설정할 메뉴 항목을 지정 *nEnable*합니다. 이 매개 변수는 표준 메뉴 항목 뿐만 아니라 팝업 메뉴 항목에 지정할 수 있습니다.

*nEnable*<br/>
수행할 동작을 지정 합니다. MF_DISABLED, MF_ENABLED, 또는 MF_BYCOMMAND 또는 MF_BYPOSITION MF_GRAYED의 조합 수 있습니다. 이러한 값은 비트 OR 연산자를 사용 하 여 결합할 수 있습니다. 이러한 값에는 다음과 같은 의미가 있습니다.

- MF_BYCOMMAND 지정 매개 변수는 기존 메뉴 항목의 명령 ID를 제공 합니다. 이 값이 기본값입니다.

- MF_BYPOSITION 매개 변수가 기존 메뉴 항목의 위치를 제공 하는 것을 지정 합니다. 위치 0의 첫 번째 항목이 표시 됩니다.

- MF_DISABLED를 선택할 수 없습니다. 하지만 해당 흐리게 표시 하지 않습니다 메뉴 항목을 사용 하지 않도록 설정 합니다.

- MF_ENABLED 있도록 메뉴 항목을 선택 하 고 흐리게 상태에서 복원 합니다.

- MF_GRAYED 메뉴 항목을 선택할 수 없습니다 하 고이 흐리게 표시 되도록 사용 하지 않도록 설정 합니다.

### <a name="return-value"></a>반환 값

이전 상태 (MF_DISABLED, MF_ENABLED, 또는 MF_GRAYED) 또는 유효 하지 않은 경우-1입니다.

### <a name="remarks"></a>설명

합니다 [CreateMenu](#createmenu), [InsertMenu](#insertmenu)합니다 [ModifyMenu](#modifymenu), 및 [LoadMenuIndirect](#loadmenuindirect) 멤버 함수 (활성화 상태를 설정할 수도 있습니다 비활성화 또는 흐리게 표시) 메뉴 항목의 합니다.

올바른 사용 하 여 응용 프로그램 해야 MF_BYPOSITION 값을 사용 하 여 `CMenu`입니다. 경우는 `CMenu` 메뉴의 표시줄을 사용 (메뉴 모음에서 항목) 최상위 메뉴 항목을 영향을 받습니다. 위치별 팝업 또는 중첩 된 팝업 메뉴에서 항목의 상태를 설정 하려면 응용 프로그램 지정 해야 합니다는 `CMenu` 팝업 메뉴입니다.

MF_BYCOMMAND 플래그를 지정 하는 응용 프로그램을 Windows에 종속 된 모든 팝업 메뉴 항목을 확인 합니다 `CMenu`따라서 존재 하지 않는 중복 된 메뉴 항목을 사용 하 여는 `CMenu` 메뉴 표시줄 부족.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#25](../../mfc/reference/codesnippet/cpp/cmenu-class_5.cpp)]

##  <a name="fromhandle"></a>  CMenu::FromHandle

에 대 한 포인터를 반환 합니다.는 `CMenu` 메뉴에 대 한 Windows 핸들을 지정 된 개체입니다.

```
static CMenu* PASCAL FromHandle(HMENU hMenu);
```

### <a name="parameters"></a>매개 변수

*hMenu*<br/>
메뉴에는 Windows 핸들입니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `CMenu` 일시적 또는 영구적 수 있습니다.

### <a name="remarks"></a>설명

경우는 `CMenu` Windows 메뉴 개체에 임시 개체가 이미 연결 되지 않은 `CMenu` 개체를 만들어 연결 합니다.

이 임시 `CMenu` 개체는 응용 프로그램에서 임시 개체를 모두 삭제 됩니다 해당 이벤트 루프에 대 한 유휴 시간 때까지만 유효 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CMenu::CreateMenu](#createmenu)합니다.

##  <a name="getdefaultitem"></a>  CMenu::GetDefaultItem

지정 된 메뉴의 기본 메뉴 항목을 결정합니다.

```
UINT GetDefaultItem(
    UINT gmdiFlags,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>매개 변수

*gmdiFlags*<br/>
메뉴 항목에 대 한 함수가 검색 하는 방법을 지정 하는 값입니다. 이 매개 변수 없음, 1 또는 다음 값의 조합 수 있습니다.

|값|의미|
|-----------|-------------|
|GMDI_GOINTOPOPUPS|기본 항목 하위 메뉴가 열리는 중 하나인 경우 함수는 해당 하위 메뉴 재귀적으로 검색 하려면를 지정 합니다. 하위 메뉴에 기본 항목이 있는 경우 반환 값 하위 메뉴를 열고 항목을 식별 합니다.<br /><br /> 기본적으로 함수는 하위 메뉴가 열린 항목 인지에 관계 없이 지정 된 메뉴에서 첫 번째 기본 항목을 반환 합니다.|
|GMDI_USEDISABLED|비활성화 된 경우에 기본 항목을 반환 하는 함수 임을 지정 합니다.<br /><br /> 기본적으로 함수는 사용 안 함 또는 회색으로 표시 항목을 건너뜁니다.|

*fByPos*<br/>
메뉴 항목의 식별자 또는 위치로 검색할 것인지를 지정 하는 값입니다. 이 매개 변수가 FALSE 인 경우는 식별자가 반환 됩니다. 그렇지 않은 경우 위치가 반환 됩니다.

### <a name="return-value"></a>반환 값

함수가 성공할 경우 반환 값을 식별자 또는 메뉴 항목의 위치입니다. 함수가 실패 한 경우 반환 값은-1입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 함수의 동작을 구현 [GetMenuDefaultItem](/windows/desktop/api/winuser/nf-winuser-getmenudefaultitem)Windows SDK에 설명 된 대로 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CMenu::InsertMenu](#insertmenu)합니다.

##  <a name="getmenucontexthelpid"></a>  CMenu::GetMenuContextHelpId

연결 된 ID를 상황에 맞는 도움말 검색 `CMenu`합니다.

```
DWORD GetMenuContextHelpId() const;
```

### <a name="return-value"></a>반환 값

ID가 현재 연결 된 상황에 맞는 도움말 `CMenu` 요소가 있을 경우 0이 고, 그렇지 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CMenu::InsertMenu](#insertmenu)합니다.

##  <a name="getmenuinfo"></a>  CMenu::GetMenuInfo

메뉴에 대 한 정보를 검색합니다.

```
BOOL GetMenuInfo(LPMENUINFO lpcmi) const;
```

### <a name="parameters"></a>매개 변수

*lpcmi*<br/>
에 대 한 포인터를 [MENUINFO](/windows/desktop/api/winuser/ns-winuser-tagmenuinfo) 메뉴에 대 한 정보를 포함 하는 구조체.

### <a name="return-value"></a>반환 값

함수가 성공할 경우 반환 값은 0이 아닌; 그렇지 않은 경우 반환 값은 0입니다.

### <a name="remarks"></a>설명

메뉴에 대 한 정보를 검색 하려면이 함수를 호출 합니다.

##  <a name="getmenuitemcount"></a>  CMenu::GetMenuItemCount

팝업 또는 최상위 메뉴에서 항목의 수를 결정합니다.

```
UINT GetMenuItemCount() const;
```

### <a name="return-value"></a>반환 값

함수가 성공할 경우 메뉴의 항목 수 그렇지 않으면-1입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu)합니다.

##  <a name="getmenuitemid"></a>  CMenu::GetMenuItemID

정의한 위치에 있는 메뉴 항목에 대 한 메뉴 항목 식별자를 가져옵니다 *nPos*합니다.

```
UINT GetMenuItemID(int nPos) const;
```

### <a name="parameters"></a>매개 변수

*nPos*<br/>
위치 (0부터 시작) 메뉴 항목의 ID를 검색 하는 지정 합니다.

### <a name="return-value"></a>반환 값

함수에 성공 하는 경우 팝업 메뉴에서 지정된 된 항목에 대 한 항목 ID입니다. 팝업 메뉴 팝업 메뉴 내의 항목) (달리 지정된 된 항목을 사용 하는 경우 반환 값은-1입니다. 하는 경우 *nPos* 해당 구분 기호가 메뉴 항목에 반환 값은 0입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CMenu::InsertMenu](#insertmenu)합니다.

##  <a name="getmenuiteminfo"></a>  CMenu::GetMenuItemInfo

메뉴 항목에 대 한 정보를 검색합니다.

```
BOOL GetMenuItemInfo(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>매개 변수

*uItem*<br/>
식별자 또는 메뉴 항목에 대 한 정보를 가져올 수 위치입니다. 이 매개 변수의 의미 값에 따라 달라 집니다 `ByPos`합니다.

*lpMenuItemInfo*<br/>
에 대 한 포인터를 [MENUITEMINFO](/windows/desktop/api/winuser/ns-winuser-tagmenuiteminfoa)메뉴에 대 한 정보를 포함 하는 Windows SDK에 설명 된 대로 합니다.

*fByPos*<br/>
의미를 지정 하는 값 `nIDItem`합니다. 기본적으로 `ByPos` 은 FALSE 이며 해당 uItem 메뉴 항목 식별자를 나타냅니다. 경우 `ByPos` 설정 되지 않은 메뉴 항목 위치를 나타냅니다. FALSE로 합니다.

### <a name="return-value"></a>반환 값

함수가 성공 하면 반환 값은 0이 아닌 값입니다. 함수가 실패하면 반환 값은 0입니다. 확장 정보를 가져오려면 오류, Win32 함수를 사용 하 여 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)Windows SDK에 설명 된 대로 합니다.

### <a name="remarks"></a>설명

동작을 구현 하는이 멤버 함수는 Win32 함수의 [GetMenuItemInfo](/windows/desktop/api/winuser/nf-winuser-getmenuiteminfoa)Windows SDK에 설명 된 대로 합니다. MFC 구현에서 `GetMenuItemInfo`, 메뉴에 대 한 핸들을 사용 하지 마십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#26](../../mfc/reference/codesnippet/cpp/cmenu-class_6.cpp)]

##  <a name="getmenustate"></a>  CMenu::GetMenuState

팝업 메뉴의 항목 수가 지정 된 메뉴 항목의 상태를 반환합니다.

```
UINT GetMenuState(
    UINT nID,
    UINT nFlags) const;
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
메뉴 항목 ID를 기준으로 지정 *nFlags*합니다.

*nFlags*<br/>
특성을 지정 *nID*합니다. 다음 값 중 하나일 수 있습니다.

- MF_BYCOMMAND 지정 매개 변수는 기존 메뉴 항목의 명령 ID를 제공 합니다. 이 값이 기본값입니다.

- MF_BYPOSITION 매개 변수가 기존 메뉴 항목의 위치를 제공 하는 것을 지정 합니다. 위치 0의 첫 번째 항목이 표시 됩니다.

### <a name="return-value"></a>반환 값

지정된 된 항목이 없는 경우에 0xFFFFFFFF 값입니다. 하는 경우 *nId* 하 게 식별 하는 팝업 메뉴에서 높은 순서 바이트가 팝업 메뉴의 항목 수를 포함 하 고 팝업 메뉴를 사용 하 여 연결 된 메뉴 플래그를 포함 하는 낮은 순서 바이트입니다. 그렇지 않은 경우 반환 값입니다 (부울 또는)를 마스크 다음 목록에서 값 (이 마스크는 메뉴의 상태를 설명 하는 항목 *nId* 식별):

- 기본 배치 MF_UNCHECKED 사용 하 여 MF_CHECKED 역할도 토글 항목 옆에 표시를 확인 합니다. 응용 프로그램에서 확인 표시 비트맵을 제공 하는 경우 (참조는 `SetMenuItemBitmaps` 멤버 함수), "에 확인 표시" 비트맵 표시 됩니다.

- MF_DISABLED를 선택할 수 없습니다. 하지만 해당 흐리게 표시 하지 않습니다 메뉴 항목을 사용 하지 않도록 설정 합니다.

- MF_ENABLED 있도록 메뉴 항목을 선택 하 고 흐리게 상태에서 복원 합니다. 이 상수의 값이 0 인지 note 이 값을 사용 하는 경우 응용 프로그램 오류에 대 한 0에 대해 테스트 되지 해야 합니다.

- MF_GRAYED 메뉴 항목을 선택할 수 없습니다 하 고이 흐리게 표시 되도록 사용 하지 않도록 설정 합니다.

- MF_MENUBARBREAK 정적 메뉴 또는 팝업 메뉴에 새 열에 새 줄에 항목을 배치합니다. 새 팝업 메뉴 열 세로 줄을 구분 하 여 이전 열에서 구분 됩니다.

- MF_MENUBREAK 정적 메뉴 또는 팝업 메뉴에 새 열에 새 줄에 항목을 배치합니다. 열 사이의 구분선이 없이 배치 됩니다.

- MF_SEPARATOR 가로 구분선을 그립니다. 팝업 메뉴에만 사용할 수 있습니다. 이 줄을 흐리게 표시, 비활성화 하거나 강조 표시 될 수 없습니다. 다른 매개 변수는 무시 됩니다.

- 확인을 제거 하려면 MF_CHECKED 사용 하 여 MF_UNCHECKED 역할도 토글 항목 옆에 표시 합니다. 응용 프로그램에서 확인 표시 비트맵을 제공 하는 경우 (참조는 `SetMenuItemBitmaps` 멤버 함수)를 "끄기 확인 표시" 비트맵 표시 됩니다. 이 상수의 값이 0 인지 note 이 값을 사용 하는 경우 응용 프로그램 오류에 대 한 0에 대해 테스트 되지 해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#27](../../mfc/reference/codesnippet/cpp/cmenu-class_7.cpp)]

##  <a name="getmenustring"></a>  CMenu::GetMenuString

지정한 메뉴 항목의 레이블을 지정 된 버퍼에 복사합니다.

```
int GetMenuString(
    UINT nIDItem,
    LPTSTR lpString,
    int nMaxCount,
    UINT nFlags) const;

int GetMenuString(
    UINT nIDItem,
    CString& rString,
    UINT nFlags) const;
```

### <a name="parameters"></a>매개 변수

*nIDItem*<br/>
값에 따라 메뉴에서 메뉴 항목의 정수 식별자 또는 메뉴 항목의 오프셋을 지정 *nFlags*합니다.

*lpString*<br/>
레이블을 수신 하는 버퍼를 가리킵니다.

*rString*<br/>
에 대 한 참조를 `CString` 복사 메뉴 문자열을 수신 하는 개체입니다.

*nMaxCount*<br/>
복사할 레이블의 문자 단위로 최대 길이 지정 합니다. 레이블을에 지정 된 최대값 보다 깁니다 *nMaxCount*, 나머지 문자는 잘립니다.

*nFlags*<br/>
해석은 지정 된 *nIDItem* 매개 변수입니다. 다음 값 중 하나일 수 있습니다.

|nFlags|NIDItem 해석|
|------------|-------------------------------|
|MF_BYCOMMAND|매개 변수 제공 기존 메뉴 항목의 명령 ID를 지정 합니다. MF_BYCOMMAND 아니고 MF_BYPOSITION 설정 된 경우 이것이 기본값입니다.|
|MF_BYPOSITION|기존 메뉴 항목의 위치를 제공 하는 매개 변수는 지정 합니다. 위치 0의 첫 번째 항목이 표시 됩니다.|

### <a name="return-value"></a>반환 값

실제 null 종결자를 포함 하지 않습니다 버퍼에 복사 되는 문자 수를 지정 합니다.

### <a name="remarks"></a>설명

합니다 *nMaxCount* 매개 변수는 문자열 종료 null 문자를 수용할 수 있도록 레이블의 문자 수보다 하나 이어야 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CMenu::InsertMenu](#insertmenu)합니다.

##  <a name="getsafehmenu"></a>  CMenu::GetSafeHmenu

이 래핑 HMENU 반환 `CMenu` 개체 또는 NULL`CMenu` 포인터입니다.

```
HMENU GetSafeHmenu() const;
```

### <a name="example"></a>예제

  예를 참조 하세요 [CMenu::LoadMenu](#loadmenu)합니다.

##  <a name="getsubmenu"></a>  CMenu::GetSubMenu

검색 된 `CMenu` 팝업 메뉴의 개체입니다.

```
CMenu* GetSubMenu(int nPos) const;
```

### <a name="parameters"></a>매개 변수

*nPos*<br/>
메뉴에 포함 된 팝업 메뉴의 위치를 지정 합니다. 위치 값은 첫 번째 메뉴 항목의 0부터 시작합니다. 이 함수에 팝업 메뉴의 식별자를 사용할 수 없습니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `CMenu` 개체 `m_hMenu` 멤버의 지정 된 위치에 있을 때 팝업 메뉴 팝업 메뉴에 대 한 핸들을 포함, 그렇지 않으면 NULL입니다. 경우는 `CMenu` 개체가 존재 하지 않는 다음 임시 사용자가 만들어집니다. `CMenu` 반환 된 포인터를 저장 되어야 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CMenu::TrackPopupMenu](#trackpopupmenu)합니다.

##  <a name="insertmenu"></a>  CMenu::InsertMenu

에 지정 된 위치에 새 메뉴 항목을 삽입 *찾기를* 한 다른 항목 메뉴 아래로 이동 합니다.

```
BOOL InsertMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem = 0,
    LPCTSTR lpszNewItem = NULL);

BOOL InsertMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem,
    const CBitmap* pBmp);
```

### <a name="parameters"></a>매개 변수

*nPosition*<br/>
새 메뉴 항목을 삽입할 메뉴 항목 앞을 지정 합니다. 합니다 *nFlags* 매개 변수를 사용 하 여 해석할 수 있습니다 *찾기를* 다음과 같은 방법으로:

|nFlags|찾기 해석|
|------------|---------------------------------|
|MF_BYCOMMAND|매개 변수 제공 기존 메뉴 항목의 명령 ID를 지정 합니다. MF_BYCOMMAND 아니고 MF_BYPOSITION 설정 된 경우 이것이 기본값입니다.|
|MF_BYPOSITION|기존 메뉴 항목의 위치를 제공 하는 매개 변수는 지정 합니다. 위치 0의 첫 번째 항목이 표시 됩니다. 하는 경우 *찾기를* 가-1 이면 새 메뉴 항목이 메뉴의 끝에 추가 됩니다.|

*nFlags*<br/>
지정 하는 방법을 *찾기를* 해석 되 고 메뉴에 추가 될 때 새 메뉴 항목의 상태에 대 한 정보를 지정 합니다. 목록을 설정할 수 있는 플래그에 대 한 참조를 [AppendMenu](#appendmenu) 멤버 함수입니다. 둘 이상의 값을 지정 하려면 비트 OR 연산자를 사용 하 여 MF_BYCOMMAND 또는 MF_BYPOSITION 플래그를 사용 하 여 결합 합니다.

*nIDNewItem*<br/>
새 메뉴 항목의 명령 ID를 지정 합니다. 또는 *nFlags* MF_POPUP, 팝업 메뉴의 메뉴 핸들 (HMENU)로 설정 됩니다. 합니다 *nIDNewItem* 매개 변수는 (필요 하지 않게) *nFlags* MF_SEPARATOR로 설정 됩니다.

*lpszNewItem*<br/>
새 메뉴 항목의 콘텐츠를 지정합니다. *nFlags* 해석에 사용할 수 있습니다 *lpszNewItem* 다음과 같은 방법으로:

|nFlags|LpszNewItem 해석|
|------------|-----------------------------------|
|MF_OWNERDRAW|응용 프로그램 메뉴 항목과 연결 된 추가 데이터를 유지 하는 데 사용할 수 있는 응용 프로그램에서 제공한 32 비트 값을 포함 합니다. 이 32 비트 값을 응용 프로그램에 사용할 수는 `itemData` 에서 제공 하는 구조체의 멤버는 [WM_MEASUREITEM](/windows/desktop/Controls/wm-measureitem) 하 고 [WM_DRAWITEM](/windows/desktop/Controls/wm-drawitem) 메시지. 이러한 메시지에는 메뉴 항목이 처음 표시 되거나 변경 되 면 전송 됩니다.|
|MF_STRING|Null로 끝나는 문자열에 대 한 긴 포인터를 포함합니다. 기본 해석입니다.|
|MF_SEPARATOR|합니다 *lpszNewItem* (필요 없음) 매개 변수가 무시 됩니다.|

*pBmp*<br/>
가리키는 `CBitmap` 메뉴 항목으로 사용할 개체입니다.

### <a name="return-value"></a>반환 값

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

응용 프로그램에서 값을 설정 하 여 메뉴 항목의 상태를 지정할 수 *nFlags*합니다.

(여부 창 표시 됨)는 창이 변경 될 때마다에 상주 하는 메뉴, 응용 프로그램을 호출 해야 `CWnd::DrawMenuBar`합니다.

때 *nIDNewItem* 팝업 메뉴 지정 삽입 되는 메뉴의 일부가 됩니다. 해당 메뉴 손상 된 경우에 삽입된 메뉴 소멸 됩니다. 삽입된 메뉴는에서 분리 해야는 `CMenu` 충돌을 피하기 위해 개체입니다.

여러 문서 MDI (인터페이스) 자식 창이 최대화 되어 활성 및이 함수를 호출 하 고 메뉴 MF_BYPOSITION 플래그를 지정 하 여 MDI 응용 프로그램의 메뉴에 팝업 메뉴는 응용 프로그램 삽입 한 위치 보다 남아 있는 시간을 미래의 시간을 삽입 한 경우 필요합니다. 활성 MDI 자식 창의 컨트롤 메뉴를 MDI 프레임 창의 메뉴 표시줄의 첫 번째 위치에 삽입 되어 있으므로이 발생 합니다. 메뉴를 올바르게 배치 하려면 응용 프로그램에 사용 되는 위치 값 1을 추가 해야 합니다. 응용 프로그램 WM_MDIGETACTIVE 메시지를 사용 하 여 현재 활성 자식 창 최대화 되었는지 여부를 결정할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#28](../../mfc/reference/codesnippet/cpp/cmenu-class_8.cpp)]

##  <a name="insertmenuitem"></a>  CMenu::InsertMenuItem

메뉴의 지정된 된 위치에 새 메뉴 항목을 삽입합니다.

```
BOOL InsertMenuItem(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>매개 변수

*uItem*<br/>
에 대 한 설명을 참조 하세요 *uItem* 에 [InsertMenuItem](/windows/desktop/api/winuser/nf-winuser-insertmenuitema) Windows SDK에 있습니다.

*lpMenuItemInfo*<br/>
에 대 한 설명을 참조 하세요 *lpmii* 에서 `InsertMenuItem` Windows SDK에 있습니다.

*fByPos*<br/>
에 대 한 설명을 참조 하세요 *fByPosition* 에서 `InsertMenuItem` Windows SDK에 있습니다.

### <a name="remarks"></a>설명

이 함수를 래핑하고 [InsertMenuItem](/windows/desktop/api/winuser/nf-winuser-insertmenuitema)Windows SDK에서 설명 합니다.

##  <a name="loadmenu"></a>  CMenu::LoadMenu

응용 프로그램의 실행 파일에서 메뉴 리소스를 로드 하 고 연결 하는 `CMenu` 개체입니다.

```
BOOL LoadMenu(LPCTSTR lpszResourceName);
BOOL LoadMenu(UINT nIDResource);
```

### <a name="parameters"></a>매개 변수

*lpszResourceName*<br/>
로드 메뉴 리소스의 이름이 포함 된 null로 끝나는 문자열을 가리킵니다.

*nIDResource*<br/>
로드할 메뉴 리소스의 메뉴 ID를 지정 합니다.

### <a name="return-value"></a>반환 값

메뉴 리소스를 성공적으로 로드 한 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

를 종료 하기 전에 응용 프로그램 메뉴 창에 할당 되지 않은 경우 메뉴를 사용 하 여 연결 된 시스템 리소스를 해제 해야 합니다. 응용 프로그램 메뉴를 호출 하 여 해제 합니다 [DestroyMenu](#destroymenu) 멤버 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#29](../../mfc/reference/codesnippet/cpp/cmenu-class_9.cpp)]

##  <a name="loadmenuindirect"></a>  CMenu::LoadMenuIndirect

메모리의 메뉴 템플릿에서 리소스를 로드 하 고에 연결 된 `CMenu` 개체입니다.

```
BOOL LoadMenuIndirect(const void* lpMenuTemplate);
```

### <a name="parameters"></a>매개 변수

*lpMenuTemplate*<br/>
메뉴 템플릿을 가리키는 (단일 되 [MENUITEMTEMPLATEHEADER](/windows/desktop/api/winuser/ns-winuser-menuitemtemplateheader) 구조 및 하나 이상의 컬렉션 [MENUITEMTEMPLATE](/windows/desktop/api/winuser/ns-winuser-menuitemtemplate) 구조). 이러한 두 구조에 대 한 자세한 내용은 Windows SDK를 참조 하세요.

### <a name="return-value"></a>반환 값

메뉴 리소스를 성공적으로 로드 한 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

메뉴 서식 파일은 하나 이상의 컬렉션 뒤에 헤더 [MENUITEMTEMPLATE](/windows/desktop/api/winuser/ns-winuser-menuitemtemplate) 메뉴 항목 및 팝업 메뉴를 하나 이상 포함 될 수 있습니다 각 구조입니다.

버전 번호는 0 이어야 합니다.

`mtOption` 팝업 목록에서 마지막 항목 및 기본 목록의 마지막 항목에 대 한 플래그 MF_END를 포함 해야 합니다. 참조 된 `AppendMenu` 다른 플래그에 대 한 멤버 함수입니다. 합니다 `mtId` MF_POPUP이 지정 된 경우 MENUITEMTEMPLATE 구조에서 멤버를 생략 합니다 `mtOption`합니다.

MENUITEMTEMPLATE 구조에 충분 해야 합니다. 할당 된 공간 `mtString` null로 끝나는 문자열을 표시 된 메뉴 항목의 이름을 포함 합니다.

를 종료 하기 전에 응용 프로그램 메뉴 창에 할당 되지 않은 경우 메뉴를 사용 하 여 연결 된 시스템 리소스를 해제 해야 합니다. 응용 프로그램 메뉴를 호출 하 여 해제 합니다 [DestroyMenu](#destroymenu) 멤버 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#30](../../mfc/reference/codesnippet/cpp/cmenu-class_10.cpp)]

##  <a name="m_hmenu"></a>  CMenu::m_hMenu

에 연결 된 Windows 메뉴의 HMENU 핸들을 지정 합니다 `CMenu` 개체입니다.

```
HMENU m_hMenu;
```

### <a name="example"></a>예제

  예를 참조 하세요 [CMenu::LoadMenu](#loadmenu)합니다.

##  <a name="measureitem"></a>  CMenu::MeasureItem

소유자 그리기 스타일을 사용 하 여 메뉴를 만들 때 프레임 워크에서 호출 됩니다.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpMeasureItemStruct*<br/>
에 대 한 포인터를 `MEASUREITEMSTRUCT` 구조입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 기본적으로 아무 작업도 수행 하지. 이 멤버 함수를 재정의 하 고 입력을 `MEASUREITEMSTRUCT` 구조 메뉴의 차원의 Windows에 알림을 보내야 합니다.

참조 [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) 에 대 한 설명은 `MEASUREITEMSTRUCT` 구조입니다.

### <a name="example"></a>예제

MFC에서 다음 코드는 [CTRLTEST](../../overview/visual-cpp-samples.md) 샘플:

[!code-cpp[NVC_MFCWindowing#31](../../mfc/reference/codesnippet/cpp/cmenu-class_11.cpp)]

##  <a name="modifymenu"></a>  CMenu::ModifyMenu

지정 된 위치에 있는 기존 메뉴 항목을 변경 *찾기를*합니다.

```
BOOL ModifyMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem = 0,
    LPCTSTR lpszNewItem = NULL);

BOOL ModifyMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem,
    const CBitmap* pBmp);
```

### <a name="parameters"></a>매개 변수

*nPosition*<br/>
메뉴 항목을 변경할 수를 지정 합니다. 합니다 *nFlags* 매개 변수를 사용 하 여 해석할 수 있습니다 *찾기를* 다음과 같은 방법으로:

|nFlags|찾기 해석|
|------------|---------------------------------|
|MF_BYCOMMAND|매개 변수 제공 기존 메뉴 항목의 명령 ID를 지정 합니다. MF_BYCOMMAND 아니고 MF_BYPOSITION 설정 된 경우 이것이 기본값입니다.|
|MF_BYPOSITION|기존 메뉴 항목의 위치를 제공 하는 매개 변수는 지정 합니다. 위치 0의 첫 번째 항목이 표시 됩니다.|

*nFlags*<br/>
지정 하는 방법을 *찾기를* 해석 되 고 메뉴 항목에 대 한 변경 내용에 대 한 정보를 제공 합니다. 목록을 설정할 수 있는 플래그에 대 한 참조를 [AppendMenu](#appendmenu) 멤버 함수입니다.

*nIDNewItem*<br/>
수정 된 메뉴 항목의 명령 ID를 지정 합니다. 또는 *nFlags* MF_POPUP, 팝업 메뉴의 메뉴 핸들 (HMENU)로 설정 됩니다. 합니다 *nIDNewItem* 매개 변수는 (필요 하지 않게) *nFlags* MF_SEPARATOR로 설정 됩니다.

*lpszNewItem*<br/>
새 메뉴 항목의 콘텐츠를 지정합니다. 합니다 *nFlags* 매개 변수를 사용 하 여 해석할 수 있습니다 *lpszNewItem* 다음과 같은 방법으로:

|nFlags|LpszNewItem 해석|
|------------|-----------------------------------|
|MF_OWNERDRAW|응용 프로그램 메뉴 항목과 연결 된 추가 데이터를 유지 하는 데 사용할 수 있는 응용 프로그램에서 제공한 32 비트 값을 포함 합니다. 이 32 비트 값은 MF_MEASUREITEM 및 MF_DRAWITEM 처리할 때 응용 프로그램에 사용할 수 있습니다.|
|MF_STRING|또는 null로 끝나는 문자열에 대 한 긴 포인터를 포함 한 `CString`합니다.|
|MF_SEPARATOR|합니다 *lpszNewItem* (필요 없음) 매개 변수가 무시 됩니다.|

*pBmp*<br/>
가리키는 `CBitmap` 메뉴 항목으로 사용할 개체입니다.

### <a name="return-value"></a>반환 값

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

값을 설정 하 여 메뉴 항목의 새 상태를 지정 하는 응용 프로그램 *nFlags*합니다. 이 함수는 메뉴 항목과 연결 된 팝업 메뉴를 대체 하는 경우 이전 팝업 메뉴를 제거 하 고 팝업 메뉴에서 사용 하는 메모리를 해제 합니다.

때 *nIDNewItem* 팝업 메뉴 지정 삽입 되는 메뉴의 일부가 됩니다. 해당 메뉴 손상 된 경우에 삽입된 메뉴 소멸 됩니다. 삽입된 메뉴는에서 분리 해야는 `CMenu` 충돌을 피하기 위해 개체입니다.

(여부 창 표시 됨)는 창이 변경 될 때마다에 상주 하는 메뉴, 응용 프로그램을 호출 해야 `CWnd::DrawMenuBar`합니다. 기존 메뉴 항목의 특성을 변경 하려면 훨씬 빠르게 사용 되는 `CheckMenuItem` 및 `EnableMenuItem` 멤버 함수입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CMenu::InsertMenu](#insertmenu)합니다.

##  <a name="operator_hmenu"></a>  CMenu::operator HMENU

이 연산자의 핸들을 검색 하는 데는 `CMenu` 개체입니다.

```
operator HMENU() const;
```

### <a name="return-value"></a>반환 값

성공 하면의 핸들을 `CMenu` NULL이 고, 그렇지 않으면 개체.

### <a name="remarks"></a>설명

Windows Api를 직접 호출 하는 핸들을 사용할 수 있습니다.

##  <a name="operator_neq"></a>  CMenu::operator !=

이면 두 메뉴 다릅니다 논리적으로 결정 합니다.

```
BOOL operator!=(const CMenu& menu) const;
```

### <a name="parameters"></a>매개 변수

*menu*<br/>
`CMenu` 비교할 개체입니다.

### <a name="remarks"></a>설명

왼쪽 메뉴 개체를 오른쪽에 있는 메뉴 개체 같음 인지 테스트 합니다.

##  <a name="operator_eq_eq"></a>  CMenu::operator ==

두 개의 메뉴가 논리적으로 같은지 여부를 결정 합니다.

```
BOOL operator==(const CMenu& menu) const;
```

### <a name="parameters"></a>매개 변수

*menu*<br/>
`CMenu` 비교할 개체입니다.

### <a name="remarks"></a>설명

왼쪽 메뉴 개체와 같은지 테스트 (측면에서 HMENU 값) 오른쪽에 있는 메뉴 개체입니다.

##  <a name="removemenu"></a>  CMenu::RemoveMenu

메뉴에서 연결 된 팝업 메뉴를 사용 하 여 메뉴 항목을 삭제합니다.

```
BOOL RemoveMenu(
    UINT nPosition,
    UINT nFlags);
```

### <a name="parameters"></a>매개 변수

*nPosition*<br/>
제거할 메뉴 항목을 지정 합니다. 합니다 *nFlags* 매개 변수를 사용 하 여 해석할 수 있습니다 *찾기를* 다음과 같은 방법으로:

|nFlags|찾기 해석|
|------------|---------------------------------|
|MF_BYCOMMAND|매개 변수 제공 기존 메뉴 항목의 명령 ID를 지정 합니다. MF_BYCOMMAND 아니고 MF_BYPOSITION 설정 된 경우 이것이 기본값입니다.|
|MF_BYPOSITION|기존 메뉴 항목의 위치를 제공 하는 매개 변수는 지정 합니다. 위치 0의 첫 번째 항목이 표시 됩니다.|

*nFlags*<br/>
지정 하는 방법을 *찾기를* 해석 됩니다.

### <a name="return-value"></a>반환 값

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

메뉴를 다시 사용할 수 있도록 팝업 메뉴에 대 한 핸들은 삭제 되지 않습니다. 이 함수를 호출 하기 전에 응용 프로그램이 호출할 수는 `GetSubMenu` 팝업을 검색 하려면 멤버 함수 `CMenu` 재사용에 대 한 개체입니다.

(여부 창 표시 됨)는 창이 변경 될 때마다에 상주 하는 메뉴, 호출 하는 응용 프로그램 `CWnd::DrawMenuBar`합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CMenu::InsertMenu](#insertmenu)합니다.

##  <a name="setdefaultitem"></a>  CMenu::SetDefaultItem

지정된 된 메뉴의 기본 메뉴 항목을 설정합니다.

```
BOOL SetDefaultItem(
    UINT uItem,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>매개 변수

*uItem*<br/>
식별자 또는 새 기본 메뉴 항목 또는 기본 항목이 1의 위치입니다. 이 매개 변수의 의미 값에 따라 달라 집니다 *fByPos*합니다.

*fByPos*<br/>
의미를 지정 하는 값 *uItem*합니다. 이 매개 변수가 FALSE 이면 *uItem* 메뉴 항목 식별자입니다. 그렇지 않을 경우 메뉴 항목 위치입니다.

### <a name="return-value"></a>반환 값

함수가 성공 하면 반환 값은 0이 아닌 값입니다. 함수가 실패하면 반환 값은 0입니다. 확장 정보를 가져오려면 오류, Win32 함수를 사용 하 여 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)Windows SDK에 설명 된 대로 합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 함수의 동작을 구현 [SetMenuDefaultItem](/windows/desktop/api/winuser/nf-winuser-setmenudefaultitem)Windows SDK에 설명 된 대로 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CMenu::InsertMenu](#insertmenu)합니다.

##  <a name="setmenucontexthelpid"></a>  CMenu::SetMenuContextHelpId

상황에 맞는 도움말 ID를 사용 하 여 연결 `CMenu`합니다.

```
BOOL SetMenuContextHelpId(DWORD dwContextHelpId);
```

### <a name="parameters"></a>매개 변수

*dwContextHelpId*<br/>
상황에 맞는 도움말 ID와 연결할 `CMenu`합니다.

### <a name="return-value"></a>반환 값

성공 하면 0이 아닌 값 그렇지 않은 0

### <a name="remarks"></a>설명

이 식별자를 공유 하는 메뉴에서 모든 항목-도움말 컨텍스트 식별자를 개별 메뉴 항목에 연결할 수 없는 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CMenu::InsertMenu](#insertmenu)합니다.

##  <a name="setmenuinfo"></a>  CMenu::SetMenuInfo

메뉴에 대 한 정보를 설정합니다.

```
BOOL SetMenuInfo(LPCMENUINFO lpcmi);
```

### <a name="parameters"></a>매개 변수

*lpcmi*<br/>
에 대 한 포인터를 [MENUINFO](/windows/desktop/api/winuser/ns-winuser-tagmenuinfo) 메뉴에 대 한 정보를 포함 하는 구조체.

### <a name="return-value"></a>반환 값

함수가 성공할 경우 반환 값은 0이 아닌; 그렇지 않은 경우 반환 값은 0입니다.

### <a name="remarks"></a>설명

메뉴에 대 한 특정 정보를 설정 하려면이 함수를 호출 합니다.

##  <a name="setmenuitembitmaps"></a>  CMenu::SetMenuItemBitmaps

메뉴 항목을 사용 하 여 지정 된 비트맵에 연결합니다.

```
BOOL SetMenuItemBitmaps(
    UINT nPosition,
    UINT nFlags,
    const CBitmap* pBmpUnchecked,
    const CBitmap* pBmpChecked);
```

### <a name="parameters"></a>매개 변수

*nPosition*<br/>
메뉴 항목을 변경할 수를 지정 합니다. 합니다 *nFlags* 매개 변수를 사용 하 여 해석할 수 있습니다 *찾기를* 다음과 같은 방법으로:

|nFlags|찾기 해석|
|------------|---------------------------------|
|MF_BYCOMMAND|매개 변수 제공 기존 메뉴 항목의 명령 ID를 지정 합니다. MF_BYCOMMAND 아니고 MF_BYPOSITION 설정 된 경우 이것이 기본값입니다.|
|MF_BYPOSITION|기존 메뉴 항목의 위치를 제공 하는 매개 변수는 지정 합니다. 위치 0의 첫 번째 항목이 표시 됩니다.|

*nFlags*<br/>
지정 하는 방법을 *찾기를* 해석 됩니다.

*pBmpUnchecked*<br/>
확인 하지 않습니다는 메뉴 항목에 대해 사용할 비트맵을 지정 합니다.

*pBmpChecked*<br/>
확인란이 선택 된 메뉴 항목에 사용할 비트맵을 지정 합니다.

### <a name="return-value"></a>반환 값

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

Checked 또는 unchecked 메뉴 항목 인지 Windows 메뉴 항목 옆에 있는 적절 한 비트맵을 표시 합니다.

이면 *pBmpUnchecked* 하거나 *pBmpChecked* 가 NULL 이면 Windows 해당 특성에 대 한 메뉴 항목 옆에 있는 아무 것도 표시 합니다. 매개 변수가 모두 NULL 인 경우 Windows는 항목이 선택 되 고 항목을 선택 하지 않은 경우 확인 표시를 제거 하는 경우 기본 확인 표시를 사용 합니다.

메뉴 소멸 될 때 이러한 비트맵 소멸 되지 않습니다. 응용 프로그램을 파기 해야 합니다.

Windows `GetMenuCheckMarkDimensions` 함수 메뉴 항목에 사용 되는 기본 확인란의 크기를 검색 합니다. 이 함수를 사용 하 여 제공 된 비트맵에 대 한 적절 한 크기를 확인 하려면 이러한 값을 사용 하는 응용 프로그램입니다. 크기를 가져오고에 비트맵을 만들 설정 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#32](../../mfc/reference/codesnippet/cpp/cmenu-class_12.cpp)]

[!code-cpp[NVC_MFCWindowing#33](../../mfc/reference/codesnippet/cpp/cmenu-class_13.cpp)]

##  <a name="setmenuiteminfo"></a>  CMenu::SetMenuItemInfo

메뉴 항목에 대 한 정보를 변경합니다.

```
BOOL SetMenuItemInfo(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>매개 변수

*uItem*<br/>
에 대 한 설명을 참조 하세요 *uItem* 에 [SetMenuItemInfo](/windows/desktop/api/winuser/nf-winuser-setmenuiteminfoa) Windows SDK에 있습니다.

*lpMenuItemInfo*<br/>
에 대 한 설명을 참조 하세요 *lpmii* 에서 `SetMenuItemInfo` Windows SDK에 있습니다.

*fByPos*<br/>
에 대 한 설명을 참조 하세요 *fByPosition* 에서 `SetMenuItemInfo` Windows SDK에 있습니다.

### <a name="remarks"></a>설명

이 함수를 래핑하고 [SetMenuItemInfo](/windows/desktop/api/winuser/nf-winuser-setmenuiteminfoa)Windows SDK에서 설명 합니다.

##  <a name="trackpopupmenu"></a>  CMenu::TrackPopupMenu

지정된 된 위치에 부동 팝업 메뉴를 표시 하 고 팝업 메뉴에서 항목의 선택 집합을 추적 합니다.

```
BOOL TrackPopupMenu(
    UINT nFlags,
    int x,
    int y,
    CWnd* pWnd,
    LPCRECT lpRect = 0);
```

### <a name="parameters"></a>매개 변수

*nFlags*<br/>
화면 위치 및 마우스 위치 플래그를 지정합니다. 참조 [TrackPopupMenu](/windows/desktop/api/winuser/nf-winuser-trackpopupmenu) 사용 가능한 플래그의 목록은 합니다.

*x*<br/>
팝업 메뉴의 가로 화면 좌표 위치를 지정합니다. 값에 따라 합니다 *nFlags* 매개 변수를 왼쪽 맞춤, 오른쪽 맞춤 또는 가운데 맞춤이 위치를 기준으로 메뉴 될 수 있습니다.

*y*<br/>
화면의 맨 위에 있는 메뉴의 화면 좌표에서 세로 위치를 지정합니다.

*pWnd*<br/>
팝업 메뉴를 소유 하는 창을 식별 합니다. 이 매개 변수는 TPM_NONOTIFY 플래그를 지정 하는 경우에 NULL 일 수 없습니다. 이 창 메뉴에서 모든 WM_COMMAND 메시지를 받습니다. 버전 3.1 이상 Windows에서 창 메시지를 수신 하지 WM_COMMAND까지 `TrackPopupMenu` 반환 합니다. 창 Windows 3.0에서 전에 WM_COMMAND 메시지를 받는 `TrackPopupMenu` 반환 합니다.

*lpRect*<br/>
무시됩니다.

### <a name="return-value"></a>반환 값

이 메서드 호출의 결과 반환 [TrackPopupMenu](/windows/desktop/api/winuser/nf-winuser-trackpopupmenu) Windows SDK에 있습니다.

### <a name="remarks"></a>설명

부동 팝업 메뉴는 화면에서 아무 곳 이나 나타날 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#34](../../mfc/reference/codesnippet/cpp/cmenu-class_14.cpp)]

##  <a name="trackpopupmenuex"></a>  CMenu::TrackPopupMenuEx

지정된 된 위치에 부동 팝업 메뉴를 표시 하 고 팝업 메뉴에서 항목의 선택 집합을 추적 합니다.

```
BOOL TrackPopupMenuEx(
    UINT fuFlags,
    int x,
    int y,
    CWnd* pWnd,
    LPTPMPARAMS lptpm);
```

### <a name="parameters"></a>매개 변수

*fuFlags*<br/>
확장 된 메뉴에 대 한 다양 한 함수를 지정합니다. 모든 값의 목록 및 해당 의미가 [TrackPopupMenuEx](/windows/desktop/api/winuser/nf-winuser-trackpopupmenuex)합니다.

*x*<br/>
팝업 메뉴의 가로 화면 좌표 위치를 지정합니다.

*y*<br/>
화면의 맨 위에 있는 메뉴의 화면 좌표에서 세로 위치를 지정합니다.

*pWnd*<br/>
팝업 메뉴를 소유 하 고 만든된 메뉴에서 메시지를 받는 창에 대 한 포인터입니다. 이 창은 현재 응용 프로그램에서 모든 창 수 있지만 NULL 일 수 없습니다. TPM_NONOTIFY를 지정 하는 경우는 *fuFlags* 매개 변수, 함수를 모든 메시지를 보내지 않습니다 *pWnd*합니다. 함수를 가리키는 창에 대 한 반환 해야 합니다 *pWnd* WM_COMMAND 메시지를 받을 수 있습니다.

*lptpm*<br/>
에 대 한 포인터를 [TPMPARAMS](/windows/desktop/api/winuser/ns-winuser-tagtpmparams) 구조 메뉴 화면의 영역을 지정 하는 겹치지 않아야 합니다. 이 매개 변수는 NULL 일 수 있습니다.

### <a name="return-value"></a>반환 값

TPM_RETURNCMD를 지정 하는 경우는 *fuFlags* 매개 변수, 반환 값은 사용자가 선택한 항목의 메뉴 항목 식별자입니다. 사용자 메뉴를 선택 하지 않고 취소 또는 오류가 발생 한 경우 반환 값은 0입니다.

TPM_RETURNCMD 지정 하지 않으면 경우는 *fuFlags* 매개 변수, 반환 값은 함수가 성공 하면 0이 아닌 값 및 0 실패 한 경우. 확장 오류 정보를 가져오기, 호출 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)합니다.

### <a name="remarks"></a>설명

부동 팝업 메뉴는 화면에서 아무 곳 이나 나타날 수 있습니다. 팝업 메뉴를 만들 때 오류를 처리 하는 방법은 참조 하세요 [TrackPopupMenuEx](/windows/desktop/api/winuser/nf-winuser-trackpopupmenuex)합니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 CTRLTEST](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 DYNAMENU](../../overview/visual-cpp-samples.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)
