---
title: CListBox 클래스
ms.date: 11/04/2016
f1_keywords:
- CListBox
- AFXWIN/CListBox
- AFXWIN/CListBox::CListBox
- AFXWIN/CListBox::AddString
- AFXWIN/CListBox::CharToItem
- AFXWIN/CListBox::CompareItem
- AFXWIN/CListBox::Create
- AFXWIN/CListBox::DeleteItem
- AFXWIN/CListBox::DeleteString
- AFXWIN/CListBox::Dir
- AFXWIN/CListBox::DrawItem
- AFXWIN/CListBox::FindString
- AFXWIN/CListBox::FindStringExact
- AFXWIN/CListBox::GetAnchorIndex
- AFXWIN/CListBox::GetCaretIndex
- AFXWIN/CListBox::GetCount
- AFXWIN/CListBox::GetCurSel
- AFXWIN/CListBox::GetHorizontalExtent
- AFXWIN/CListBox::GetItemData
- AFXWIN/CListBox::GetItemDataPtr
- AFXWIN/CListBox::GetItemHeight
- AFXWIN/CListBox::GetItemRect
- AFXWIN/CListBox::GetListBoxInfo
- AFXWIN/CListBox::GetLocale
- AFXWIN/CListBox::GetSel
- AFXWIN/CListBox::GetSelCount
- AFXWIN/CListBox::GetSelItems
- AFXWIN/CListBox::GetText
- AFXWIN/CListBox::GetTextLen
- AFXWIN/CListBox::GetTopIndex
- AFXWIN/CListBox::InitStorage
- AFXWIN/CListBox::InsertString
- AFXWIN/CListBox::ItemFromPoint
- AFXWIN/CListBox::MeasureItem
- AFXWIN/CListBox::ResetContent
- AFXWIN/CListBox::SelectString
- AFXWIN/CListBox::SelItemRange
- AFXWIN/CListBox::SetAnchorIndex
- AFXWIN/CListBox::SetCaretIndex
- AFXWIN/CListBox::SetColumnWidth
- AFXWIN/CListBox::SetCurSel
- AFXWIN/CListBox::SetHorizontalExtent
- AFXWIN/CListBox::SetItemData
- AFXWIN/CListBox::SetItemDataPtr
- AFXWIN/CListBox::SetItemHeight
- AFXWIN/CListBox::SetLocale
- AFXWIN/CListBox::SetSel
- AFXWIN/CListBox::SetTabStops
- AFXWIN/CListBox::SetTopIndex
- AFXWIN/CListBox::VKeyToItem
helpviewer_keywords:
- CListBox [MFC], CListBox
- CListBox [MFC], AddString
- CListBox [MFC], CharToItem
- CListBox [MFC], CompareItem
- CListBox [MFC], Create
- CListBox [MFC], DeleteItem
- CListBox [MFC], DeleteString
- CListBox [MFC], Dir
- CListBox [MFC], DrawItem
- CListBox [MFC], FindString
- CListBox [MFC], FindStringExact
- CListBox [MFC], GetAnchorIndex
- CListBox [MFC], GetCaretIndex
- CListBox [MFC], GetCount
- CListBox [MFC], GetCurSel
- CListBox [MFC], GetHorizontalExtent
- CListBox [MFC], GetItemData
- CListBox [MFC], GetItemDataPtr
- CListBox [MFC], GetItemHeight
- CListBox [MFC], GetItemRect
- CListBox [MFC], GetListBoxInfo
- CListBox [MFC], GetLocale
- CListBox [MFC], GetSel
- CListBox [MFC], GetSelCount
- CListBox [MFC], GetSelItems
- CListBox [MFC], GetText
- CListBox [MFC], GetTextLen
- CListBox [MFC], GetTopIndex
- CListBox [MFC], InitStorage
- CListBox [MFC], InsertString
- CListBox [MFC], ItemFromPoint
- CListBox [MFC], MeasureItem
- CListBox [MFC], ResetContent
- CListBox [MFC], SelectString
- CListBox [MFC], SelItemRange
- CListBox [MFC], SetAnchorIndex
- CListBox [MFC], SetCaretIndex
- CListBox [MFC], SetColumnWidth
- CListBox [MFC], SetCurSel
- CListBox [MFC], SetHorizontalExtent
- CListBox [MFC], SetItemData
- CListBox [MFC], SetItemDataPtr
- CListBox [MFC], SetItemHeight
- CListBox [MFC], SetLocale
- CListBox [MFC], SetSel
- CListBox [MFC], SetTabStops
- CListBox [MFC], SetTopIndex
- CListBox [MFC], VKeyToItem
ms.assetid: 7ba3c699-c286-4cd9-9066-532c41ec05d1
ms.openlocfilehash: b448f725bac68c2b67dc44d660c664c075aa86da
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62225271"
---
# <a name="clistbox-class"></a>CListBox 클래스

Windows 목록 상자의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CListBox : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CListBox::CListBox](#clistbox)|`CListBox` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CListBox::AddString](#addstring)|목록 상자에 문자열을 추가 합니다.|
|[CListBox::CharToItem](#chartoitem)|사용자 지정 WM_CHAR 문자열 않은 소유자 그리기 목록 상자에 대 한 처리를 제공 하기 위해 재정의 합니다.|
|[CListBox::CompareItem](#compareitem)|정렬 된 소유자 그리기 목록 상자에서 새 항목의 위치를 확인 하기 위해 프레임 워크에서 호출 됩니다.|
|[CListBox::Create](#create)|Windows 목록 상자를 만들고 연결 하는 `CListBox` 개체입니다.|
|[CListBox::DeleteItem](#deleteitem)|사용자는 소유자 그리기 목록 상자에서 항목을 삭제 하는 경우 프레임 워크에서 호출 됩니다.|
|[CListBox::DeleteString](#deletestring)|목록 상자에서 문자열을 삭제합니다.|
|[CListBox::Dir](#dir)|목록 상자에 파일 이름, 드라이브 또는 현재 디렉터리에서 둘 다를 추가합니다.|
|[CListBox::DrawItem](#drawitem)|소유자 그리기 목록 상자 변경 시각적 측면이 때 프레임 워크에서 호출 됩니다.|
|[CListBox::FindString](#findstring)|목록 상자에 문자열을 검색 합니다.|
|[CListBox::FindStringExact](#findstringexact)|지정 된 문자열과 일치 하는 첫 번째 목록 상자 문자열을 찾습니다.|
|[CListBox::GetAnchorIndex](#getanchorindex)|목록 상자에서 현재 앵커 항목의 0부터 시작 인덱스를 가져옵니다.|
|[CListBox::GetCaretIndex](#getcaretindex)|포커스 영역을 다중 선택 목록 상자에 있는 항목의 인덱스를 결정 합니다.|
|[CListBox::GetCount](#getcount)|목록 상자에서 문자열의 수를 반환합니다.|
|[CListBox::GetCurSel](#getcursel)|목록 상자에서 현재 선택된 된 문자열의 0부터 시작 인덱스를 반환합니다.|
|[CListBox::GetHorizontalExtent](#gethorizontalextent)|목록 상자를 가로로 스크롤할 수는 픽셀에서 너비를 반환 합니다.|
|[CListBox::GetItemData](#getitemdata)|목록 상자 항목과 연결 된 32 비트 값을 반환 합니다.|
|[CListBox::GetItemDataPtr](#getitemdataptr)|목록 상자 항목에 대 한 포인터를 반환합니다.|
|[CListBox::GetItemHeight](#getitemheight)|목록 상자의 항목 높이 결정합니다.|
|[CListBox::GetItemRect](#getitemrect)|현재 표시 되는 목록 상자 항목의 경계 사각형을 반환 합니다.|
|[CListBox::GetListBoxInfo](#getlistboxinfo)|열에 따라 항목의 수를 검색 합니다.|
|[CListBox::GetLocale](#getlocale)|목록 상자에 대 한 로캘 식별자를 검색합니다.|
|[CListBox::GetSel](#getsel)|목록 상자 항목의 선택 상태를 반환합니다.|
|[CListBox::GetSelCount](#getselcount)|다중 선택 목록 상자에서 현재 선택 된 문자열의 수를 반환 합니다.|
|[CListBox::GetSelItems](#getselitems)|목록 상자에서 현재 선택 된 문자열의 인덱스를 반환 합니다.|
|[CListBox::GetText](#gettext)|목록 상자 항목을 버퍼에 복사합니다.|
|[CListBox::GetTextLen](#gettextlen)|목록 상자 항목의 바이트 길이 반환합니다.|
|[CListBox::GetTopIndex](#gettopindex)|목록 상자에서 첫 번째 표시 문자열의 인덱스를 반환합니다.|
|[CListBox::InitStorage](#initstorage)|목록 상자 항목 및 문자열에 대 한 메모리 블록을 미리 할당합니다.|
|[CListBox::InsertString](#insertstring)|목록 상자에서 특정 위치에 문자열을 삽입 합니다.|
|[CListBox::ItemFromPoint](#itemfrompoint)|점 가장 가까운 목록 상자 항목의 인덱스를 반환합니다.|
|[CListBox::MeasureItem](#measureitem)|목록 상자 크기를 결정 하는 소유자 그리기 목록 상자를 만들 때 프레임 워크에서 호출 됩니다.|
|[CListBox::ResetContent](#resetcontent)|목록 상자에서 항목을 모두 지웁니다.|
|[CListBox::SelectString](#selectstring)|검색 하 고 단일 선택 목록 상자에 문자열을 선택 합니다.|
|[CListBox::SelItemRange](#selitemrange)|다중 선택 목록 상자에서 문자열의 범위를 선택 취소 하거나 선택 합니다.|
|[CListBox::SetAnchorIndex](#setanchorindex)|확장된을 선택 하려면 다중 선택 목록 상자에 앵커를 설정 합니다.|
|[CListBox::SetCaretIndex](#setcaretindex)|다중 선택 목록 상자에 지정된 된 인덱스의 항목에 포커스를 설정합니다.|
|[CListBox::SetColumnWidth](#setcolumnwidth)|여러 열 목록 상자의 열 너비를 설정합니다.|
|[CListBox::SetCurSel](#setcursel)|목록 상자 문자열을 선택합니다.|
|[CListBox::SetHorizontalExtent](#sethorizontalextent)|목록 상자를 가로로 스크롤할 수는 픽셀에서 너비를 설정 합니다.|
|[CListBox::SetItemData](#setitemdata)|목록 상자 항목과 연결 된 32 비트 값을 설정 합니다.|
|[CListBox::SetItemDataPtr](#setitemdataptr)|목록 상자 항목에 대 한 포인터를 설정합니다.|
|[CListBox::SetItemHeight](#setitemheight)|목록 상자에서 항목의 높이 설정합니다.|
|[CListBox::SetLocale](#setlocale)|목록 상자에 대 한 로캘 식별자를 설정합니다.|
|[CListBox::SetSel](#setsel)|다중 선택 목록 상자에서 목록 상자 항목을 선택 취소 하거나 선택 합니다.|
|[CListBox::SetTabStops](#settabstops)|목록 상자에 탭 정지 위치를 설정 합니다.|
|[CListBox::SetTopIndex](#settopindex)|목록 상자에서 첫 번째 표시 문자열의 0부터 시작 인덱스를 설정합니다.|
|[CListBox::VKeyToItem](#vkeytoitem)|사용자 지정 WM_KEYDOWN LBS_WANTKEYBOARDINPUT 스타일 집합을 사용 하 여 목록 상자에 대 한 처리를 제공 하기 위해 재정의 합니다.|

## <a name="remarks"></a>설명

목록 상자에 사용자 보고 선택할 수 있는 파일 이름과 같은 항목의 목록을 표시 합니다.

단일 선택 목록 상자에 사용자 항목을 하나만 선택할 수 있습니다. 다중 선택 목록 상자에 항목의 범위를 선택할 수 있습니다. 사용자가 항목을 선택 하면 강조 표시 하 고 목록 상자 부모 창에 알림 메시지를 보냅니다.

목록 상자 대화 상자 템플릿에서 또는 코드에서 직접 만들 수 있습니다. 만들려면 직접 생성 합니다 `CListBox` 개체를 만든 다음 호출 합니다 [만들기](#create) Windows 목록 상자 컨트롤을 만들고 연결 하는 멤버 함수는 `CListBox` 개체. 대화 상자 템플릿에서 목록 상자를 사용 하려면 대화 상자 클래스에서 목록 상자 변수를 선언 다음 사용 하 여 `DDX_Control` 프로그램 대화 상자 클래스의 `DoDataExchange` 컨트롤 멤버 변수를 연결 하는 함수입니다. (이렇게를 자동으로 대화 상자 클래스에는 제어 변수를 추가 합니다.)

생성 1 단계 프로세스에서 파생 된 클래스 수 `CListBox`입니다. 파생된 클래스 및 호출에 대 한 생성자 작성 `Create` 에서 생성자 내에서.

목록 상자에서 해당 부모에 보냅니다 Windows 알림 메시지를 처리 하려는 경우 (일반적으로 클래스에서 파생 [CDialog](../../mfc/reference/cdialog-class.md)), 각 메시지에 대 한 부모 클래스에는 메시지 맵 항목 및 메시지 처리기 멤버 함수를 추가 합니다.

각 메시지 맵 항목은 다음 형식을 사용 합니다.

`ON_Notification( id, memberFxn )`

여기서 `id` 알림을 전송 하는 목록 상자 컨트롤의 자식 창 ID를 지정 하 고 `memberFxn` 알림을 처리 하는 것이 기록한 부모 멤버 함수의 이름입니다.

부모의 함수 프로토타입에 다음과 같습니다.

`afx_msg void memberFxn( );`

다음은 잠재적인 메시지 맵 항목 및 부모로 전송 되는 있는 경우에 대 한 설명을의 목록.

- ON_LBN_DBLCLK 사용자가 목록 상자에 문자열로 두 번 클릭 합니다. 에 있는 목록 상자를는 [LBS_NOTIFY](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 이 알림 메시지를 보낼 스타일입니다.

- 목록 상자 ON_LBN_ERRSPACE 요청에 맞게 충분 한 메모리를 할당할 수 없습니다.

- 목록 상자 ON_LBN_KILLFOCUS 입력된 포커스를 잃을 합니다.

- ON_LBN_SELCANCEL 현재 목록 상자 선택이 취소 됩니다. 이 메시지는 목록 상자에 LBS_NOTIFY 스타일이 하는 경우에 전송 됩니다.

- 목록 상자에서 선택한 ON_LBN_SELCHANGE 변경 되었습니다. 선택 하 여 변경 되 면이 알림은 전송 되지 않습니다 합니다 [CListBox::SetCurSel](#setcursel) 멤버 함수입니다. 이 알림은 LBS_NOTIFY 스타일이 있는 목록 상자에만 적용 됩니다. LBN_SELCHANGE 알림 메시지가 보내집니다 다중 선택 목록 상자에 대 한 화살표 키를 누를 때마다 선택을 변경 되지 않는 경우에 합니다.

- ON_LBN_SETFOCUS 목록 상자에 입력된 포커스를 받고 있습니다.

- 모든 액세스 권한을 제공 된 소유자 그리기 목록 상자를 ON_WM_CHARTOITEM WM_CHAR 메시지를 받습니다.

- LBS_WANTKEYBOARDINPUT 스타일 ON_WM_VKEYTOITEM는 목록 상자 WM_KEYDOWN 메시지를 받습니다.

만드는 경우는 `CListBox` (대화 상자 리소스의 경우)를 통해 대화 상자 내에서 개체를 `CListBox` 개체에는 사용자가 대화 상자를 닫으면 자동으로 제거 됩니다.

만드는 경우는 `CListBox` 개체 창 내에서 삭제 해야 합니다 `CListBox` 개체입니다. 만드는 경우는 `CListBox` 개체 스택에 자동으로 제거 됩니다. 만드는 경우는 `CListBox` 를 사용 하 여 힙에 있는 개체에는 **새** 를 호출 해야 함수를 **삭제** 개체에서 사용자가 부모 창의 닫을 때 삭제를 합니다.

메모리를 할당 하는 경우는 `CListBox` 개체를 재정의 `CListBox` 소멸자는 할당을 삭제 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CListBox`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="addstring"></a>  CListBox::AddString

목록 상자에 문자열을 추가 합니다.

```
int AddString(LPCTSTR lpszItem);
```

### <a name="parameters"></a>매개 변수

*lpszItem*<br/>
추가 되는 null로 끝나는 문자열을 가리킵니다.

### <a name="return-value"></a>반환 값

목록 상자에서 문자열에 0부터 시작 하는 인덱스입니다. 오류가 발생 하는 경우 반환 값은 LB_ERR 반환 값 LB_ERRSPACE 경우 새 문자열을 저장 하는 사용 가능한 공간이 부족 합니다.

### <a name="remarks"></a>설명

목록 상자를 사용 하 여 만들지 않은 경우는 [LBS_SORT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일 문자열 목록의 끝에 추가 됩니다. 그렇지 않으면 문자열 목록에 삽입 됩니다 하 고 목록이 정렬 됩니다. LBS_SORT 스타일을 사용 하 여 목록 상자를 만든 경우 아닌 합니다 [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일 프레임 워크를 기준으로 정렬에 대 한 하나 이상의 호출을 `CompareItem` 멤버 함수입니다.

사용 하 여 [InsertString](#insertstring) 목록 상자 내의 특정 위치에 문자열을 삽입 하도록 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#3](../../mfc/codesnippet/cpp/clistbox-class_1.cpp)]

##  <a name="chartoitem"></a>  CListBox::CharToItem

목록 상자의 부모 창 목록 상자에서 WM_CHARTOITEM 메시지를 받을 때 프레임 워크에서 호출 됩니다.

```
virtual int CharToItem(
    UINT nKey,
    UINT nIndex);
```

### <a name="parameters"></a>매개 변수

*nKey*<br/>
사용자가 입력 한 문자의 ANSI 코드입니다.

*nIndex*<br/>
목록 상자 캐럿의 현재 위치입니다.

### <a name="return-value"></a>반환 값

반환-1 또는 2 추가 작업이 없으므로 또는 음수가 아닌 숫자 키 입력에 대 한 기본 작업을 수행 하는 목록 상자 항목의 인덱스를 지정 합니다. 기본 구현에서는-1이 반환 됩니다.

### <a name="remarks"></a>설명

WM_CHAR 메시지를 받으면 하지만 목록 상자는 이러한 조건을 모두 충족 하는 경우에 WM_CHARTOITEM 메시지 목록 상자로 전송 됩니다.

- 소유자 그리기 목록 상자가입니다.

- 없는 합니다 [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일 집합을 지정 합니다.

- 에 하나 이상의 항목이 있습니다.

호출 하지 말아야이 함수가 직접. 키보드 메시지의 고유한 사용자 지정 처리를 제공 하려면이 함수를 재정의 합니다.

재정의에서 수행한 작업 프레임 워크에 알립니다 값을 반환 해야 합니다. 반환 값-1 또는 2 나타냅니다 항목을 선택 하는 모든 측면을 처리 하는 목록 상자에서 추가 작업이 없으므로 필요 합니다. -반환 하기 전에 1-2, 있습니다 수 선택을 설정 또는 캐럿 또는 둘 다를 이동 합니다. 선택 영역을 설정 하려면 [SetCurSel](#setcursel) 하거나 [SetSel](#setsel)합니다. 캐럿을 이동 하려면 사용 하 여 [SetCaretIndex](#setcaretindex)합니다.

반환 값 0 이상인 목록 상자에서 항목의 인덱스를 지정 하 고 목록 상자에서 지정된 된 항목 키에 대 한 기본 작업을 수행 해야 나타냅니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#4](../../mfc/codesnippet/cpp/clistbox-class_2.cpp)]

##  <a name="clistbox"></a>  CListBox::CListBox

`CListBox` 개체를 생성합니다.

```
CListBox();
```

### <a name="remarks"></a>설명

생성 된 `CListBox` 두 단계에서 개체입니다. 먼저 생성자를 호출 `ClistBox` 호출 `Create`, Windows 목록 상자를 초기화 하 고 연결 하는 `CListBox`합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#1](../../mfc/codesnippet/cpp/clistbox-class_3.cpp)]

##  <a name="compareitem"></a>  CListBox::CompareItem

정렬 된 소유자 그리기 목록 상자에서 새 항목의 상대 위치를 확인 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpCompareItemStruct*<br/>
에 대 한 긴 포인터는 `COMPAREITEMSTRUCT` 구조입니다.

### <a name="return-value"></a>반환 값

에 설명 된 두 항목의 상대 위치를 나타내는 합니다 [COMPAREITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagcompareitemstruct) 구조입니다. 다음 값 중 하나일 수 있습니다.

|값|의미|
|-----------|-------------|
|-1|항목 1 항목 2 앞에 정렬 합니다.|
|0|항목 1 및 2 항목 동일를 정렬 합니다.|
|1|항목 1 항목 2 뒤에 정렬 합니다.|

참조 [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) 에 대 한 설명은 `COMPAREITEMSTRUCT` 구조입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 기본적으로 아무 작업도 수행 하지. LBS_SORT 스타일을 사용 하 여 소유자 그리기 목록 상자를 만든 경우 목록 상자에 추가 된 새 항목 정렬에 프레임 워크를 지원 하기 위해이 멤버 함수를 재정의 해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#5](../../mfc/codesnippet/cpp/clistbox-class_4.cpp)]

##  <a name="create"></a>  CListBox::Create

Windows 목록 상자를 만들고 연결 하는 `CListBox` 개체입니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
목록 상자의 스타일을 지정합니다. 어떤 조합도 적용할 [목록 상자 스타일](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 상자로 합니다.

*rect*<br/>
목록 상자 크기와 위치를 지정합니다. 일 수를 `CRect` 개체 또는 `RECT` 구조입니다.

*pParentWnd*<br/>
목록 상자의 부모 창 (일반적으로 `CDialog` 개체). NULL이 아니어야 합니다.

*nID*<br/>
목록 상자 컨트롤 ID를 지정 합니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

생성 된 `CListBox` 두 단계에서 개체입니다. 먼저 생성자를 호출 하 고 호출 하 `Create`, Windows 목록 상자를 초기화 하며에 연결 된 `CListBox` 개체입니다.

때 `Create` 보냅니다 Windows를 실행 합니다 [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate)를 [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), 및 [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) 목록 상자 컨트롤에 대 한 메시지입니다.

기본적으로 이러한 메시지의 처리를 [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate)합니다 [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), 및 [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) 멤버 함수 에 `CWnd` 기본 클래스입니다. 기본 메시지 처리를 확장 하려면에서 클래스를 파생 `CListBox`메시지 맵을 새 클래스를 추가 하 고 이전 메시지 처리기 멤버 함수를 재정의 합니다. 재정의 `OnCreate`, 예를 들어, 새 클래스에 대 한 필요한 초기화를 수행 하도록 합니다.

다음 적용 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 목록 상자 컨트롤입니다.

- WS_CHILD 항상

- WS_VISIBLE 일반적으로

- WS_DISABLED 거의

- WS_VSCROLL에 세로 스크롤 막대를 추가 합니다.

- WS_HSCROLL에 가로 스크롤 막대를 추가 합니다.

- 그룹 컨트롤에 WS_GROUP

- WS_TABSTOP에이 컨트롤에 탭 허용

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#2](../../mfc/codesnippet/cpp/clistbox-class_5.cpp)]

##  <a name="deleteitem"></a>  CListBox::DeleteItem

사용자는 소유자 그리기에서 항목을 삭제 하는 경우 프레임 워크에서 호출 `CListBox` 개체 또는 목록 상자를 제거 합니다.

```
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpDeleteItemStruct*<br/>
Windows에 대 한 긴 포인터 [DELETEITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdeleteitemstruct) 삭제 된 항목에 대 한 정보를 포함 하는 구조입니다.

### <a name="remarks"></a>설명

이 함수의 기본 구현은 아무 작업도 수행하지 않습니다. 필요에 따라 소유자 그리기 목록 상자를 다시 그리도록 하려면이 함수를 재정의 합니다.

참조 [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) 에 대 한 설명은 `DELETEITEMSTRUCT` 구조입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#6](../../mfc/codesnippet/cpp/clistbox-class_6.cpp)]

##  <a name="deletestring"></a>  CListBox::DeleteString

위치에 항목을 삭제 *nIndex* 목록 상자에서.

```
int DeleteString(UINT nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
삭제 된 문자열의 0부터 시작 인덱스를 지정 합니다.

### <a name="return-value"></a>반환 값

목록에 남아 있는 문자열의 수입니다. 하는 경우 반환 값은 LB_ERR *nIndex* 목록의 항목 수보다 큰 인덱스를 지정 합니다.

### <a name="remarks"></a>설명

다음 모든 항목 *nIndex* 이제 한 단계 아래로 이동 합니다. 예를 들어, 두 항목을 포함 하는 목록 상자에서 첫 번째 항목을 삭제 하면 나머지 항목을 이제 첫 번째 위치에서 합니다. *nIndex*= 첫 번째 위치에서 항목의 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#7](../../mfc/codesnippet/cpp/clistbox-class_7.cpp)]

##  <a name="dir"></a>  CListBox::Dir

파일 이름, 드라이브 또는 목록 상자에 둘 다의 목록을 추가합니다.

```
int Dir(
    UINT attr,
    LPCTSTR lpszWildCard);
```

### <a name="parameters"></a>매개 변수

*attr*<br/>
조합일 수 있습니다 합니다 **enum** 에 설명 된 값 `CFile::GetStatu` [s](../../mfc/reference/cfile-class.md#getstatus), 다음 값을 조합:

|값|의미|
|-----------|-------------|
|0x0000|파일에서 읽거나 쓸 수 수 있습니다.|
|0x0001|파일에서 읽을 수는 있지만 쓸 수 없습니다.|
|0x0002|숨겨진 파일과 디렉터리 목록에 나타나지 않습니다.|
|0x0004|파일은 시스템 파일이입니다.|
|0x0010|지정 된 이름을 *lpszWildCard* 디렉터리를 지정 합니다.|
|0x0020|파일에 보관 되었습니다.|
|0x4000|지정 된 이름과 일치 하는 모든 드라이브를 포함 *lpszWildCard*합니다.|
|0x8000|전용 플래그입니다. 전용 플래그가 설정 된 경우 지정 된 형식의 파일에만 나열 됩니다. 그렇지 않은 경우 지정 된 형식의 파일 "normal" 파일 외에도 나열 됩니다.|

*lpszWildCard*<br/>
로 파일 사양 문자열을 가리킵니다. 문자열에서 와일드 카드를 포함할 수 있습니다 (예를 들어, *.\*).

### <a name="return-value"></a>반환 값

목록에 추가할 마지막 파일의 0부터 시작 하는 인덱스입니다. 오류가 발생 하는 경우 반환 값은 LB_ERR 반환 값 LB_ERRSPACE 경우 새 문자열을 저장 하는 사용 가능한 공간이 부족 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#8](../../mfc/codesnippet/cpp/clistbox-class_8.cpp)]

##  <a name="drawitem"></a>  CListBox::DrawItem

소유자 그리기 목록 상자 변경 시각적 측면이 때 프레임 워크에서 호출 됩니다.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpDrawItemStruct*<br/>
에 대 한 긴 포인터를 [DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct) 필요한 드로잉의 종류에 대 한 정보를 포함 하는 구조입니다.

### <a name="remarks"></a>설명

합니다 `itemAction` 및 `itemState` 의 멤버는 `DRAWITEMSTRUCT` 구조 정의 그리기 작업 수행 수입니다.

이 멤버 함수는 기본적으로 아무 작업도 수행 하지. 소유자 그리기에 대 한 그리기를 구현 하려면이 멤버 함수를 재정의 `CListBox` 개체입니다. 응용 프로그램에 제공 된 디스플레이 컨텍스트를 위해 선택한 모든 그래픽 장치 GDI (인터페이스) 개체를 복원 해야 *lpDrawItemStruct* 전에이 멤버 함수를 종료 합니다.

참조 [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) 에 대 한 설명은 `DRAWITEMSTRUCT` 구조입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#9](../../mfc/codesnippet/cpp/clistbox-class_9.cpp)]

##  <a name="findstring"></a>  CListBox::FindString

목록 상자 선택 항목을 변경 하지 않고 지정된 된 접두사를 포함 하는 목록 상자에서 첫 번째 문자열을 찾습니다.

```
int FindString(
    int nStartAfter,
    LPCTSTR lpszItem) const;
```

### <a name="parameters"></a>매개 변수

*nStartAfter*<br/>
첫 번째 항목을 검색 하기 전에 항목의 0부터 시작 하는 인덱스를 포함 합니다. 에 지정 된 항목으로 목록 상자 맨 위부터 계속 검색 목록 상자의 아래쪽에 도달 하면 *nStartAfter*합니다. 하는 경우 *nStartAfter* 가-1 이면 전체 목록 상자 시작 부분에서 검색 됩니다.

*lpszItem*<br/>
검색할 접두사를 포함 하는 null로 끝나는 문자열을 가리킵니다. 검색 사례 독립적 이므로 모든 조합을 대문자 및 소문자가이 문자열 포함 될 수 있습니다.

### <a name="return-value"></a>반환 값

LB_ERR 검색 하지 못한 경우 일치 하는 항목의 0부터 시작 하는 인덱스입니다.

### <a name="remarks"></a>설명

사용 된 [SelectString](#selectstring) 멤버 함수를 찾아 문자열을 선택 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#10](../../mfc/codesnippet/cpp/clistbox-class_10.cpp)]

##  <a name="findstringexact"></a>  CListBox::FindStringExact

에 지정 된 문자열과 일치 하는 첫 번째 목록 상자 문자열을 찾습니다 *lpszFind*합니다.

```
int FindStringExact(
    int nIndexStart,
    LPCTSTR lpszFind) const;
```

### <a name="parameters"></a>매개 변수

*nIndexStart*<br/>
첫 번째 항목을 검색 하기 전에 항목의 0부터 시작 인덱스를 지정 합니다. 에 지정 된 항목으로 목록 상자 맨 위부터 계속 검색 목록 상자의 아래쪽에 도달 하면 *nIndexStart*합니다. 하는 경우 *nIndexStart* 가-1 이면 전체 목록 상자 시작 부분에서 검색 됩니다.

*lpszFind*<br/>
검색할 null 종료 문자열을 가리킵니다. 이 문자열에는 확장명을 포함 하는 전체 파일 이름을 포함할 수 있습니다. 검색 대 소문자를 구분 하지 않으므로 모든 조합을 대문자 및 소문자 문자열을 포함할 수 있습니다.

### <a name="return-value"></a>반환 값

LB_ERR 검색 하지 못한 경우 일치 하는 항목의 인덱스입니다.

### <a name="remarks"></a>설명

목록 상자 없이 소유자 그리기 스타일을 사용 하 여 생성 된 경우는 [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일의 `FindStringExact` 멤버 함수 값에 워드 값을 일치 시 키 려 *lpszFind*합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#11](../../mfc/codesnippet/cpp/clistbox-class_11.cpp)]

##  <a name="getanchorindex"></a>  CListBox::GetAnchorIndex

목록 상자에서 현재 앵커 항목의 0부터 시작 인덱스를 가져옵니다.

```
int GetAnchorIndex() const;
```

### <a name="return-value"></a>반환 값

성공할 경우 현재 앵커 항목의 인덱스 그렇지 않으면 LB_ERR 합니다.

### <a name="remarks"></a>설명

다중 선택 목록 상자에 앵커 항목은 연속 선택한 항목의 블록의 첫 번째 또는 마지막 항목입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CListBox::SetAnchorIndex](#setanchorindex)합니다.

##  <a name="getcaretindex"></a>  CListBox::GetCaretIndex

포커스 영역을 다중 선택 목록 상자에 있는 항목의 인덱스를 결정 합니다.

```
int GetCaretIndex() const;
```

### <a name="return-value"></a>반환 값

포커스 사각형을 목록 상자에 있는 항목의 0부터 시작 하는 인덱스입니다. 목록 상자는 단일 선택 목록 상자 인 경우 반환 값은 있으면 선택 된 항목의 인덱스입니다.

### <a name="remarks"></a>설명

항목 수 또는 선택할 수 있습니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CListBox::SetCaretIndex](#setcaretindex)합니다.

##  <a name="getcount"></a>  CListBox::GetCount

목록 상자에서 항목을 검색합니다.

```
int GetCount() const;
```

### <a name="return-value"></a>반환 값

목록 상자 또는 LB_ERR 오류가 발생 한 경우에 있는 항목의 수입니다.

### <a name="remarks"></a>설명

반환 된 수 (인덱스는 0부터 시작) 마지막 항목의 인덱스 값을 보다 하나 더 큰 경우

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#12](../../mfc/codesnippet/cpp/clistbox-class_12.cpp)]

##  <a name="getcursel"></a>  CListBox::GetCurSel

단일 선택 목록 상자에 있는 경우에 현재 선택한 항목의 인덱스를 검색 합니다.

```
int GetCurSel() const;
```

### <a name="return-value"></a>반환 값

현재 선택된 된 경우 단일 선택 목록 상자 항목의 0부터 시작 하는 인덱스입니다. 현재 선택 된 항목이 없는 경우 LB_ERR입니다.

다중 선택 목록 상자에서 포커스가 있는 항목의 인덱스입니다.

### <a name="remarks"></a>설명

호출 하지 마십시오 `GetCurSel` 다중 선택 목록 상자에 대 한 합니다. 사용 하 여 [CListBox::GetSelItems](#getselitems) 대신 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#13](../../mfc/codesnippet/cpp/clistbox-class_13.cpp)]

##  <a name="gethorizontalextent"></a>  CListBox::GetHorizontalExtent

목록 상자에서 사용 되 고 가로로 스크롤할 수 픽셀에서 너비를 검색 합니다.

```
int GetHorizontalExtent() const;
```

### <a name="return-value"></a>반환 값

목록 상자의 픽셀에서 스크롤할 수 있는 너비입니다.

### <a name="remarks"></a>설명

목록 상자에 가로 스크롤 막대를 경우에 적용 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#14](../../mfc/codesnippet/cpp/clistbox-class_14.cpp)]

##  <a name="getitemdata"></a>  CListBox::GetItemData

지정 된 목록 상자 항목과 연결 된 워드 응용 프로그램에서 제공한 값을 검색 합니다.

```
DWORD_PTR GetItemData(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
목록 상자에서 항목의 0부터 시작 하는 인덱스를 지정합니다.

### <a name="return-value"></a>반환 값

또는 연결 된 항목을 LB_ERR 오류가 발생 하는 경우 32 비트 값입니다.

### <a name="remarks"></a>설명

워드 값이를 *dwItemData* 의 매개 변수를 [SetItemData](#setitemdata) 호출 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#15](../../mfc/codesnippet/cpp/clistbox-class_15.cpp)]

##  <a name="getitemdataptr"></a>  CListBox::GetItemDataPtr

포인터로 지정 된 목록 상자 항목과 연결 된 응용 프로그램에서 제공한 32 비트 값을 검색 (**void** <strong>\*</strong>).

```
void* GetItemDataPtr(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
목록 상자에서 항목의 0부터 시작 하는 인덱스를 지정합니다.

### <a name="return-value"></a>반환 값

오류가 발생 하는 경우에 포인터 또는-1을 검색 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#16](../../mfc/codesnippet/cpp/clistbox-class_16.cpp)]

##  <a name="getitemheight"></a>  CListBox::GetItemHeight

목록 상자의 항목 높이 결정합니다.

```
int GetItemHeight(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
목록 상자에서 항목의 0부터 시작 하는 인덱스를 지정합니다. 목록 상자에 LBS_OWNERDRAWVARIABLE 스타일이; 하는 경우에이 매개 변수는 그렇지 않으면 0으로 설정 되어야 합니다.

### <a name="return-value"></a>반환 값

목록 상자에 있는 항목의 픽셀에서 높이입니다. 목록 상자에는 [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일 반환 값은 지정 된 항목의 높이 *nIndex*합니다. 오류가 발생 하는 경우 반환 값은 LB_ERR 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#17](../../mfc/codesnippet/cpp/clistbox-class_17.cpp)]

##  <a name="getitemrect"></a>  CListBox::GetItemRect

목록 상자 창에 표시 되는 현재 사각형의 크기 해당 범위 목록 상자 항목을 검색 합니다.

```
int GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
항목의 0부터 시작 하는 인덱스를 지정합니다.

*lpRect*<br/>
에 대 한 긴 포인터를 지정 된 [RECT 구조체](/windows/desktop/api/windef/ns-windef-tagrect) 을 받는 항목의 목록 상자 클라이언트 좌표에 합니다.

### <a name="return-value"></a>반환 값

LB_ERR 오류가 발생 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#18](../../mfc/codesnippet/cpp/clistbox-class_18.cpp)]

##  <a name="getlistboxinfo"></a>  CListBox::GetListBoxInfo

열에 따라 항목의 수를 검색 합니다.

```
DWORD GetListBoxInfo() const;
```

### <a name="return-value"></a>반환 값

열 당 항목 수를 `CListBox` 개체입니다.

### <a name="remarks"></a>설명

이 멤버 함수는의 기능을 에뮬레이션 합니다 [LB_GETLISTBOXINFO](/windows/desktop/Controls/lb-getlistboxinfo) Windows SDK에 설명 된 대로 메시지입니다.

##  <a name="getlocale"></a>  CListBox::GetLocale

목록 상자에서 사용 하는 로캘을 검색 합니다.

```
LCID GetLocale() const;
```

### <a name="return-value"></a>반환 값

목록 상자에서 문자열에 대 한 로캘 id (LCID) 값입니다.

### <a name="remarks"></a>설명

로캘이 사용 됩니다, 예를 들어 정렬 된 목록 상자에서 문자열의 정렬 순서를 결정 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CListBox::SetLocale](#setlocale)합니다.

##  <a name="getsel"></a>  CListBox::GetSel

항목의 선택 상태를 검색합니다.

```
int GetSel(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
항목의 0부터 시작 하는 인덱스를 지정합니다.

### <a name="return-value"></a>반환 값

지정된 된 항목을 선택 하는 경우 같은 양수 그렇지 않으면 0입니다. 반환 값 LB_ERR 경우 오류가 발생 합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 모두 단일 및 다중 선택 목록 상자를 사용 하 여 작동합니다.

현재 선택 된 목록 상자 항목의 인덱스를 검색 하려면 사용 [CListBox::GetCurSel](#getcursel)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#19](../../mfc/codesnippet/cpp/clistbox-class_19.cpp)]

##  <a name="getselcount"></a>  CListBox::GetSelCount

다중 선택 목록 상자에서 선택한 항목의 총 수를 검색 합니다.

```
int GetSelCount() const;
```

### <a name="return-value"></a>반환 값

목록 상자에서 선택한 항목의 수입니다. 목록 상자는 단일 선택 목록 상자 인 경우 반환 값은 LB_ERR 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CListBox::GetSelItems](#getselitems)합니다.

##  <a name="getselitems"></a>  CListBox::GetSelItems

다중 선택 목록 상자에서 선택한 항목의 항목 번호를 지정 하는 정수 배열을 사용 하 여 버퍼를 채웁니다.

```
int GetSelItems(
    int nMaxItems,
    LPINT rgIndex) const;
```

### <a name="parameters"></a>매개 변수

*nMaxItems*<br/>
항목 번호가 있는 버퍼에 배치할 수는 선택한 항목의 최대 수를 지정 합니다.

*rgIndex*<br/>
지정 된 정수의 수에 대 한 충분히 큰 버퍼에 대 한 포인터를 지정 *nMaxItems*합니다.

### <a name="return-value"></a>반환 값

항목 수가 실제 버퍼에 배치 합니다. 목록 상자는 단일 선택 목록 상자 인 경우 반환 값은 `LB_ERR`합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#20](../../mfc/codesnippet/cpp/clistbox-class_20.cpp)]

##  <a name="gettext"></a>  CListBox::GetText

목록 상자에서 문자열을 가져옵니다.

```
int GetText(
    int nIndex,
    LPTSTR lpszBuffer) const;

void GetText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
검색할 문자열의 0부터 시작 인덱스를 지정 합니다.

*lpszBuffer*<br/>
문자열을 수신 하는 버퍼를 가리킵니다. 버퍼에 문자열 및 null 종결 문자에 대 한 충분 한 공간이 있어야 합니다. 호출 하 여 문자열의 크기를 미리 확인할 수 있습니다는 `GetTextLen` 멤버 함수입니다.

*rString*<br/>
`CString` 개체에 대한 참조입니다.

### <a name="return-value"></a>반환 값

Null 종결 문자를 제외 하 고 문자열의 길이 (메가바이트)입니다. 하는 경우 *nIndex* 유효한 인덱스를 지정 하지 않는 반환 값은 LB_ERR 합니다.

### <a name="remarks"></a>설명

이 멤버의 두 번째 폼 채우기 함수를 `CString` 문자열 텍스트를 사용 하 여 개체입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#21](../../mfc/codesnippet/cpp/clistbox-class_21.cpp)]

##  <a name="gettextlen"></a>  CListBox::GetTextLen

목록 상자 항목의 문자열의 길이 가져옵니다.

```
int GetTextLen(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
문자열의 0부터 시작 인덱스를 지정 합니다.

### <a name="return-value"></a>반환 값

종료 null 문자를 제외한 문자 문자열의 길이입니다. 하는 경우 *nIndex* 유효한 인덱스를 지정 하지 않는 반환 값은 LB_ERR 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CListBox::GetText](#gettext)합니다.

##  <a name="gettopindex"></a>  CListBox::GetTopIndex

목록 상자에 표시 되는 첫 번째 항목의 인덱스를 검색합니다.

```
int GetTopIndex() const;
```

### <a name="return-value"></a>반환 값

성공 하면 목록 상자에 표시 되는 첫 번째 항목의 인덱스가 고 그렇지 LB_ERR 합니다.

### <a name="remarks"></a>설명

처음에 목록 상자 맨 위에 있는 항목 0가 있지만 목록 상자에서 스크롤 된 다른 항목 맨 위에 있는 될 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#22](../../mfc/codesnippet/cpp/clistbox-class_22.cpp)]

##  <a name="initstorage"></a>  CListBox::InitStorage

목록 상자 항목을 저장 하는 것에 대 한 메모리를 할당 합니다.

```
int InitStorage(
    int nItems,
    UINT nBytes);
```

### <a name="parameters"></a>매개 변수

*nItems*<br/>
추가할 항목의 수를 지정 합니다.

*nBytes*<br/>
메모리의 양 (바이트)를 항목 문자열에 대 한 할당 지정 합니다.

### <a name="return-value"></a>반환 값

성공 하면 최대 메모리 재할당 하기 전에 목록 상자를 저장할 수 있는 항목의 경우 필요한 그렇지 LB_ERRSPACE, 즉 충분 한 메모리를 사용할 수 없습니다.

### <a name="remarks"></a>설명

많은 항목을 추가 하기 전에이 함수 호출을 `CListBox`입니다.

이 함수를 사용 하면 많은 수의 항목 (100 개 이상)이 있는 목록 상자를 초기화 하는 속도입니다. 그러면 다음 메모리의 지정 된 양을 사전 할당 것 [AddString](#addstring), [InsertString](#insertstring), 및 [Dir](#dir) 함수는 사용 가능한 가장 짧은 시간. 매개 변수에 대해 예측을 사용할 수 있습니다. 를 추정 하는 경우 일부 추가 메모리가 할당; 을 과소 평가 하는 경우 미리 할당 된 크기를 초과 하는 항목에 대 한 정상적인 할당이 됩니다.

Windows 95/98만: 합니다 *nItems* 매개 변수는 16 비트 값으로 제한 합니다. 즉, 목록 상자 32,767 개 항목을 포함할 수 없습니다. 항목 수가 제한 된 경우에 목록 상자의 항목의 총 크기는 사용 가능한 메모리 크기로 제한 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#23](../../mfc/codesnippet/cpp/clistbox-class_23.cpp)]

##  <a name="insertstring"></a>  CListBox::InsertString

목록 상자에 문자열을 삽입 합니다.

```
int InsertString(
    int nIndex,
    LPCTSTR lpszItem);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
문자열을 삽입할 위치의 인덱스를 지정 합니다. 이 매개 변수가-1 이면 문자열이 목록의 끝에 추가 됩니다.

*lpszItem*<br/>
삽입할 null 종료 문자열을 가리킵니다.

### <a name="return-value"></a>반환 값

문자열이 삽입된 위치의 0부터 시작하는 인덱스입니다. 오류가 발생 하는 경우 반환 값은 LB_ERR 반환 값 LB_ERRSPACE 경우 새 문자열을 저장 하는 사용 가능한 공간이 부족 합니다.

### <a name="remarks"></a>설명

달리 합니다 [AddString](#addstring) 멤버 함수 `InsertString` 목록을 사용 하 여 발생 하지 않습니다는 [LBS_SORT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 정렬할 스타일.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#24](../../mfc/codesnippet/cpp/clistbox-class_24.cpp)]

##  <a name="itemfrompoint"></a>  CListBox::ItemFromPoint

에 지정 된 지점에 가장 가까운 목록 상자 항목을 결정 *pt*합니다.

```
UINT ItemFromPoint(
    CPoint pt,
    BOOL& bOutside) const;
```

### <a name="parameters"></a>매개 변수

*pt*<br/>
목록 상자의 클라이언트 영역의 왼쪽 위 모퉁이 기준으로 지정 된 가장 가까운 항목을 찾을 수 있는 지점입니다.

*bOutside*<br/>
True로 설정 됩니다는 BOOL 변수에 참조 *pt* 가장 가까운 목록 상자 항목의 클라이언트 영역 외부 false *pt* 가장 가까운 목록 상자 항목의 클라이언트 영역 내 합니다.

### <a name="return-value"></a>반환 값

에 지정 된 지점에 가장 가까운 항목의 인덱스 *pt*합니다.

### <a name="remarks"></a>설명

위에 마우스 커서를 이동 하는 목록 상자 항목을 확인 하려면이 함수를 사용할 수 있습니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CListBox::SetAnchorIndex](#setanchorindex)합니다.

##  <a name="measureitem"></a>  CListBox::MeasureItem

소유자 그리기 스타일을 사용 하 여 목록 상자를 만들 때 프레임 워크에서 호출 됩니다.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpMeasureItemStruct*<br/>
에 대 한 긴 포인터를 [MEASUREITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagmeasureitemstruct) 구조입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 기본적으로 아무 작업도 수행 하지. 이 멤버 함수를 재정의 하 고 입력을 `MEASUREITEMSTRUCT` 구조 목록 상자 크기의 Windows에 알림을 보내야 합니다. 목록 상자를 사용 하 여 만들어지는 경우 합니다 [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일 프레임 워크가이 멤버 함수 목록 상자에서 각 항목에 대 한 호출 합니다. 그렇지 않은 경우이 멤버는 한 번만 호출 됩니다.

사용에 대 한 자세한 내용은 합니다 [LBS_OWNERDRAWFIXED](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 사용 하 여 만든 소유자 그리기 목록 상자에서 스타일의 `SubclassDlgItem` 멤버 함수 `CWnd`의 설명을 참조 하세요 [기술 참고 14](../../mfc/tn014-custom-controls.md).

참조 [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) 에 대 한 설명은 `MEASUREITEMSTRUCT` 구조입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#25](../../mfc/codesnippet/cpp/clistbox-class_25.cpp)]

##  <a name="resetcontent"></a>  CListBox::ResetContent

목록 상자에서 모든 항목을 제거합니다.

```
void ResetContent();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#26](../../mfc/codesnippet/cpp/clistbox-class_26.cpp)]

##  <a name="selectstring"></a>  CListBox::SelectString

검색 목록 상자 항목에 대 한 지정된 된 문자열을 일치 하는 일치 하는 항목이 있으면 해당 항목을 선택 합니다.

```
int SelectString(
    int nStartAfter,
    LPCTSTR lpszItem);
```

### <a name="parameters"></a>매개 변수

*nStartAfter*<br/>
첫 번째 항목을 검색 하기 전에 항목의 0부터 시작 하는 인덱스를 포함 합니다. 에 지정 된 항목으로 목록 상자 맨 위부터 계속 검색 목록 상자의 아래쪽에 도달 하면 *nStartAfter*합니다. 하는 경우 *nStartAfter* 가-1 이면 전체 목록 상자 시작 부분에서 검색 됩니다.

*lpszItem*<br/>
검색할 접두사를 포함 하는 null로 끝나는 문자열을 가리킵니다. 검색 사례 독립적 이므로 모든 조합을 대문자 및 소문자가이 문자열 포함 될 수 있습니다.

### <a name="return-value"></a>반환 값

성공적으로 검색 하는 경우 선택한 항목의 인덱스입니다. 검색에 실패할 경우 반환 값은 LB_ERR 및 현재 선택 영역이 변경 되지 않습니다.

### <a name="remarks"></a>설명

목록 상자가 스크롤됩니다 뷰로 선택한 항목을 가져올 때까지.

이 멤버 함수는 목록 상자를 사용 하 여 사용할 수 없습니다는 [LBS_MULTIPLESEL](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일입니다.

초기 문자 (시작 지점)로 지정한 문자열의 문자를 일치 하는 경우에 항목을 선택한 경우 *lpszItem*합니다.

사용 된 `FindString` 문자열을 찾을 항목을 선택 하지 않고 멤버 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#27](../../mfc/codesnippet/cpp/clistbox-class_27.cpp)]

##  <a name="selitemrange"></a>  CListBox::SelItemRange

다중 선택 목록 상자에서 연속적으로 항목을 선택합니다.

```
int SelItemRange(
    BOOL bSelect,
    int nFirstItem,
    int nLastItem);
```

### <a name="parameters"></a>매개 변수

*bSelect*<br/>
선택 영역을 설정 하는 방법을 지정 합니다. 하는 경우 *선택 하십시오* 가 TRUE 이면 FALSE 인 경우 강조 표시를 제거 되 고 문자열 옵션을 선택 하지 않으면 문자열 선택 되 고 강조 표시 합니다.

*nFirstItem*<br/>
설정할 첫 번째 항목의 0부터 시작 인덱스를 지정 합니다.

*nLastItem*<br/>
설정할 마지막 항목의 0부터 시작 인덱스를 지정 합니다.

### <a name="return-value"></a>반환 값

LB_ERR 오류가 발생 합니다.

### <a name="remarks"></a>설명

다중 선택 목록 상자에만이 멤버 함수를 사용 합니다. 다중 선택 목록 상자에서 항목을 하나만 선택 해야 할 경우-즉, 경우 *nFirstItem* 값과 같음 *nLastItem* -호출 합니다 [SetSel](#setsel) 멤버 함수를 대신 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#28](../../mfc/codesnippet/cpp/clistbox-class_28.cpp)]

##  <a name="setanchorindex"></a>  CListBox::SetAnchorIndex

확장된을 선택 하려면 다중 선택 목록 상자에 앵커를 설정 합니다.

```
void SetAnchorIndex(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
앵커 되는 목록 상자 항목의 0부터 시작 하는 인덱스를 지정 합니다.

### <a name="remarks"></a>설명

다중 선택 목록 상자에 앵커 항목은 연속 선택한 항목의 블록의 첫 번째 또는 마지막 항목입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#29](../../mfc/codesnippet/cpp/clistbox-class_29.cpp)]

##  <a name="setcaretindex"></a>  CListBox::SetCaretIndex

다중 선택 목록 상자에 지정된 된 인덱스의 항목에 포커스를 설정합니다.

```
int SetCaretIndex(
    int nIndex,
    BOOL bScroll = TRUE);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
목록 상자에 포커스를 받을 항목의 0부터 시작 하는 인덱스를 지정 합니다.

*bScroll*<br/>
이 값이 0 이면 완벽 하 게 표시 될 때까지 항목이 스크롤됩니다. 이 값이 없는 경우 0, 항목을 스크롤하여 최소한 부분적으로 표시 될 때까지 합니다.

### <a name="return-value"></a>반환 값

LB_ERR 오류가 발생 합니다.

### <a name="remarks"></a>설명

항목이 표시 되지 않으면, 보기로 스크롤됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#30](../../mfc/codesnippet/cpp/clistbox-class_30.cpp)]

##  <a name="setcolumnwidth"></a>  CListBox::SetColumnWidth

여러 목록 상자에서 모든 열의 픽셀 너비를 설정 (사용 하 여 만든 합니다 [LBS_MULTICOLUMN](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일).

```
void SetColumnWidth(int cxWidth);
```

### <a name="parameters"></a>매개 변수

*cxWidth*<br/>
모든 열의 픽셀 너비를 지정합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#31](../../mfc/codesnippet/cpp/clistbox-class_31.cpp)]

##  <a name="setcursel"></a>  CListBox::SetCurSel

문자열을 선택 하 고 필요한 경우 보기로 스크롤합니다.

```
int SetCurSel(int nSelect);
```

### <a name="parameters"></a>매개 변수

*nSelect*<br/>
선택 된 문자열의 0부터 시작 인덱스를 지정 합니다. 경우 *선택* 가-1 이면 목록 상자 선택 영역이 없는 설정 됩니다.

### <a name="return-value"></a>반환 값

LB_ERR 오류가 발생 합니다.

### <a name="remarks"></a>설명

새 문자열을 선택 하면 목록 상자에서 이전에 선택한 문자열을 강조 표시를 제거 합니다.

단일 선택 목록 상자에만이 멤버 함수를 사용 합니다.

사용을 설정 하거나 다중 선택 목록 상자에서 선택 항목을 제거 하려면 [CListBox::SetSel](#setsel)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#32](../../mfc/codesnippet/cpp/clistbox-class_32.cpp)]

##  <a name="sethorizontalextent"></a>  CListBox::SetHorizontalExtent

목록 상자를 가로로 스크롤할 수 픽셀에서 너비를 설정 합니다.

```
void SetHorizontalExtent(int cxExtent);
```

### <a name="parameters"></a>매개 변수

*cxExtent*<br/>
목록 상자를 가로로 스크롤할 수 픽셀 수를 지정 합니다.

### <a name="remarks"></a>설명

목록 상자의 크기가이 값 보다 작은 경우 가로 스크롤 막대 목록 상자의 항목 가로로 스크롤됩니다. 목록 상자 큰 또는이 값 보다 큰 경우 가로 스크롤 막대가 숨겨집니다.

에 대 한 호출에 응답할 `SetHorizontalExtent`, 목록 상자를 사용 하 여 정의 해야 합니다 [WS_HSCROLL](../../mfc/reference/styles-used-by-mfc.md#window-styles) 스타일입니다.

이 멤버 함수 여러 목록 상자에 유용 하지 않습니다. 여러 목록 상자에 대 한 호출을 `SetColumnWidth` 멤버 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#33](../../mfc/codesnippet/cpp/clistbox-class_33.cpp)]

##  <a name="setitemdata"></a>  CListBox::SetItemData

목록 상자에 지정 된 항목과 연결 된 32 비트 값을 설정 합니다.

```
int SetItemData(
    int nIndex,
    DWORD_PTR dwItemData);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
항목의 0부터 시작 하는 인덱스를 지정합니다.

*dwItemData*<br/>
항목과 연관 될 값을 지정 합니다.

### <a name="return-value"></a>반환 값

LB_ERR 오류가 발생 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#34](../../mfc/codesnippet/cpp/clistbox-class_34.cpp)]

##  <a name="setitemdataptr"></a>  CListBox::SetItemDataPtr

지정 된 포인터 목록 상자에 지정 된 항목과 연결 된 32 비트 값을 설정 합니다 ( **void** <strong>\*</strong>).

```
int SetItemDataPtr(
    int nIndex,
    void* pData);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
항목의 0부터 시작 하는 인덱스를 지정합니다.

*pData*<br/>
항목과 연결 된 수에 대 한 포인터를 지정 합니다.

### <a name="return-value"></a>반환 값

LB_ERR 오류가 발생 합니다.

### <a name="remarks"></a>설명

이 포인터 목록 상자 내에서 항목의 상대 위치 항목을 추가 하거나 제거 달라질 경우에 목록 상자의 수명 동안 유효한 상태로 유지 됩니다. 따라서 상자 내에서 항목의 인덱스에 변경할 수 있지만 포인터 신뢰할 수 있는 상태로 유지 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#35](../../mfc/codesnippet/cpp/clistbox-class_35.cpp)]

##  <a name="setitemheight"></a>  CListBox::SetItemHeight

목록 상자에서 항목의 높이 설정합니다.

```
int SetItemHeight(
    int nIndex,
    UINT cyItemHeight);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
목록 상자에서 항목의 0부터 시작 하는 인덱스를 지정합니다. 목록 상자에 LBS_OWNERDRAWVARIABLE 스타일이; 하는 경우에이 매개 변수는 그렇지 않으면 0으로 설정 되어야 합니다.

*cyItemHeight*<br/>
항목의 픽셀에서 높이 지정합니다.

### <a name="return-value"></a>반환 값

LB_ERR 인덱스나 높이 유효 하지 않은 경우입니다.

### <a name="remarks"></a>설명

목록 상자에는 [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일을이 함수에 지정 된 항목의 높이 설정 합니다 *nIndex*합니다. 그렇지 않은 경우이 함수는 목록 상자에서 모든 항목의 높이 설정합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#36](../../mfc/codesnippet/cpp/clistbox-class_36.cpp)]

##  <a name="setlocale"></a>  CListBox::SetLocale

이 목록 상자에 대 한 로캘 식별자를 설정합니다.

```
LCID SetLocale(LCID nNewLocale);
```

### <a name="parameters"></a>매개 변수

*nNewLocale*<br/>
새 로캘 id (LCID) 목록 상자에 대해 설정할 값입니다.

### <a name="return-value"></a>반환 값

이 목록 상자에 대 한 이전 로캘 id (LCID) 값입니다.

### <a name="remarks"></a>설명

경우 `SetLocale` 를 호출 하지 않으면 기본 시스템에서 로캘을 가져옵니다. 이 시스템 기본 로캘로 Control Panel을 사용 하 여 수정할 수 있는 지역 (또는 International) 응용 프로그램입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#37](../../mfc/codesnippet/cpp/clistbox-class_37.cpp)]

##  <a name="setsel"></a>  CListBox::SetSel

다중 선택 목록 상자에 문자열을 선택합니다.

```
int SetSel(
    int nIndex,
    BOOL bSelect = TRUE);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
설정할 문자열의 0부터 시작 하는 인덱스를 포함 합니다. 경우-1로, 선택 영역에 추가 하거나 값에 따라 모든 문자열에서 제거 *선택 하십시오*합니다.

*bSelect*<br/>
선택 영역을 설정 하는 방법을 지정 합니다. 하는 경우 *선택 하십시오* 가 TRUE 이면 FALSE 인 경우 강조 표시를 제거 되 고 문자열 옵션을 선택 하지 않으면 문자열 선택 되 고 강조 표시 합니다. 지정된 된 문자열 선택 하 고 기본적으로 강조 표시 됩니다.

### <a name="return-value"></a>반환 값

LB_ERR 오류가 발생 합니다.

### <a name="remarks"></a>설명

다중 선택 목록 상자에만이 멤버 함수를 사용 합니다.

단일 선택 목록 상자에서 항목을 선택 하려면 사용 하 여 [CListBox::SetCurSel](#setcursel)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#38](../../mfc/codesnippet/cpp/clistbox-class_38.cpp)]

##  <a name="settabstops"></a>  CListBox::SetTabStops

목록 상자에 탭 정지 위치를 설정 합니다.

```
void SetTabStops();
BOOL SetTabStops(const int& cxEachStop);

BOOL SetTabStops(
    int nTabStops,
    LPINT rgTabStops);
```

### <a name="parameters"></a>매개 변수

*cxEachStop*<br/>
탭 정지에 설정 된 모든 *cxEachStop* 대화 상자 단위입니다. 참조 *rgTabStops* 대화 상자 단위에 대 한 합니다.

*nTabStops*<br/>
목록 상자에 탭 정지의 수를 지정 합니다.

*rgTabStops*<br/>
대화 상자 단위에서 탭 정지 위치를 포함 하는 정수 배열의 첫 번째 멤버를 가리킵니다. 대화 상자 단위는 가로 또는 세로 거리입니다. 하나의 가로 대화 상자 단위는 1-4 현재 대화 기본 너비 단위 같음 및 하나의 세로 대화 상자 단위는 현재 대화 기본 높이 단위의 1 / 8 같음. 대화 상자 기본 단위는 현재 시스템 글꼴의 너비와 높이에 따라 계산 됩니다. `GetDialogBaseUnits` Windows 함수 현재 대화 상자 기본 단위를 픽셀 단위로 반환 합니다. 탭 정지; 오름차순으로 정렬 되어야 합니다. 백 탭 허용 되지 않습니다.

### <a name="return-value"></a>반환 값

모든 탭 설정 된 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

탭 정지 2 대화 상자 단위는 기본 크기를 설정 하려면이 멤버 함수는 매개 변수가 없는 버전을 호출 합니다. 탭 정지 2 이외의 크기를 설정 하려면 사용 하 여 버전을 호출 합니다 *cxEachStop* 인수입니다.

탭 정지 배열의 크기를 설정 하려면 사용 하 여 버전을 사용 합니다 *rgTabStops* 하 고 *nTabStops* 인수. 탭 정지의 각 값에 대해 설정할 *rgTabStops*를 지정한 수 까지의 *nTabStops*합니다.

에 대 한 호출에 응답 하는 `SetTabStops` 멤버 함수를 목록 상자 만들어야 사용 하 여 합니다 [LBS_USETABSTOPS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#39](../../mfc/codesnippet/cpp/clistbox-class_39.cpp)]

##  <a name="settopindex"></a>  CListBox::SetTopIndex

특정 목록 상자 항목을 표시 하는지 확인 합니다.

```
int SetTopIndex(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
목록 상자 항목의 0부터 시작 하는 인덱스를 지정합니다.

### <a name="return-value"></a>반환 값

성공 하면 0 또는 LB_ERR 오류가 발생 합니다.

### <a name="remarks"></a>설명

목록 상자에 지정 된 항목까지 스크롤 하는 시스템이 *nIndex* 나타납니다 목록의 맨 위에 있는 상자 또는 최대 스크롤 범위에 도달 했습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#40](../../mfc/codesnippet/cpp/clistbox-class_40.cpp)]

##  <a name="vkeytoitem"></a>  CListBox::VKeyToItem

목록 상자의 부모 창 목록 상자에서 WM_VKEYTOITEM 메시지를 받을 때 프레임 워크에서 호출 됩니다.

```
virtual int VKeyToItem(
    UINT nKey,
    UINT nIndex);
```

### <a name="parameters"></a>매개 변수

*nKey*<br/>
사용자가 누른 키의 가상 키 코드입니다. 에서 표준 가상 키 코드 목록은 Winuser.h을 참조 하세요.

*nIndex*<br/>
목록 상자 캐럿의 현재 위치입니다.

### <a name="return-value"></a>반환 값

반환-더 이상 작업에 대 한 2,-기본 작업에 대 한 1 또는 음수가 아닌 숫자 키 입력에 대 한 기본 작업을 수행 하는 목록 상자 항목의 인덱스를 지정 합니다.

### <a name="remarks"></a>설명

목록 상자에서 다음을 모두 충족 하는 경우에 있지만 WM_KEYDOWN 메시지를 받으면 WM_VKEYTOITEM 메시지 목록 상자에서 전송 됩니다.

- 에 [LBS_WANTKEYBOARDINPUT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일 집합을 지정 합니다.

- 에 하나 이상의 항목이 있습니다.

호출 하지 말아야이 함수가 직접. 키보드 메시지의 고유한 사용자 지정 처리를 제공 하려면이 함수를 재정의 합니다.

재정의 수행 작업 프레임 워크에 알립니다 값을 반환 해야 합니다. 반환 값-2 응용 프로그램 항목을 선택 하는 모든 측면을 처리 하 고 목록 상자에 추가 작업이 없으므로 필요 나타냅니다. 반환 전에-2, 선택을 설정 하거나 캐럿 또는 둘 다를 이동할 수 있습니다. 선택 영역을 설정 하려면 [SetCurSel](#setcursel) 하거나 [SetSel](#setsel)합니다. 캐럿을 이동 하려면 사용 하 여 [SetCaretIndex](#setcaretindex)합니다.

반환 값은-1이 나타냅니다 목록 상자 키 입력에 대 한 응답의 기본 작업을 수행 해야 합니다. 기본 구현에서는-1이 반환 됩니다.

반환 값 0 이상인 목록 상자에서 항목의 인덱스를 지정 하 고 목록 상자에서 지정된 된 항목 키에 대 한 기본 작업을 수행 해야 나타냅니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#41](../../mfc/codesnippet/cpp/clistbox-class_41.cpp)]

## <a name="see-also"></a>참고자료

[MFC 샘플 CTRLTEST](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[CButton 클래스](../../mfc/reference/cbutton-class.md)<br/>
[CComboBox 클래스](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit Class](../../mfc/reference/cedit-class.md)<br/>
[CScrollBar 클래스](../../mfc/reference/cscrollbar-class.md)<br/>
[CStatic 클래스](../../mfc/reference/cstatic-class.md)
