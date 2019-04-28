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
ms.openlocfilehash: 9c649dd979b28e2b545a797c5453a2ec9aa6d0dc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62206732"
---
# <a name="cchecklistbox-class"></a>CCheckListBox 클래스

Windows 검사 목록 상자의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CCheckListBox : public CListBox
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CCheckListBox::CCheckListBox](#cchecklistbox)|`CCheckListBox` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CCheckListBox::Create](#create)|Windows 검사 목록 상자를 만들고 연결 하는 `CCheckListBox` 개체입니다.|
|[CCheckListBox::DrawItem](#drawitem)|소유자 그리기 목록 상자 변경 시각적 측면이 때 프레임 워크에서 호출 됩니다.|
|[CCheckListBox::Enable](#enable)|사용 하거나 검사 목록 상자 항목을 사용 하지 않도록 설정 합니다.|
|[CCheckListBox::GetCheck](#getcheck)|항목의 확인란의 상태를 가져옵니다.|
|[CCheckListBox::GetCheckStyle](#getcheckstyle)|컨트롤의 확인란 스타일을 가져옵니다.|
|[CCheckListBox::IsEnabled](#isenabled)|항목 사용 되는지 여부를 결정 합니다.|
|[CCheckListBox::MeasureItem](#measureitem)|소유자 그리기 스타일을 사용 하 여 목록 상자를 만들 때 프레임 워크에서 호출 됩니다.|
|[CCheckListBox::OnGetCheckPosition](#ongetcheckposition)|항목의 확인란의 위치를 가져오기 위해 프레임 워크에서 호출 됩니다.|
|[CCheckListBox::SetCheck](#setcheck)|항목의 확인란의 상태를 설정 합니다.|
|[CCheckListBox::SetCheckStyle](#setcheckstyle)|컨트롤의 확인란의 스타일을 설정 합니다.|

## <a name="remarks"></a>설명

"검사 목록 상자" 파일 이름과 같은 항목의 목록을 표시합니다. 목록의 각 항목 옆에 있는 사용자 수 선택 하거나 선택 취소 하는 확인란에 있습니다.

`CCheckListBox` 목록에는 텍스트 문자열에 비해 더 포함 되어 있으므로 소유자가 그린 컨트롤에만 됩니다. 가장 간단한 검사 목록 상자의 텍스트 문자열과 확인란을 포함 하지만 텍스트를 전혀 할 필요가 없습니다. 예를 들어, 각 항목 옆의 확인란을 사용 하 여 작은 비트맵 목록이 있을 수 있습니다.

고유한 클래스를 파생 해야 사용자가 직접 검사 목록 상자를 만들려면 `CCheckListBox`합니다. 사용자 고유의 클래스를 파생 파생된 클래스의 생성자를 작성 하려면 호출 `Create`합니다.

목록 상자에서 해당 부모에 보냅니다 Windows 알림 메시지를 처리 하려는 경우 (일반적으로 클래스에서 파생 [CDialog](../../mfc/reference/cdialog-class.md)), 각 메시지에 대 한 부모 클래스에는 메시지 맵 항목 및 메시지 처리기 멤버 함수를 추가 합니다.

각 메시지 맵 항목은 다음 형식을 사용 합니다.

**ON\_**_Notification_ **(** _id_, _memberFxn_ **)**

여기서 `id` 알림을 전송 하는 컨트롤의 자식 창 ID를 지정 하 고 `memberFxn` 알림을 처리 하는 것이 기록한 부모 멤버 함수의 이름입니다.

부모의 함수 프로토타입에 다음과 같습니다.

`afx_msg void memberFxn();`

특히 관련 된 메시지 맵 항목이 하나만 `CCheckListBox` (에 대 한 메시지 맵 항목을 참조 하세요. 하지만 [CListBox](../../mfc/reference/clistbox-class.md)):

- ON_CLBN_CHKCHANGE 사용자는 항목의 확인란의 상태를 변경 되었습니다.

검사 목록 상자에는 기본 검사 목록 상자 (왼쪽의 각 기본 크기의 확인란을 사용 하 여 문자열의 목록)을 하는 경우에 기본값을 사용할 수 있습니다 [CCheckListBox::DrawItem](#drawitem) 검사 목록 상자를 그립니다. 이 고, 그렇지 재정의 해야 합니다는 [CListBox::CompareItem](../../mfc/reference/clistbox-class.md#compareitem) 함수 및 [CCheckListBox::DrawItem](#drawitem) 하 고 [CCheckListBox::MeasureItem](#measureitem) 함수.

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

생성 된 `CCheckListBox` 두 단계에서 개체입니다. 파생 된 클래스를 먼저 정의 `CCheckListBox`, 다음 호출 `Create`, Windows 검사 목록 상자를 초기화 하 고에 연결 하는 `CCheckListBox` 개체입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#60](../../mfc/codesnippet/cpp/cchecklistbox-class_1.cpp)]

##  <a name="create"></a>  CCheckListBox::Create

Windows 검사 목록 상자를 만들고 연결 하는 `CCheckListBox` 개체입니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
검사 목록 상자의 스타일을 지정합니다. LBS_HASSTRINGS LBS_OWNERDRAWFIXED (목록의 모든 항목이 같은 높이 하는 데 사용) 또는 LBS_OWNERDRAWVARIABLE 스타일 이어야 합니다 (목록의 항목은 다양 한 높이가). 이 스타일을 다른와 결합할 수 있습니다 [목록 상자 스타일](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) LBS_USETABSTOPS를 제외 하 고 있습니다.

*rect*<br/>
검사 목록 상자 크기와 위치를 지정합니다. 일 수를 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 구조입니다.

*pParentWnd*<br/>
검사 목록 상자의 부모 창 (일반적으로 `CDialog` 개체). NULL이 아니어야 합니다.

*nID*<br/>
검사 목록 상자의 컨트롤 ID를 지정 합니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

생성 된 `CCheckListBox` 두 단계에서 개체입니다. 파생 된 클래스를 먼저 정의 `CcheckListBox` 호출 `Create`, Windows 검사 목록 상자를 초기화 하 고에 연결 하는 `CCheckListBox`합니다. 참조 [CCheckListBox::CCheckListBox](#cchecklistbox) 샘플입니다.

때 `Create` 보냅니다 Windows를 실행 합니다 [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate)를 [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), 및 [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) 검사 목록 상자 컨트롤에 대 한 메시지입니다.

기본적으로 이러한 메시지의 처리를 [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate)합니다 [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), 및 [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) 멤버 함수 에 `CWnd` 기본 클래스입니다. 기본 메시지 처리를 확장 하는 메시지 맵을 추가 파생된 클래스 및 재정의 이전 메시지 처리기 멤버 함수를 합니다. 재정의 `OnCreate`, 예를 들어, 새 클래스에 대 한 필요한 초기화를 수행 하도록 합니다.

다음 적용 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 검사 목록 상자 컨트롤에:

- WS_CHILD 항상

- WS_VISIBLE 일반적으로

- WS_DISABLED 거의

- WS_VSCROLL에 세로 스크롤 막대를 추가 합니다.

- WS_HSCROLL에 가로 스크롤 막대를 추가 합니다.

- 그룹 컨트롤에 WS_GROUP

- WS_TABSTOP에이 컨트롤에 탭 허용

##  <a name="drawitem"></a>  CCheckListBox::DrawItem

소유자가 그린 검사 목록 상자 변경 시각적 측면이 때 프레임 워크에서 호출 됩니다.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpDrawItemStruct*<br/>
에 대 한 긴 포인터를 [DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct) 필요한 드로잉의 종류에 대 한 정보를 포함 하는 구조입니다.

### <a name="remarks"></a>설명

합니다 `itemAction` 및 `itemState` 의 멤버는 `DRAWITEMSTRUCT` 구조 정의 그리기 작업 수행 수입니다.

기본적으로이 함수는 각 문자열 왼쪽에는 기본 크기의 확인란을 사용 하 여 목록으로 구성 된 기본 확인란 목록을 그립니다. 확인란 목록 크기는에 지정 된 [만들기](#create)합니다.

소유자 그리기 검사 목록 상자의 문자열 없는 목록을 사용 하 여, 가변 높이 항목이 또는 왼쪽에 없는 확인란을 사용 하 여 검사 목록 상자와 같은 기본 없는 그리기를 구현 하려면이 멤버 함수를 재정의 합니다. 응용 프로그램에 제공 된 디스플레이 컨텍스트를 위해 선택한 모든 그래픽 장치 GDI (인터페이스) 개체를 복원 해야 *lpDrawItemStruct* 이 멤버 함수 종료 전에 합니다.

검사 목록 상자 스타일 검사 목록 상자 항목 높이가 모두 같습니다가 아닌 경우 (에 지정 된 `Create`) 이어야 합니다 * * LBS_OWNERVARIABLE를 고를 재정의 해야 합니다 [MeasureItem](#measureitem) 함수.

##  <a name="enable"></a>  CCheckListBox::Enable

검사 목록 상자 항목을 사용 하지 않도록 설정 하거나 사용 하려면이 함수를 호출 합니다.

```
void Enable(
    int nIndex,
    BOOL bEnabled = TRUE);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
사용 하도록 설정 하는 검사 목록 상자 항목의 인덱스입니다.

*bEnabled*<br/>
항목 사용 되는지 여부를 지정 합니다.

##  <a name="getcheck"></a>  CCheckListBox::GetCheck

지정 된 확인란의 상태를 검색 합니다.

```
int GetCheck(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
목록 상자에 있는 확인란의 0부터 시작 인덱스입니다.

### <a name="return-value"></a>반환 값

지정 된 확인란의 상태입니다. 다음 표에서 가능한 값을 나열합니다.

|값|설명|
|-----------|-----------------|
|BST_CHECKED|확인 확인란 합니다.|
|BST_UNCHECKED|확인란 확인 하지 않습니다.|
|BST_INDETERMINATE|확인란 상태가 확정적이 지 않습니다.|

##  <a name="getcheckstyle"></a>  CCheckListBox::GetCheckStyle

검사 목록 상자의 스타일을 가져오려면이 함수를 호출 합니다.

```
UINT GetCheckStyle();
```

### <a name="return-value"></a>반환 값

컨트롤의 확인란 스타일입니다.

### <a name="remarks"></a>설명

가능한 스타일에 대 한 내용은 참조 하세요 [SetCheckStyle](#setcheckstyle)합니다.

##  <a name="isenabled"></a>  CCheckListBox::IsEnabled

항목을 사용할 수 있는지 여부를 확인 하려면이 함수를 호출 합니다.

```
BOOL IsEnabled(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
항목의 인덱스입니다.

### <a name="return-value"></a>반환 값

항목이 활성화 되 면 0이 아닌 값 그렇지 않으면 0입니다.

##  <a name="measureitem"></a>  CCheckListBox::MeasureItem

기본값이 아닌 스타일을 사용 하 여 검사 목록 상자를 만들 때 프레임 워크에서 호출 합니다.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpMeasureItemStruct*<br/>
에 대 한 긴 포인터를 [MEASUREITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagmeasureitemstruct) 구조입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 기본적으로 아무 작업도 수행 하지. 이 멤버 함수를 재정의 하 고 입력 된 `MEASUREITEMSTRUCT` 구조 검사 목록 상자 항목의 크기의 Windows에 알림을 보내야 합니다. 검사 목록 상자를 사용 하 여 만들어지는 경우 합니다 [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일 프레임 워크가이 멤버 함수 목록 상자에서 각 항목에 대 한 호출 합니다. 그렇지 않은 경우이 멤버는 한 번만 호출 됩니다.

##  <a name="ongetcheckposition"></a>  CCheckListBox::OnGetCheckPosition

프레임 워크는 항목의 확인란의 크기와 위치를 가져오려면이 함수를 호출 합니다.

```
virtual CRect OnGetCheckPosition(
    CRect rectItem,
    CRect rectCheckBox);
```

### <a name="parameters"></a>매개 변수

*rectItem*<br/>
목록 항목의 크기와 위치 합니다.

*rectCheckBox*<br/>
기본 위치와 크기를 항목의 상자를 선택합니다.

### <a name="return-value"></a>반환 값

항목의 크기와 위치 상자를 선택합니다.

### <a name="remarks"></a>설명

확인란의 크기와 기본 위치에만 기본 구현은 반환 (`rectCheckBox`). 기본적으로 확인란을 항목의 왼쪽 위 모서리에서 정렬 되 고 표준 확인란 크기입니다. 오른쪽에 있는 확인란을 선택 하거나 크게 또는 작게 확인란이 있는 경우 있을 수 있습니다. 이러한 경우 재정의 `OnGetCheckPosition` 확인란 위치와 항목 내에서 크기를 변경 합니다.

##  <a name="setcheck"></a>  CCheckListBox::SetCheck

지정 된 확인란의 상태를 설정 합니다.

```
void SetCheck(
    int nIndex,
    int nCheck);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
목록 상자에 있는 확인란의 0부터 시작 인덱스입니다.

*nCheck*<br/>
지정 된 확인란 단추 상태입니다. 가능한 값에 대 한 설명 섹션을 참조 합니다.

### <a name="remarks"></a>설명

다음 표에 대 한 가능한 값은 *nCheck* 매개 변수입니다.

|값|설명|
|-----------|-----------------|
|BST_CHECKED|지정 된 확인란을 선택 합니다.|
|BST_UNCHECKED|지정 된 확인란의 선택을 취소 합니다.|
|BST_INDETERMINATE|지정 된 확인란 상태 비활성화를 설정 합니다.<br /><br /> 이 상태는만 확인란 스타일 BS_AUTO3STATE 인지 BS_3STATE 경우 사용할 수 있습니다. 자세한 내용은 [단추 스타일](../../mfc/reference/styles-used-by-mfc.md#button-styles)합니다.|

##  <a name="setcheckstyle"></a>  CCheckListBox::SetCheckStyle

검사 목록 상자에서 확인란의 스타일을 설정 하려면이 함수를 호출 합니다.

```
void SetCheckStyle(UINT nStyle);
```

### <a name="parameters"></a>매개 변수

*nStyle*<br/>
검사 목록 상자에서 확인란의 스타일을 결정 합니다.

### <a name="remarks"></a>설명

유효한 스타일은:

- BS_CHECKBOX

- BS_AUTOCHECKBOX

- BS_AUTO3STATE

- BS_3STATE

이러한 스타일에 대 한 내용은 참조 하세요 [단추 스타일](../../mfc/reference/styles-used-by-mfc.md#button-styles)합니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 TSTCON](../../overview/visual-cpp-samples.md)<br/>
[CListBox 클래스](../../mfc/reference/clistbox-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CListBox 클래스](../../mfc/reference/clistbox-class.md)
