---
title: CMFCDynamicLayout 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCDynamicLayout
- AFXLAYOUT/CMFCDynamicLayout
- AFXLAYOUT/CMFCDynamicLayout::AddItem
- AFXLAYOUT/CMFCDynamicLayout::Adjust
- AFXLAYOUT/CMFCDynamicLayout::Create
- AFXLAYOUT/CMFCDynamicLayout::GetHostWnd
- AFXLAYOUT/CMFCDynamicLayout::GetMinSize
- AFXLAYOUT/CMFCDynamicLayout::GetWindowRect
- AFXLAYOUT/CMFCDynamicLayout::HasItem
- AFXLAYOUT/CMFCDynamicLayout::IsEmpty
- AFXLAYOUT/CMFCDynamicLayout::LoadResource
- AFXLAYOUT/CMFCDynamicLayout::SetMinSize
ms.assetid: c2df2976-f049-47fc-9cf0-abe3e01948bc
ms.openlocfilehash: 40dedbe2737a79b7531b8acd47870ce7cb788604
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62237593"
---
# <a name="cmfcdynamiclayout-class"></a>CMFCDynamicLayout 클래스

사용자가 창의 크기를 조정할 때 창에서 컨트롤이 이동하고 컨트롤의 크기가 조정되는 방식을 지정합니다.

## <a name="syntax"></a>구문

```
class CMFCDynamicLayout : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|`CMFCDynamicLayout::CMFCDynamicLayout`|`CMFCDynamicLayout` 개체를 생성합니다.|
|`CMFCDynamicLayout::~CMFCDynamicLayout`|소멸자|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCDynamicLayout::AddItem](#additem)|자식 창(일반적으로 컨트롤)을 동적 레이아웃 관리자가 제어하는 창 목록에 추가합니다.|
|[CMFCDynamicLayout::Adjust](#adjust)|자식 창(일반적으로 컨트롤)을 동적 레이아웃 관리자가 제어하는 창 목록에 추가합니다.|
|[CMFCDynamicLayout::Create](#create)|호스트 창을 저장하고 유효성을 검사합니다.|
|[CMFCDynamicLayout::GetHostWnd](#gethostwnd)|호스트 창에 대한 포인터를 반환합니다.|
|[CMFCDynamicLayout::GetMinSize](#getminsize)|레이아웃이 그 이하로 조정되지 않는 창 크기를 반환합니다.|
|[CMFCDynamicLayout::GetWindowRect](#getwindowrect)|창의 현재 클라이언트 영역에 대한 사각형을 검색합니다.|
|[CMFCDynamicLayout::HasItem](#hasitem)|자식 컨트롤이 동적 레이아웃에 추가되었는지 확인합니다.|
|[CMFCDynamicLayout::IsEmpty](#isempty)|동적 레이아웃에 추가된 자식 창이 없는지 확인합니다.|
|[CMFCDynamicLayout::LoadResource](#loadresource)|AFX_DIALOG_LAYOUT 리소스에서 동적 레이아웃을 읽고 레이아웃을 호스트 창에 적용합니다.|
|정적 [cmfcdynamiclayout:: Movehorizontal](#movehorizontal)|가져옵니다를 [MoveSettings](#movesettings_structure) 얼마나 많은 자식 컨트롤이 가로로 얼마나 이동 사용자가 호스팅 창의 크기 조정 정의 하는 값입니다.|
|정적 [cmfcdynamiclayout:: Movehorizontalandvertical](#movehorizontalandvertical)|가져옵니다를 [MoveSettings](#movesettings_structure) 얼마나 많은 자식 컨트롤이 가로로 얼마나 이동 사용자가 호스팅 창의 크기 조정 정의 하는 값입니다.|
|static [CMFCDynamicLayout::MoveNone](#movenone)|가져옵니다를 [MoveSettings](#movesettings_structure) 세로 또는 자식 컨트롤의 가로 동작이 없음을 나타내는 값입니다.|
|static [CMFCDynamicLayout::MoveVertical](#movevertical)|가져옵니다를 [MoveSettings](#movesettings_structure) 얼마나를 자식 컨트롤이 세로로 얼마나 이동 사용자가 호스팅 창의 크기 조정 정의 하는 값입니다.|
|[CMFCDynamicLayout::SetMinSize](#setminsize)|레이아웃이 그 이하로 조정되지 않는 창 크기를 설정합니다.|
|static [CMFCDynamicLayout::SizeHorizontal](#sizehorizontal)|가져옵니다를 [SizeSettings](#sizesettings_structure) 사용자가 호스팅 창의 크기 조정 얼마나 많은 자식 컨트롤이 가로로 크기가 정의 하는 값입니다.|
|정적 [CMFCDynamicLayout::SizeHorizontalAndVertical](#sizehorizontalandvertical)|가져옵니다를 [SizeSettings](#sizesettings_structure) 사용자가 호스팅 창의 크기 조정 얼마나 많은 자식 컨트롤이 가로로 크기가 정의 하는 값입니다.|
|static [CMFCDynamicLayout::SizeNone](#sizenone)|가져옵니다를 [SizeSettings](#sizesettings_structure) 자식 컨트롤의 크기에 변경이 없음을 나타내는 값입니다.|
|static [CMFCDynamicLayout::SizeVertical](#sizevertical)|가져옵니다를 [SizeSettings](#sizesettings_structure) 얼마나 많은 자식 컨트롤이 세로로 조정 하 사용자가 호스팅 창의 크기 조정 정의입니다.|

## <a name="nested-types"></a>중첩 형식

|이름|설명|
|----------|-----------------|
|[Cmfcdynamiclayout:: Movesettings 구조체](#movesettings_structure)|동적 레이아웃의 컨트롤에 대한 이동 데이터를 캡슐화합니다.|
|[Cmfcdynamiclayout:: Sizesettings 구조체](#sizesettings_structure)|동적 레이아웃의 컨트롤에 대한 크기 변경 데이터를 캡슐화합니다.|

## <a name="remarks"></a>설명

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCDynamicLayout](../../mfc/reference/cmfctoolbarbutton-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxlayout.h

##  <a name="additem"></a>  CMFCDynamicLayout::AddItem

자식 창(일반적으로 컨트롤)을 동적 레이아웃 관리자가 제어하는 창 목록에 추가합니다.

```
BOOL AddItem(
    HWND hwnd,
    MoveSettings moveSettings SizeSettings sizeSettings);

BOOL AddItem(
    int nID,
    MoveSettings moveSettings SizeSettings sizeSettings);
```

### <a name="parameters"></a>매개 변수

*hwnd*<br/>
추가할 창에 대한 핸들입니다.

*nID*<br/>
추가할 자식 컨트롤의 ID입니다.

*moveSettings*<br/>
창 크기가 변경될 때 컨트롤을 이동하는 방법을 설명하는 구조체입니다.

*sizeSettings*<br/>
창 크기가 변경될 때 컨트롤의 크기를 조정하는 방법을 설명하는 구조체입니다.

### <a name="return-value"></a>반환 값

항목이 성공적으로 추가되었으면 TRUE이고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

호스팅 창의 크기를 조정하면 자식 컨트롤의 위치 및 크기가 동적으로 변경됩니다.

##  <a name="adjust"></a>  CMFCDynamicLayout::Adjust

자식 창(일반적으로 컨트롤)을 동적 레이아웃 관리자가 제어하는 창 목록에 추가합니다.

```
void Adjust();
```

### <a name="remarks"></a>설명

호스팅 창의 크기를 조정하면 자식 컨트롤의 위치 및 크기가 동적으로 변경됩니다.

##  <a name="create"></a>  CMFCDynamicLayout::Create

호스트 창을 저장하고 유효성을 검사합니다.

```
BOOL Create(CWnd* pHostWnd);
```

### <a name="parameters"></a>매개 변수

*pHostWnd*<br/>
호스트 창에 대한 포인터입니다.

### <a name="return-value"></a>반환 값

생성에 성공하면 TRUE이고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="gethostwnd"></a>  CMFCDynamicLayout::GetHostWnd

호스트 창에 대한 포인터를 반환합니다.

```
CWnd* GetHostWnd();
```

### <a name="return-value"></a>반환 값

호스트 창에 대한 포인터입니다.

### <a name="remarks"></a>설명

기본적으로 모든 자식 컨트롤 위치가 이 창을 기준으로 다시 계산됩니다.

##  <a name="getminsize"></a>  CMFCDynamicLayout::GetMinSize

레이아웃이 그 이하로 조정되지 않는 창 크기를 반환합니다.

```
CSize GetMinSize();
```

### <a name="return-value"></a>반환 값

레이아웃이 그 이하로 조정되지 않는 창 크기입니다.

### <a name="remarks"></a>설명

호스팅 창의 크기를 조정하면 자식 컨트롤의 위치 및 크기가 동적으로 변경되지만 레이아웃이 그 이하로 조정되지 않는 최소 크기가 있습니다. 사용자는 창의 크기를 더 작은 크기로 조정할 수 있지만 이렇게 하면 창 부분이 뷰에서 숨겨집니다.

##  <a name="getwindowrect"></a>  CMFCDynamicLayout::GetWindowRect

창의 현재 클라이언트 영역에 대한 사각형을 검색합니다.

```
void GetHostWndRect(CRect& rect,);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
함수에서 반환된 이 매개 변수에는 레이아웃 영역의 경계 사각형이 포함됩니다. 이는 출력 매개 변수이며, 입력 값은 덮어써집니다.

### <a name="remarks"></a>설명

##  <a name="hasitem"></a>  CMFCDynamicLayout::HasItem

자식 컨트롤이 동적 레이아웃에 추가되었는지 확인합니다.

```
BOOL HasItem(HWND hwnd);
```

### <a name="parameters"></a>매개 변수

*hwnd*<br/>
컨트롤의 창 핸들입니다.

### <a name="return-value"></a>반환 값

레이아웃에 이 항목이 있으면 TRUE이고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="isempty"></a>  CMFCDynamicLayout::IsEmpty

동적 레이아웃에 추가된 자식 창이 없는지 확인합니다.

```
BOOL IsEmpty();
```

### <a name="return-value"></a>반환 값

레이아웃에 항목이 없으면 TRUE이고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="loadresource"></a>  CMFCDynamicLayout::LoadResource

AFX_DIALOG_LAYOUT 리소스에서 동적 레이아웃을 읽고 레이아웃을 호스트 창에 적용합니다.

```
static BOOL LoadResource(CWnd* pHostWnd,
    LPVOID lpResource,
    DWORD dwSize);
```

### <a name="parameters"></a>매개 변수

*pHostWnd*<br/>
호스트 창에 대한 포인터입니다.

*lpResource*<br/>
AFX_DIALOG_LAYOUT 리소스를 포함하는 버퍼에 대한 포인터입니다.

*dwSize*<br/>
버퍼 크기(바이트)입니다.

### <a name="return-value"></a>반환 값

리소스가 로드되어 호스트 창에 적용되면 TRUE이고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="movehorizontal"></a>  CMFCDynamicLayout::MoveHorizontal

가져옵니다를 [MoveSettings](#movesettings_structure) 얼마나 많은 자식 컨트롤이 가로로 얼마나 이동 사용자가 호스팅 창의 크기 조정 정의 하는 값입니다.

```
static MoveSettings MoveHorizontal(int nRatio);
```

### <a name="parameters"></a>매개 변수

*nRatio*<br/>
사용자가 호스트 창의 크기를 조정할 때 자식 컨트롤이 가로로 얼마나 이동하는지를 백분율로 정의합니다.

### <a name="return-value"></a>반환 값

A [MoveSettings](#movesettings_structure) 요청한 캡슐화 하는 값 비율을 이동 합니다.

### <a name="remarks"></a>설명

##  <a name="movehorizontalandvertical"></a>  CMFCDynamicLayout::MoveHorizontalAndVertical

가져옵니다를 [MoveSettings](#movesettings_structure) 얼마나 많은 자식 컨트롤이 가로로 얼마나 이동 사용자가 호스팅 창의 크기 조정 정의 하는 값입니다.

```
static MoveSettings MoveHorizontalAndVertical(int nXRatio int nYRatio);
```

### <a name="parameters"></a>매개 변수

*nXRatio*<br/>
사용자가 호스트 창의 크기를 조정할 때 자식 컨트롤이 가로로 얼마나 이동하는지를 백분율로 정의합니다.

*nYRatio*<br/>
사용자가 호스트 창의 크기를 조정할 때 자식 컨트롤이 세로로 얼마나 이동하는지를 백분율로 정의합니다.

### <a name="return-value"></a>반환 값

A [MoveSettings](#movesettings_structure) 요청한 캡슐화 하는 값 비율을 이동 합니다.

### <a name="remarks"></a>설명

##  <a name="movenone"></a>  CMFCDynamicLayout::MoveNone

가져옵니다를 [MoveSettings](#movesettings_structure) 세로 또는 자식 컨트롤의 가로 동작이 없음을 나타내는 값입니다.

```
static MoveSettings MoveNone();
```

### <a name="return-value"></a>반환 값

A [MoveSettings](#movesettings_structure) 는 사용자가 호스트 창으로 이동 하지 않습니다 있도록 위치에 컨트롤을 수정 하는 값입니다.

### <a name="remarks"></a>설명

##  <a name="movesettings_structure"></a>  Cmfcdynamiclayout:: Movesettings 구조체

동적 레이아웃의 컨트롤에 대한 이동 데이터를 캡슐화합니다.

```
struct CMFCDynamicLayout::MoveSettings;
```

### <a name="remarks"></a>설명

이는 `CMFCDynamicLayout` 내부에 중첩된 클래스입니다.

## <a name="cmfcdynamiclayoutmovesettingsishorizontal"></a>CMFCDynamicLayout::MoveSettings::IsHorizontal

이동 데이터가 0이 아닌 가로 이동을 지정하는지 확인합니다.

```
BOOL IsHorizontal() const
```

## <a name="return-value"></a>반환 값

`MoveSettings` 개체가 0이 아닌 가로 이동을 지정하면 TRUE입니다.

## <a name="cmfcdynamiclayoutmovesettingsisnone"></a>CMFCDynamicLayout::MoveSettings::IsNone

데이터 이동에서 이동을 지정하지 않는지 확인합니다.

```
BOOL IsNone() const
```

## <a name="return-value"></a>반환 값

`MoveSettings` 개체가 이동을 지정하지 않는 경우 TRUE입니다.

## <a name="cmfcdynamiclayoutmovesettingsisvertical"></a>CMFCDynamicLayout::MoveSettings::IsVertical

  이동 데이터가 0이 아닌 세로 이동을 지정하는지 확인합니다.

```
BOOL IsVertical() const
```

## <a name="return-value"></a>반환 값

`MoveSettings` 개체가 0이 아닌 세로 이동을 지정하면 TRUE입니다.

##  <a name="movevertical"></a>  CMFCDynamicLayout::MoveVertical

가져옵니다를 [MoveSettings](#movesettings_structure) 얼마나를 자식 컨트롤이 세로로 얼마나 이동 사용자가 호스팅 창의 크기 조정 정의 하는 값입니다.

```
static MoveSettings MoveVertical(int nRatio);
```

### <a name="parameters"></a>매개 변수

*nRatio*<br/>
사용자가 호스트 창의 크기를 조정할 때 자식 컨트롤이 세로로 얼마나 이동하는지를 백분율로 정의합니다.

### <a name="return-value"></a>반환 값

A [MoveSettings](#movesettings_structure) 요청한 캡슐화 하는 값 비율을 이동 합니다.

### <a name="remarks"></a>설명

##  <a name="setminsize"></a>  CMFCDynamicLayout::SetMinSize

레이아웃이 그 이하로 조정되지 않는 창 크기를 설정합니다.

```
void SetMinSize(const CSize& size);
```

### <a name="parameters"></a>매개 변수

*size*<br/>
레이아웃이 그 이하로 조정되지 않는 원하는 크기입니다.

### <a name="remarks"></a>설명

호스팅 창의 크기를 조정하면 자식 컨트롤의 위치 및 크기가 동적으로 변경되지만 레이아웃이 그 이하로 조정되지 않는 최소 크기가 있습니다. 사용자는 창의 크기를 더 작은 크기로 조정할 수 있지만 이렇게 하면 창 부분이 뷰에서 숨겨집니다.

##  <a name="sizehorizontal"></a>  CMFCDynamicLayout::SizeHorizontal

가져옵니다를 [SizeSettings](#sizesettings_structure) 사용자가 호스팅 창의 크기 조정 얼마나 많은 자식 컨트롤이 가로로 크기가 정의 하는 값입니다.

```
static SizeSettings SizeHorizontal(int nRatio);
```

### <a name="parameters"></a>매개 변수

*nRatio*<br/>
사용자가 호스트 창 크기를 조정할 때 자식 컨트롤의 크기가 가로로 얼마나 조정되는지를 백분율로 정의합니다.

### <a name="return-value"></a>반환 값

A [SizeSettings](#sizesettings_structure) 요청 된 크기 비율을 캡슐화 하는 값입니다.

### <a name="remarks"></a>설명

##  <a name="sizehorizontalandvertical"></a>  CMFCDynamicLayout::SizeHorizontalAndVertical

가져옵니다를 [SizeSettings](#sizesettings_structure) 사용자가 호스팅 창의 크기 조정 얼마나 많은 자식 컨트롤이 가로로 크기가 정의 하는 값입니다.

```
static SizeSettings SizeHorizontalAndVertical(int nXRatio int nYRatio);
```

### <a name="parameters"></a>매개 변수

*nXRatio*<br/>
사용자가 호스트 창 크기를 조정할 때 자식 컨트롤의 크기가 가로로 얼마나 조정되는지를 백분율로 정의합니다.

*nYRatio*<br/>
사용자가 호스트 창 크기를 조정할 때 자식 컨트롤의 크기가 세로로 얼마나 조정되는지를 백분율로 정의합니다.

### <a name="return-value"></a>반환 값

A [SizeSettings](#sizesettings_structure) 요청 된 크기 비율을 캡슐화 하는 값입니다.

### <a name="remarks"></a>설명

##  <a name="sizenone"></a>  CMFCDynamicLayout::SizeNone

가져옵니다를 [SizeSettings](#sizesettings_structure) 자식 컨트롤의 크기에 변경이 없음을 나타내는 값입니다.

```
static SizeSettings SizeNone();
```

### <a name="return-value"></a>반환 값

A [SizeSettings](#sizesettings_structure) 사용자가 호스트 창 크기 조정으로 크기를 변경 되지 않습니다 있도록 크기에서 컨트롤을 수정 하는 값입니다.

### <a name="remarks"></a>설명

##  <a name="sizesettings_structure"></a>  Cmfcdynamiclayout:: Sizesettings 구조체

동적 레이아웃의 컨트롤에 대한 크기 변경 데이터를 캡슐화합니다.

```
struct CMFCDynamicLayout::SizeSettings;
```

### <a name="remarks"></a>설명

이는 `CMFCDynamicLayout` 내부에 중첩된 클래스입니다.

## <a name="cmfcdynamiclayoutsizesettingsishorizontal"></a>CMFCDynamicLayout::SizeSettings::IsHorizontal

크기 조정 데이터가 0이 아닌 가로 크기 조정을 지정하는지 확인합니다.

```
BOOL IsHorizontal() const
```

## <a name="return-value"></a>반환 값

`SizeSettings` 개체가 0이 아닌 가로 크기 조정을 지정하면 TRUE입니다.

## <a name="cmfcdynamiclayoutsizesettingsisnone"></a>CMFCDynamicLayout::SizeSettings::IsNone

크기 조정 데이터가 크기 조정을 지정하지 않는지 여부를 확인합니다.

```
BOOL IsNone() const
```

## <a name="return-value"></a>반환 값

`SizeSettings` 개체가 크기 조정을 지정하지 않는 경우 TRUE입니다.

## <a name="cmfcdynamiclayoutsizesettingsisvertical"></a>CMFCDynamicLayout::SizeSettings::IsVertical

크기 조정 데이터가 0이 아닌 세로 크기 조정을 지정하는지 확인합니다.

```
BOOL IsVertical() const
```

## <a name="return-value"></a>반환 값

`SizeSettings` 개체가 0이 아닌 세로 크기 조정을 지정하면 TRUE입니다.

##  <a name="sizevertical"></a>  CMFCDynamicLayout::SizeVertical

가져옵니다를 [SizeSettings](#sizesettings_structure) 얼마나 많은 자식 컨트롤이 세로로 조정 하 사용자가 호스팅 창의 크기 조정 정의입니다.

```
static SizeSettings SizeVertical(int nRatio);
```

### <a name="parameters"></a>매개 변수

*nRatio*<br/>
사용자가 호스트 창 크기를 조정할 때 자식 컨트롤의 크기가 세로로 얼마나 조정되는지를 백분율로 정의합니다.

### <a name="return-value"></a>반환 값

A [SizeSettings](#sizesettings_structure) 요청 된 크기 비율을 캡슐화 하는 값입니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)
