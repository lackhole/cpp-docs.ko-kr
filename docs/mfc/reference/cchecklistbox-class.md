---
title: CCheckListBox 클래스
ms.date: 11/04/2016
f1_keywords:
- CCheckListBox
- AFXWIN/CCheckListBox
- AFXWIN/CCheckListBox::CCheckListBox
- AFXWIN/CCheckListBox::Create
- AFXWIN/CCheckListBox::DrawItem
- AFXWIN/CCheckListBox::Enable
- AFXWIN/CCheckListBox::GetCheck
- AFXWIN/CCheckListBox::GetCheckStyle
- AFXWIN/CCheckListBox::IsEnabled
- AFXWIN/CCheckListBox::MeasureItem
- AFXWIN/CCheckListBox::OnGetCheckPosition
- AFXWIN/CCheckListBox::SetCheck
- AFXWIN/CCheckListBox::SetCheckStyle
helpviewer_keywords:
- CCheckListBox [MFC], CCheckListBox
- CCheckListBox [MFC], Create
- CCheckListBox [MFC], DrawItem
- CCheckListBox [MFC], Enable
- CCheckListBox [MFC], GetCheck
- CCheckListBox [MFC], GetCheckStyle
- CCheckListBox [MFC], IsEnabled
- CCheckListBox [MFC], MeasureItem
- CCheckListBox [MFC], OnGetCheckPosition
- CCheckListBox [MFC], SetCheck
- CCheckListBox [MFC], SetCheckStyle
ms.assetid: 1dd78438-00e8-441c-b36f-9c4f9ac0d019
ms.openlocfilehash: f8c725ea30754a42ce3045f1160b7a09c4481e39
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507345"
---
# <a name="cchecklistbox-class"></a>CCheckListBox 클래스

Windows 검사 목록 상자의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CCheckListBox : public CListBox
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|Description|
|----------|-----------------|
|[CCheckListBox::CCheckListBox](#cchecklistbox)|`CCheckListBox` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|Description|
|----------|-----------------|
|[CCheckListBox::Create](#create)|Windows 검사 목록 상자를 만들고 `CCheckListBox` 개체에 연결 합니다.|
|[CCheckListBox::DrawItem](#drawitem)|소유자 그리기 목록 상자의 시각적 측면이 변경 될 때 프레임 워크에서 호출 됩니다.|
|[CCheckListBox::Enable](#enable)|검사 목록 상자 항목을 사용 하거나 사용 하지 않도록 설정 합니다.|
|[CCheckListBox::GetCheck](#getcheck)|항목의 확인란 상태를 가져옵니다.|
|[CCheckListBox::GetCheckStyle](#getcheckstyle)|컨트롤의 확인란에 대 한 스타일을 가져옵니다.|
|[CCheckListBox::IsEnabled](#isenabled)|항목을 사용할 수 있는지 여부를 확인 합니다.|
|[CCheckListBox::MeasureItem](#measureitem)|소유자 그리기 스타일이 있는 목록 상자를 만들 때 프레임 워크에서 호출 됩니다.|
|[CCheckListBox::OnGetCheckPosition](#ongetcheckposition)|항목의 확인란 위치를 가져오기 위해 프레임 워크에서 호출 됩니다.|
|[CCheckListBox::SetCheck](#setcheck)|항목의 확인란 상태를 설정 합니다.|
|[CCheckListBox::SetCheckStyle](#setcheckstyle)|컨트롤의 확인란에 대 한 스타일을 설정 합니다.|

## <a name="remarks"></a>설명

"검사 목록 상자"는 파일 이름과 같은 항목의 목록을 표시 합니다. 목록의 각 항목에는 사용자가 확인 하거나 지울 수 있는 옆에 있는 확인란이 있습니다.

`CCheckListBox`는 목록에 텍스트 문자열이 너무 많이 포함 되어 있으므로 소유자가 그린 컨트롤에만 사용할 수 있습니다. 가장 간단 하 게 검사 목록 상자에는 텍스트 문자열과 확인란이 포함 되어 있지만 텍스트가 없어도 됩니다. 예를 들어 각 항목 옆에 확인란이 있는 작은 비트맵 목록을 사용할 수 있습니다.

사용자 고유의 검사 목록 상자를 만들려면에서 `CCheckListBox`고유한 클래스를 파생 해야 합니다. 고유한 클래스를 파생 시키려면 파생 된 클래스에 대 한 생성자를 작성 한 다음 `Create`를 호출 합니다.

목록 상자에서 부모 (일반적으로 [CDialog](../../mfc/reference/cdialog-class.md)에서 파생 된 클래스)로 보낸 Windows 알림 메시지를 처리 하려면 각 메시지의 부모 클래스에 메시지 매핑 항목과 메시지 처리기 멤버 함수를 추가 합니다.

각 메시지 맵 항목은 다음 형식을 사용 합니다.

**ON\_** _Notification_ **(** _id_, _memberFxn_ **)**

여기서 `id` 는 알림을 보내는 컨트롤의 자식 창 ID를 지정 하 고 `memberFxn` 는 알림을 처리 하기 위해 작성 한 부모 멤버 함수의 이름입니다.

부모의 함수 프로토타입은 다음과 같습니다.

`afx_msg void memberFxn();`

에는 구체적으로 `CCheckListBox` 관련 된 메시지 맵 항목이 하나 뿐 이며 ( [CListBox](../../mfc/reference/clistbox-class.md)에 대 한 메시지 맵 항목도 참조):

- ON_CLBN_CHKCHANGE 사용자가 항목의 확인란 상태를 변경 했습니다.

검사 목록 상자가 기본 검사 목록 상자 (각각의 왼쪽에 있는 기본 크기의 확인란을 사용 하는 문자열 목록) 인 경우 기본 [Cchecklistbox::D rawitem](#drawitem) 를 사용 하 여 검사 목록 상자를 그릴 수 있습니다. 그렇지 않으면 [CListBox:: CompareItem](../../mfc/reference/clistbox-class.md#compareitem) 함수와 [cchecklistbox::D Rawitem](#drawitem) 및 [Cchecklistbox:: MeasureItem](#measureitem) 함수를 재정의 해야 합니다.

대화 상자 템플릿에서 또는 코드에서 직접 검사 목록 상자를 만들 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListBox](../../mfc/reference/clistbox-class.md)

`CCheckListBox`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="cchecklistbox"></a>  CCheckListBox::CCheckListBox

`CCheckListBox` 개체를 생성합니다.

```
CCheckListBox();
```

### <a name="remarks"></a>설명

두 단계로 개체 `CCheckListBox` 를 구성 합니다. 먼저에서 `CCheckListBox`파생 된 클래스를 정의한 다음 Windows `Create`검사 목록 상자를 초기화 하 여 `CCheckListBox` 개체에 연결 하는를 호출 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#60](../../mfc/codesnippet/cpp/cchecklistbox-class_1.cpp)]

##  <a name="create"></a>  CCheckListBox::Create

Windows 검사 목록 상자를 만들고 `CCheckListBox` 개체에 연결 합니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
검사 목록 상자의 스타일을 지정 합니다. 스타일은 LBS_HASSTRINGS 여야 하 고 LBS_OWNERDRAWFIXED (목록의 모든 항목의 높이가 동일 함) 또는 LBS_OWNERDRAWVARIABLE (목록의 항목 높이가 달라 집니다.) 이 스타일은 LBS_USETABSTOPS를 제외한 다른 [목록 상자 스타일](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 과 함께 사용할 수 있습니다.

*rect*<br/>
검사 목록 상자 크기와 위치를 지정 합니다. 는 [Crect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조 중 하나일 수 있습니다.

*pParentWnd*<br/>
검사 목록 상자의 부모 창 (일반적으로 `CDialog` 개체)을 지정 합니다. NULL이 아니어야 합니다.

*nID*<br/>
검사 목록 상자의 컨트롤 ID를 지정 합니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

두 단계로 개체 `CCheckListBox` 를 구성 합니다. 먼저에서 `CcheckListBox` 파생 된 클래스를 정의한 다음 Windows 검사 `Create`목록 상자를 초기화 하 `CCheckListBox`고에 연결 하는를 호출 합니다. 샘플은 [cchecklistbox:: CCheckListBox](#cchecklistbox) 를 참조 하세요.

가 `Create` 실행 되 면 Windows에서 [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)및 [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) 메시지를 검사 목록 컨트롤에 보냅니다.

`CWnd` 이러한 메시지는 기본적으로 기본 클래스의 [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)및 [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) 멤버 함수에 의해 처리 됩니다. 기본 메시지 처리를 확장 하려면 메시지 맵을 파생 된 클래스에 추가 하 고 이전 메시지 처리기 멤버 함수를 재정의 합니다. 예 `OnCreate`를 들어를 재정의 하 여 새 클래스에 필요한 초기화를 수행 합니다.

다음 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 을 검사 목록 상자 컨트롤에 적용 합니다.

- 항상 WS_CHILD

- 일반적으로 WS_VISIBLE

- 거의 WS_DISABLED

- 세로 스크롤 막대를 추가할 WS_VSCROLL

- 가로 스크롤 막대를 추가 하는 WS_HSCROLL

- WS_GROUP 컨트롤

- 이 컨트롤에 대 한 탭 이동을 허용 하는 WS_TABSTOP

##  <a name="drawitem"></a>  CCheckListBox::DrawItem

소유자가 그린 검사 목록 상자의 시각적 측면이 변경 될 때 프레임 워크에서 호출 됩니다.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpDrawItemStruct*<br/>
필요한 그리기 형식에 대 한 정보를 포함 하는 [Drawitemstruct](/windows/win32/api/winuser/ns-winuser-drawitemstruct) 구조체에 대 한 긴 포인터입니다.

### <a name="remarks"></a>설명

구조체의 `itemState` `itemAction` 및멤버는수행할그리기작업을정의합니다`DRAWITEMSTRUCT` .

기본적으로이 함수는 기본적으로 크기가 지정 된 문자열 목록으로 왼쪽에 표시 되는 기본 확인란 목록을 그립니다. 확인란 목록 크기는 [만들기](#create)에 지정 된 목록입니다.

이 멤버 함수를 재정의 하 여 기본값이 아닌 소유자 그리기 검사 목록 상자 그리기를 구현 합니다. 예를 들어, 문자열이 아닌 목록이 있는 목록 상자, 가변 높이 항목 또는 왼쪽에 있지 않은 확인란의 그리기를 구현할 수 있습니다. 응용 프로그램은이 멤버 함수를 종료 하기 전에 *Lpdrawitemstruct* 에 제공 된 표시 컨텍스트에 대해 선택한 모든 GDI (그래픽 장치 인터페이스) 개체를 복원 해야 합니다.

검사 목록 상자 항목의 높이가 모두 다른 경우 검사 목록 상자 스타일 (에 `Create`지정 됨)은 * * LBS_OWNERVARIABLE 이어야 하며 [MeasureItem](#measureitem) 함수를 재정의 해야 합니다.

##  <a name="enable"></a>  CCheckListBox::Enable

검사 목록 상자 항목을 사용 하거나 사용 하지 않도록 설정 하려면이 함수를 호출 합니다.

```
void Enable(
    int nIndex,
    BOOL bEnabled = TRUE);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
사용 하도록 설정할 검사 목록 상자 항목의 인덱스입니다.

*bEnabled*<br/>
항목의 사용 여부를 지정 합니다.

##  <a name="getcheck"></a>  CCheckListBox::GetCheck

지정 된 확인란의 상태를 검색 합니다.

```
int GetCheck(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
목록 상자에 포함 된 확인란의 인덱스 (0부터 시작)입니다.

### <a name="return-value"></a>반환 값

지정 된 확인란의 상태입니다. 다음 표에서는 가능한 값을 나열 합니다.

|값|설명|
|-----------|-----------------|
|BST_CHECKED|확인 확인란 합니다.|
|BST_UNCHECKED|확인란이 선택 되어 있지 않습니다.|
|BST_INDETERMINATE|확인란 상태는 결정 되지 않습니다.|

##  <a name="getcheckstyle"></a>  CCheckListBox::GetCheckStyle

이 함수를 호출 하 여 검사 목록 상자의 스타일을 가져옵니다.

```
UINT GetCheckStyle();
```

### <a name="return-value"></a>반환 값

컨트롤의 확인란에 대 한 스타일입니다.

### <a name="remarks"></a>설명

가능한 스타일에 대 한 자세한 내용은 [Setcheckstyle](#setcheckstyle)을 참조 하십시오.

##  <a name="isenabled"></a>  CCheckListBox::IsEnabled

항목을 사용할 수 있는지 여부를 확인 하려면이 함수를 호출 합니다.

```
BOOL IsEnabled(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
항목의 인덱스입니다.

### <a name="return-value"></a>반환 값

항목을 사용할 수 있는 경우 0이 아닙니다. 그렇지 않으면 0입니다.

##  <a name="measureitem"></a>  CCheckListBox::MeasureItem

기본값이 아닌 스타일의 검사 목록 상자가 생성 될 때 프레임 워크에서 호출 됩니다.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpMeasureItemStruct*<br/>
[MEASUREITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-measureitemstruct) 구조체에 대 한 긴 포인터입니다.

### <a name="remarks"></a>설명

기본적으로이 멤버 함수는 아무 작업도 수행 하지 않습니다. 이 멤버 함수를 재정의 하 고 `MEASUREITEMSTRUCT` 구조를 채워서 검사 목록 상자 항목의 크기를 창에 알립니다. [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일을 사용 하 여 검사 목록 상자를 만든 경우 프레임 워크는 목록 상자의 각 항목에 대해이 멤버 함수를 호출 합니다. 그렇지 않으면이 멤버는 한 번만 호출 됩니다.

##  <a name="ongetcheckposition"></a>  CCheckListBox::OnGetCheckPosition

프레임 워크는 항목에 있는 확인란의 위치와 크기를 가져오기 위해이 함수를 호출 합니다.

```
virtual CRect OnGetCheckPosition(
    CRect rectItem,
    CRect rectCheckBox);
```

### <a name="parameters"></a>매개 변수

*rectItem*<br/>
목록 항목의 위치와 크기입니다.

*rectCheckBox*<br/>
항목 확인란의 기본 위치와 크기입니다.

### <a name="return-value"></a>반환 값

항목 확인란의 위치와 크기입니다.

### <a name="remarks"></a>설명

기본 구현은 확인란의 기본 위치와 크기만 반환 합니다 (`rectCheckBox`). 기본적으로 확인란은 항목의 왼쪽 위 모퉁이에 맞춰지고 표준 확인란의 크기입니다. 오른쪽에 있는 확인란을 선택 하거나 더 크거나 더 작은 확인란을 선택 해야 하는 경우가 있을 수 있습니다. 이러한 경우를 재정의 `OnGetCheckPosition` 하 여 항목 내의 확인란 위치와 크기를 변경 합니다.

##  <a name="setcheck"></a>  CCheckListBox::SetCheck

지정 된 확인란의 상태를 설정 합니다.

```
void SetCheck(
    int nIndex,
    int nCheck);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
목록 상자에 포함 된 확인란의 인덱스 (0부터 시작)입니다.

*nCheck*<br/>
지정 된 확인란의 단추 상태입니다. 가능한 값은 설명 섹션을 참조 하세요.

### <a name="remarks"></a>설명

다음 표에서는 *n* 매개 변수에 사용할 수 있는 값을 보여 줍니다.

|값|Description|
|-----------|-----------------|
|BST_CHECKED|지정 된 확인란을 선택 합니다.|
|BST_UNCHECKED|지정 된 확인란의 선택을 취소 합니다.|
|BST_INDETERMINATE|지정 된 확인란 상태를 미정으로 설정 합니다.<br /><br /> 이 상태는 확인란 스타일이 BS_AUTO3STATE 또는 BS_3STATE 인 경우에만 사용할 수 있습니다. 자세한 내용은 [단추 스타일](../../mfc/reference/styles-used-by-mfc.md#button-styles)을 참조 하세요.|

##  <a name="setcheckstyle"></a>  CCheckListBox::SetCheckStyle

이 함수를 호출 하 여 검사 목록 상자에서 확인란의 스타일을 설정 합니다.

```
void SetCheckStyle(UINT nStyle);
```

### <a name="parameters"></a>매개 변수

*nStyle*<br/>
검사 목록 상자에서 확인란의 스타일을 결정 합니다.

### <a name="remarks"></a>설명

유효한 스타일은 다음과 같습니다.

- BS_CHECKBOX

- BS_AUTOCHECKBOX

- BS_AUTO3STATE

- BS_3STATE

이러한 스타일에 대 한 자세한 내용은 [단추 스타일](../../mfc/reference/styles-used-by-mfc.md#button-styles)을 참조 하세요.

## <a name="see-also"></a>참고자료

[MFC 샘플 TSTCON](../../overview/visual-cpp-samples.md)<br/>
[CListBox 클래스](../../mfc/reference/clistbox-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CListBox 클래스](../../mfc/reference/clistbox-class.md)
