---
title: CMFCHeaderCtrl Class
ms.date: 11/04/2016
f1_keywords:
- CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl::CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl::EnableMultipleSort
- AFXHEADERCTRL/CMFCHeaderCtrl::GetColumnState
- AFXHEADERCTRL/CMFCHeaderCtrl::GetSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::IsAscending
- AFXHEADERCTRL/CMFCHeaderCtrl::IsDialogControl
- AFXHEADERCTRL/CMFCHeaderCtrl::IsMultipleSort
- AFXHEADERCTRL/CMFCHeaderCtrl::RemoveSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::SetSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::OnDrawItem
- AFXHEADERCTRL/CMFCHeaderCtrl::OnDrawSortArrow
- AFXHEADERCTRL/CMFCHeaderCtrl::OnFillBackground
helpviewer_keywords:
- CMFCHeaderCtrl [MFC], CMFCHeaderCtrl
- CMFCHeaderCtrl [MFC], EnableMultipleSort
- CMFCHeaderCtrl [MFC], GetColumnState
- CMFCHeaderCtrl [MFC], GetSortColumn
- CMFCHeaderCtrl [MFC], IsAscending
- CMFCHeaderCtrl [MFC], IsDialogControl
- CMFCHeaderCtrl [MFC], IsMultipleSort
- CMFCHeaderCtrl [MFC], RemoveSortColumn
- CMFCHeaderCtrl [MFC], SetSortColumn
- CMFCHeaderCtrl [MFC], OnDrawItem
- CMFCHeaderCtrl [MFC], OnDrawSortArrow
- CMFCHeaderCtrl [MFC], OnFillBackground
ms.assetid: 2f5fbf7b-5c75-42db-9216-640b1628f777
ms.openlocfilehash: 86674e086da482e59b2711f5ba9154848ff05a6f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62218387"
---
# <a name="cmfcheaderctrl-class"></a>CMFCHeaderCtrl Class

`CMFCHeaderCtrl` 클래스 헤더 컨트롤에서 여러 열의 정렬을 지원 합니다.

## <a name="syntax"></a>구문

```
class CMFCHeaderCtrl : public CHeaderCtrl
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMFCHeaderCtrl::CMFCHeaderCtrl](#cmfcheaderctrl)|`CMFCHeaderCtrl` 개체를 생성합니다.|
|`CMFCHeaderCtrl::~CMFCHeaderCtrl`|소멸자|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort)|사용 하거나 사용 하지 않도록 설정 *여러 열 정렬* 현재 헤더 컨트롤에 대 한 모드입니다.|
|[CMFCHeaderCtrl::GetColumnState](#getcolumnstate)|열 정렬 되지 않으면 오름차순 또는 내림차순으로 정렬 됩니다 하는지 여부를 나타냅니다.|
|[CMFCHeaderCtrl::GetSortColumn](#getsortcolumn)|헤더 컨트롤에서 첫 번째 정렬 된 열의 인덱스를 검색합니다.|
|`CMFCHeaderCtrl::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에 의해 합니다 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식과 연결 된 개체입니다.|
|[CMFCHeaderCtrl::IsAscending](#isascending)|헤더 컨트롤에서 열을 오름차순 정렬 되었는지 여부를 나타냅니다.|
|[CMFCHeaderCtrl::IsDialogControl](#isdialogcontrol)|현재 헤더 컨트롤의 부모 창 대화 상자를 여부를 나타냅니다.|
|[CMFCHeaderCtrl::IsMultipleSort](#ismultiplesort)|현재 헤더 컨트롤 인지 여부를 나타냅니다 *여러 열 정렬* 모드입니다.|
|[CMFCHeaderCtrl::RemoveSortColumn](#removesortcolumn)|정렬 열의 목록에서 지정된 된 열을 제거합니다.|
|[CMFCHeaderCtrl::SetSortColumn](#setsortcolumn)|헤더 컨트롤의 지정 된 열의 정렬 순서를 설정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CMFCHeaderCtrl::OnDrawItem](#ondrawitem)|헤더 컨트롤 열을 그리기 위해 프레임 워크에서 호출 됩니다.|
|[CMFCHeaderCtrl::OnDrawSortArrow](#ondrawsortarrow)|정렬 화살표를 그리기 위해 프레임 워크에서 호출 됩니다.|
|[CMFCHeaderCtrl::OnFillBackground](#onfillbackground)|열 헤더 컨트롤의 배경을 채울 하기 위해 프레임 워크에서 호출 됩니다.|

## <a name="example"></a>예제

다음 예제에서는의 개체를 생성 하는 방법에 설명 합니다 `CMFCHeaderCtrl` 클래스 및 사용 하는 방법 *여러 열 정렬* 현재 헤더 컨트롤에 대 한 모드입니다.

[!code-cpp[NVC_MFC_RibbonApp#24](../../mfc/reference/codesnippet/cpp/cmfcheaderctrl-class_1.cpp)]

## <a name="remarks"></a>설명

`CMFCHeaderCtrl` 클래스를 나타내는 열이 정렬 헤더 컨트롤 열에 정렬 화살표를 그립니다. 사용 하 여 *여러 열 정렬을* 모드 경우 부모 목록 컨트롤에서 열 집합 ( [CMFCListCtrl 클래스](../../mfc/reference/cmfclistctrl-class.md)) 동시에 정렬할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CHeaderCtrl](../../mfc/reference/cheaderctrl-class.md)

[CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxheaderctrl.h

##  <a name="cmfcheaderctrl"></a>  CMFCHeaderCtrl::CMFCHeaderCtrl

`CMFCHeaderCtrl` 개체를 생성합니다.

```
CMFCHeaderCtrl::CMFCHeaderCtrl()
```

### <a name="remarks"></a>설명

이 생성자는 지정된 된 값으로 다음 멤버 변수를 초기화합니다.

|멤버 변수|값|
|---------------------|-----------|
|`m_bIsMousePressed`|FALSE|
|`m_bMultipleSort`|false|
|`m_bAscending`|TRUE|
|`m_nHighlightedItem`|-1|
|`m_bTracked`|FALSE|
|`m_bIsDlgControl`|FALSE|
|`m_hFont`|NULL|

##  <a name="enablemultiplesort"></a>  CMFCHeaderCtrl::EnableMultipleSort

사용 하거나 사용 하지 않도록 설정 *여러 열 정렬* 현재 헤더 컨트롤에 대 한 모드입니다.

```
void EnableMultipleSort(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
[in] 여러 열 정렬 모드를 사용 하도록 설정. 여러 열 정렬 모드를 사용 하지 않도록 설정 하 고 정렬 된 열의 목록에서 열을 제거 하려면 FALSE입니다. 기본값은 TRUE입니다.

### <a name="remarks"></a>설명

이 메서드를 여러 열 정렬 모드를 사용할지를 사용 합니다. 헤더 컨트롤이 여러 열 정렬 모드에 있으면 두 개 이상의 열을 정렬에 참여할 수 있습니다.

##  <a name="getcolumnstate"></a>  CMFCHeaderCtrl::GetColumnState

열에 정렬 되어 있지 않습니다 오름차순 또는 내림차순으로 정렬 됩니다 하는지 여부를 나타냅니다.

```
int GetColumnState(int iColumn) const;
```

### <a name="parameters"></a>매개 변수

*iColumn*<br/>
[in] 열의 0부터 시작 하는 인덱스입니다.

### <a name="return-value"></a>반환 값

지정 된 열의 정렬 상태를 나타내는 값입니다. 다음 표에서 가능한 값을 나열합니다.

|값|설명|
|-----------|-----------------|
|-1|내림차순으로 정렬 합니다.|
|0|정렬 되지 않습니다.|
|1|오름차순으로 정렬 합니다.|

### <a name="remarks"></a>설명

##  <a name="getsortcolumn"></a>  CMFCHeaderCtrl::GetSortColumn

헤더 컨트롤에서 첫 번째 정렬 된 열의 인덱스를 검색합니다.

```
int GetSortColumn() const;
```

### <a name="return-value"></a>반환 값

인덱스는 정렬 된 열 또는 정렬 된 열이 없으면-1입니다.

### <a name="remarks"></a>설명

헤더 컨트롤에 있으면 *여러 열 정렬을* 모드로 컴파일된 응용 프로그램 디버그 모드에서이 메서드 어설션 및 사용 하 게 합니다 [CMFCHeaderCtrl::GetColumnState](#getcolumnstate) 메서드 대신 합니다. 헤더 컨트롤은 여러 열 정렬 모드 소매 모드에서 응용 프로그램을 컴파일한 경우,이 메서드는-1을 반환 합니다.

##  <a name="isascending"></a>  CMFCHeaderCtrl::IsAscending

헤더 컨트롤에서 열을 오름차순 정렬 되었는지 여부를 나타냅니다.

```
BOOL IsAscending() const;
```

### <a name="return-value"></a>반환 값

헤더 컨트롤에서 열 순서를 오름차순 정렬 되어 있으면 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드가 반환 하는 값을 적절 한 정렬 화살표는 헤더 컨트롤 항목에 표시 됩니다. 사용 된 [CMFCHeaderCtrl::SetSortColumn](#setsortcolumn) 정렬 순서를 설정 하는 방법입니다.

##  <a name="isdialogcontrol"></a>  CMFCHeaderCtrl::IsDialogControl

현재 헤더 컨트롤의 부모 창 대화 상자를 여부를 나타냅니다.

```
BOOL IsDialogControl() const;
```

### <a name="return-value"></a>반환 값

현재 헤더 컨트롤의 부모 창 대화 상자를; 이면 TRUE 그렇지 않으면 FALSE입니다.

##  <a name="ismultiplesort"></a>  CMFCHeaderCtrl::IsMultipleSort

현재 헤더 컨트롤 인지 여부를 나타냅니다 *여러 열 정렬* 모드입니다.

```
BOOL IsMultipleSort() const;
```

### <a name="return-value"></a>반환 값

여러 열 정렬 모드를 사용 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

사용 된 [CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort) 메서드를 사용 하도록 설정 또는 여러 열 정렬 모드를 사용 하지 않도록 설정 합니다. 헤더 컨트롤이 여러 열 정렬 모드에 있으면 두 개 이상의 열을 정렬에 참여할 수 있습니다.

##  <a name="ondrawitem"></a>  CMFCHeaderCtrl::OnDrawItem

헤더 컨트롤 열을 그리기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnDrawItem(
    CDC* pDC,
    int iItem,
    CRect rect,
    BOOL bIsPressed,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터입니다.

*iItem*<br/>
[in] 그릴 항목의 0부터 시작 하는 인덱스입니다.

*rect*<br/>
[in] 그릴 항목의 경계 사각형입니다.

*bIsPressed*<br/>
[in] 누름 상태의; 항목을 그릴 TRUE 그렇지 않으면 FALSE입니다.

*bIsHighlighted*<br/>
[in] 항목을 그리는 강조 표시 된 상태 이면 TRUE 그렇지 않으면 FALSE입니다.

##  <a name="ondrawsortarrow"></a>  CMFCHeaderCtrl::OnDrawSortArrow

정렬 화살표를 그리기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnDrawSortArrow(
    CDC* pDC,
    CRect rectArrow);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터입니다.

*rectArrow*<br/>
[in] 정렬 화살표의 경계 사각형입니다.

##  <a name="onfillbackground"></a>  CMFCHeaderCtrl::OnFillBackground

열 헤더 컨트롤의 배경을 채울 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnFillBackground(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터입니다.

### <a name="remarks"></a>설명

##  <a name="removesortcolumn"></a>  CMFCHeaderCtrl::RemoveSortColumn

정렬 열의 목록에서 지정된 된 열을 제거합니다.

```
void RemoveSortColumn(int iColumn);
```

### <a name="parameters"></a>매개 변수

*iColumn*<br/>
[in] 제거할 열의 0부터 시작 하는 인덱스입니다.

##  <a name="setsortcolumn"></a>  CMFCHeaderCtrl::SetSortColumn

헤더 컨트롤의 지정 된 열의 정렬 순서를 설정합니다.

```
void SetSortColumn(
    int iColumn,
    BOOL bAscending=TRUE,
    BOOL bAdd=FALSE);
```

### <a name="parameters"></a>매개 변수

*iColumn*<br/>
[in] 헤더 컨트롤 열의 0부터 시작 하는 인덱스입니다. 이 매개 변수가 0 보다 작으면이 메서드는 정렬 열 목록에서 모든 열을 제거 합니다.

*bAscending*<br/>
[in] 열의 정렬 순서를 지정 하는 *iColumn* 매개 변수를 지정 합니다. 오름차순 키; 설정 내림차순을 설정 하려면 FALSE입니다. 기본값은 TRUE입니다.

*bAdd*<br/>
[in] 이면 true는 열의 정렬 순서를 설정 합니다 *iColumn* 매개 변수를 지정 합니다.

현재 헤더 컨트롤에 있으면 *여러 열 정렬* 모드에서는이 메서드가 정렬 열 목록에 지정 된 열을 추가 합니다. 사용 하 여 [CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort) 여러 열 정렬 모드를 설정 합니다.

여러 열 정렬 모드 설정 하지 되 고 디버그 모드에서이 메서드는 컴파일,이 메서드 어설션 합니다. 여러 열 정렬 모드 설정 하지 않으면이 메서드는 소매 모드로 컴파일된 경우이 메서드는 먼저 정렬 열 목록에서 모든 열을 제거 하 고 목록에 지정된 된 열을 추가.

FALSE로 첫 번째 정렬 열 목록에서 모든 열을 제거 하 고 목록에 지정된 된 열을 추가 합니다. 기본값은 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드를 사용 하 여 열의 정렬 순서를 설정 합니다. 필요한 경우이 메서드는 정렬 열 목록에 열을 추가 합니다. 헤더 컨트롤 위로 또는 아래로 가리키는 정렬 화살표를 그리는 정렬 순서를 사용 합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCListCtrl 클래스](../../mfc/reference/cmfclistctrl-class.md)
