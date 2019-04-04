---
title: CMFCToolBarComboBoxButton 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarComboBoxButton
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::AddItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::AddSortedItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::Compare
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::CreateEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::DeleteItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::FindItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetByCmd
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetComboBox
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCount
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCountAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCurSel
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCurSelAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetEditCtrl
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemData
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemDataAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemDataPtrAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetText
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetTextAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::IsCenterVert
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::IsFlatMode
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::RemoveAllItems
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SelectItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SelectItemAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SetCenterVert
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SetDropDownHeight
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SetFlatMode
helpviewer_keywords:
- CMFCToolBarComboBoxButton [MFC], CMFCToolBarComboBoxButton
- CMFCToolBarComboBoxButton [MFC], AddItem
- CMFCToolBarComboBoxButton [MFC], AddSortedItem
- CMFCToolBarComboBoxButton [MFC], Compare
- CMFCToolBarComboBoxButton [MFC], CreateEdit
- CMFCToolBarComboBoxButton [MFC], DeleteItem
- CMFCToolBarComboBoxButton [MFC], FindItem
- CMFCToolBarComboBoxButton [MFC], GetByCmd
- CMFCToolBarComboBoxButton [MFC], GetComboBox
- CMFCToolBarComboBoxButton [MFC], GetCount
- CMFCToolBarComboBoxButton [MFC], GetCountAll
- CMFCToolBarComboBoxButton [MFC], GetCurSel
- CMFCToolBarComboBoxButton [MFC], GetCurSelAll
- CMFCToolBarComboBoxButton [MFC], GetEditCtrl
- CMFCToolBarComboBoxButton [MFC], GetItem
- CMFCToolBarComboBoxButton [MFC], GetItemAll
- CMFCToolBarComboBoxButton [MFC], GetItemData
- CMFCToolBarComboBoxButton [MFC], GetItemDataAll
- CMFCToolBarComboBoxButton [MFC], GetItemDataPtrAll
- CMFCToolBarComboBoxButton [MFC], GetText
- CMFCToolBarComboBoxButton [MFC], GetTextAll
- CMFCToolBarComboBoxButton [MFC], IsCenterVert
- CMFCToolBarComboBoxButton [MFC], IsFlatMode
- CMFCToolBarComboBoxButton [MFC], RemoveAllItems
- CMFCToolBarComboBoxButton [MFC], SelectItem
- CMFCToolBarComboBoxButton [MFC], SelectItemAll
- CMFCToolBarComboBoxButton [MFC], SetCenterVert
- CMFCToolBarComboBoxButton [MFC], SetDropDownHeight
- CMFCToolBarComboBoxButton [MFC], SetFlatMode
ms.assetid: 32fa39f7-8e4e-4f0a-a31d-7b540d969a6c
ms.openlocfilehash: e3c124103aa95d9db5095e438a6b21d46c7cb35d
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58772074"
---
# <a name="cmfctoolbarcomboboxbutton-class"></a>CMFCToolBarComboBoxButton 클래스

콤보 상자 컨트롤을 포함 하는 도구 모음 단추 ( [CComboBox 클래스](../../mfc/reference/ccombobox-class.md)).

## <a name="syntax"></a>구문

```
class CMFCToolBarComboBoxButton : public CMFCToolBarButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton](#cmfctoolbarcomboboxbutton)|`CMFCToolBarComboBoxButton`를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCToolBarComboBoxButton::AddItem](#additem)|콤보 상자 목록 끝에 항목을 추가 합니다.|
|[CMFCToolBarComboBoxButton::AddSortedItem](#addsorteditem)|콤보 상자 목록에 항목을 추가 합니다. 목록에서 항목의 순서 된 `Compare`합니다.|
|[CMFCToolBarComboBoxButton::Compare](#compare)|두 항목을 비교합니다. 호출 정렬 하는 항목 `AddSortedItems` 콤보 상자 목록에 추가 합니다.|
|[CMFCToolBarComboBoxButton::CreateEdit](#createedit)|콤보 상자 단추에 대해 새 편집 컨트롤을 만듭니다.|
|[CMFCToolBarComboBoxButton::DeleteItem](#deleteitem)|콤보 상자 목록에서 항목을 삭제합니다.|
|[CMFCToolBarComboBoxButton::FindItem](#finditem)|지정된 된 문자열을 포함 하는 항목의 인덱스를 반환 합니다.|
|[CMFCToolBarComboBoxButton::GetByCmd](#getbycmd)|지정 된 명령 ID 사용 하 여 콤보 상자 단추에 대 한 포인터를 반환합니다.|
|[CMFCToolBarComboBoxButton::GetComboBox](#getcombobox)|콤보 상자 단추에 포함 된 콤보 상자 컨트롤에 대 한 포인터를 반환 합니다.|
|[CMFCToolBarComboBoxButton::GetCount](#getcount)|상자 목록 콤보에서 항목 수를 반환 합니다.|
|[CMFCToolBarComboBoxButton::GetCountAll](#getcountall)|콤보 상자 단추를 지정 된 명령 ID를 가진 찾습니다. 해당 단추 상자 목록을 콤보에서 항목 수를 반환합니다.|
|[CMFCToolBarComboBoxButton::GetCurSel](#getcursel)|상자 목록 콤보에서 선택한 항목의 인덱스를 반환 합니다.|
|[CMFCToolBarComboBoxButton::GetCurSelAll](#getcurselall)|콤보 상자 단추를 지정 된 명령 ID가 해당 단추의 상자 목록 콤보에서 선택한 항목의 인덱스를 반환 하는 찾습니다.|
|[CMFCToolBarComboBoxButton::GetEditCtrl](#geteditctrl)|콤보 상자 단추에 포함 된 편집 컨트롤에 대 한 포인터를 반환 합니다.|
|[CMFCToolBarComboBoxButton::GetItem](#getitem)|상자 목록을 콤보에서 지정된 된 인덱스와 연결 된 문자열을 반환 합니다.|
|[CMFCToolBarComboBoxButton::GetItemAll](#getitemall)|콤보 상자 단추를 지정 된 명령 ID가 해당 단추의 콤보 상자 목록에서 인덱스와 연결 된 문자열을 반환 하를 찾습니다.|
|[CMFCToolBarComboBoxButton::GetItemData](#getitemdata)|상자 목록을 콤보에서 지정된 된 인덱스와 연결 된 32 비트 값을 반환 합니다.|
|[CMFCToolBarComboBoxButton::GetItemDataAll](#getitemdataall)|콤보 상자 단추를 지정 된 명령 ID가 해당 단추의 콤보 상자 목록에서 인덱스와 연결 된 32 비트 값을 반환 하는 찾습니다.|
|[CMFCToolBarComboBoxButton::GetItemDataPtrAll](#getitemdataptrall)|콤보 상자 단추를 지정 된 명령 ID를 가진 찾습니다. 검색 된 32 비트 값 목록의 콤보 상자 단추 및 32 비트 값 포인터를 반환 하는 인덱스를 연결 합니다.|
|[CMFCToolBarComboBoxButton::GetText](#gettext)|콤보 상자의 편집 컨트롤에서 텍스트를 반환합니다.|
|[CMFCToolBarComboBoxButton::GetTextAll](#gettextall)|콤보 상자 단추를 지정 된 명령 ID가 해당 단추의 편집 컨트롤에서 텍스트를 반환 하는 찾습니다.|
|[CMFCToolBarComboBoxButton::IsCenterVert](#iscentervert)|응용 프로그램에서 콤보 상자 단추는 가운데 또는 도구 모음의 위쪽에 맞춰집니다 여부를 결정 합니다.|
|[CMFCToolBarComboBoxButton::IsFlatMode](#isflatmode)|응용 프로그램에서 콤보 상자 단추를 평면 모양으로 표시 여부를 확인 합니다.|
|[CMFCToolBarComboBoxButton::RemoveAllItems](#removeallitems)|제거 목록에서 항목을 모두 상자 및 콤보 상자 컨트롤을 편집 합니다.|
|[CMFCToolBarComboBoxButton::SelectItem](#selectitem)|해당 인덱스, 32 비트 값 또는 문자열에 따라 콤보 상자의 항목을 선택 하 고 선택 영역에 대 한 콤보 상자 컨트롤에 알립니다.|
|[CMFCToolBarComboBoxButton::SelectItemAll](#selectitemall)|콤보 상자 단추를 지정 된 명령 ID를 가진 찾습니다. 호출 `SelectItem` 해당 문자열, 인덱스 또는 32 비트 값에 따라 해당 단추의 콤보 상자에서 항목을 선택 합니다.|
|[CMFCToolBarComboBoxButton::SetCenterVert](#setcentervert)|응용 프로그램에서 콤보 상자 단추 세로 가운데 맞춤 되는지 또는 도구 모음의 위쪽에 맞춰집니다를 지정 합니다.|
|[CMFCToolBarComboBoxButton::SetDropDownHeight](#setdropdownheight)|드롭다운 목록 상자의 높이 설정합니다.|
|[CMFCToolBarComboBoxButton::SetFlatMode](#setflatmode)|응용 프로그램에서 콤보 상자 단추를 평면 모양으로 표시 여부를 지정 합니다.|

## <a name="remarks"></a>설명

도구 모음에 콤보 상자 단추를 추가 하려면 다음이 단계를 수행 합니다.

1. 부모 도구 모음 리소스의 단추에 대한 더미 리소스 ID를 예약합니다.

2. 생성 된 `CMFCToolBarComboBoxButton` 개체입니다.

3. AFX_WM_RESETTOOLBAR 메시지를 처리 하는 메시지 처리기에서 더미 단추를 새 콤보 상자 단추를 사용 하 여 바꿉니다 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)합니다.

자세한 내용은 [연습: 도구 모음에 컨트롤 넣기](../../mfc/walkthrough-putting-controls-on-toolbars.md)합니다. 콤보 상자 도구 모음 단추의 예 VisualStudioDemo 예제 프로젝트를 참조 하세요.

## <a name="example"></a>예제

다음 예제에서는 `CMFCToolBarComboBoxButton` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 이 예제에서는 편집 및 콤보 상자를 사용 하도록 설정, 응용 프로그램에서 세로 위치 콤보 상자 단추를 설정, 놓을 때 목록 상자의 높이 설정, 응용 프로그램에서 콤보 상자 단추의 평면 스타일 모양을 설정 하는 방법을 보여 줍니다. 및 상자 단추 콤보의 편집 상자에 텍스트를 설정 합니다. 이 코드 조각은의 일부인 합니다 [Visual Studio 데모 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_VisualStudioDemo#36](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_1.cpp)]
[!code-cpp[NVC_MFC_VisualStudioDemo#37](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxtoolbarcomboboxbutton.h

##  <a name="additem"></a>  CMFCToolBarComboBoxButton::AddItem

목록 상자에 고유한 항목을 추가합니다.

```
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>매개 변수

*lpszItem*<br/>
[in] 목록 상자에 추가할 항목의 텍스트입니다.

*dwData*<br/>
[in] 목록 상자에 추가할 항목에 연결 된 데이터입니다.

### <a name="return-value"></a>반환 값

목록 상자에 있는 마지막 항목의 인덱스입니다.

### <a name="remarks"></a>설명

목록 상자 스타일 정렬 될 때이 메서드를 사용 하지 마십시오.

항목 텍스트를 목록 상자에 이미 있으면 기존 항목과 새 데이터가 저장 됩니다. 항목에 대 한 검색은 대/소문자 구분 합니다.

##  <a name="addsorteditem"></a>  CMFCToolBarComboBoxButton::AddSortedItem

정의 된 순서 대로 목록 상자에 항목을 추가 합니다 [비교](#compare) 메서드.

```
virtual INT_PTR AddSortedItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>매개 변수

*lpszItem*<br/>
[in] 목록 상자에 추가할 항목의 텍스트입니다.

*dwData*<br/>
[in] 목록 상자에 추가할 항목에 연결 된 데이터입니다.

### <a name="return-value"></a>반환 값

목록 상자에 추가 된 항목의 인덱스입니다.

### <a name="remarks"></a>설명

이 함수를 사용 하 여 특정 순서에 따라 목록 상자에 항목을 추가 합니다.

##  <a name="canbestretched"></a>  CMFCToolBarComboBoxButton::CanBeStretched

콤보 상자 단추 크기를 변경할 수 있는지 여부를 나타냅니다.

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>반환 값

TRUE 반환.

##  <a name="cmfctoolbarcomboboxbutton"></a>  CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton

생성 된 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) 개체입니다.

```
CMFCToolBarComboBoxButton(
    UINT uiID,
    int iImage,
    DWORD dwStyle=CBS_DROPDOWNLIST,
    int iWidth=0);
```

### <a name="parameters"></a>매개 변수

*uiID*<br/>
[in] 새 단추의 명령 ID입니다.

*iImage*<br/>
[in] 새로 만들기 단추를 사용 하 여 연결 된 이미지의 이미지 인덱스입니다.

*dwStyle*<br/>
[in] 새 단추 스타일입니다.

*iWidth*<br/>
[in] 새 단추의 픽셀 너비입니다.

### <a name="remarks"></a>설명

기본 너비는 150 픽셀입니다.

도구 모음 단추 스타일의 목록을 참조 하세요. [ToolBar 컨트롤 스타일](../../mfc/reference/toolbar-control-styles.md)

##  <a name="cleardata"></a>  CMFCToolBarComboBoxButton::ClearData

사용자 정의 데이터를 삭제 합니다.

```
virtual void ClearData();
```

### <a name="remarks"></a>설명

기본적으로이 메서드는 없습니다. 모든 사용자 정의 데이터를 삭제 하려는 경우에 파생된 클래스에서이 메서드를 재정의 합니다.

##  <a name="compare"></a>  CMFCToolBarComboBoxButton::Compare

두 문자열을 비교합니다.

```
virtual int Compare(
    LPCTSTR lpszItem1,
    LPCTSTR lpszItem2);
```

### <a name="parameters"></a>매개 변수

*lpszItem1*<br/>
[in] 비교할 첫 번째 문자열입니다.

*lpszItem2*<br/>
[in] 비교할 두 번째 문자열입니다.

### <a name="return-value"></a>반환 값

대/소문자 구분 사전적 문자열 간의 관계를 나타내는 값입니다. 다음 표에서 가능한 값을 나열합니다.

|값|설명|
|-----------|-----------------|
|\<0|첫 번째 문자열이 두 번째 인스턴스보다 합니다.|
|0|첫 번째 문자열이 두 번째를 것과 같습니다.|
|>0|첫 번째 문자열이 두 번째 보다 큽니다.|

### <a name="remarks"></a>설명

목록 상자 항목 정렬 되는 방법을 변경 하려면이 메서드를 재정의 합니다.

비교는 대/소문자 구분.

에서만이 메서드는 호출 된 [AddSortedItem](#addsorteditem) 메서드.

##  <a name="copyfrom"></a>  CMFCToolBarComboBoxButton::CopyFrom

지정된 된 상태의 복사 `CMFCToolBarComboBoxButton` 현재 개체입니다.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>매개 변수

*src*<br/>
[in] 원본 `CMFCToolBarComboBoxButton` 개체입니다.

##  <a name="createcombo"></a>  CMFCToolBarComboBoxButton::CreateCombo

콤보 상자 단추에 대 한 새 콤보 상자를 만듭니다.

```
virtual CComboBox* CreateCombo(
    CWnd* pWndParent,
    const CRect& rect);
```

### <a name="parameters"></a>매개 변수

*pWndParent*<br/>
[in] 단추의 부모 창에 대 한 포인터입니다.

*rect*<br/>
[in] 콤보 상자의 경계 사각형입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 새 콤보 상자에 대 한 포인터 그렇지 않으면 NULL입니다.

##  <a name="createedit"></a>  CMFCToolBarComboBoxButton::CreateEdit

콤보 상자 단추에 대해 새 편집 상자를 만듭니다.

```
virtual CMFCToolBarComboBoxEdit* CreateEdit(
    CWnd* pWndParent,
    const CRect& rect,
    DWORD dwEditStyle);
```

### <a name="parameters"></a>매개 변수

*pWndParent*<br/>
[in] 단추의 부모 창에 대 한 포인터입니다.

*rect*<br/>
[in] 새 입력란의 경계 사각형입니다.

*dwEditStyle*<br/>
[in] 새 입력란의 스타일을 제어 합니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 새 편집 상자에 대 한 포인터 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

프레임 워크는 콤보 상자 단추에 대해 새 편집 상자를 만들 때이 메서드를 호출 합니다. 변경 하려면이 메서드를 재정의 하는 방법 [CMFCToolBarComboBoxEdit](../../mfc/reference/cmfctoolbarcomboboxedit-class.md) 만들어집니다.

##  <a name="deleteitem"></a>  CMFCToolBarComboBoxButton::DeleteItem

목록 상자에서 지정된 된 항목을 삭제합니다.

```
BOOL DeleteItem(int iIndex);
BOOL DeleteItem(DWORD_PTR dwData);
  BOOL DeleteItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
[in] 삭제할 항목의 0부터 시작 하는 인덱스입니다.

*dwData*<br/>
[in] 삭제할 항목과 연결 된 데이터입니다.

*lpszText*<br/>
[in] 삭제할 항목의 텍스트입니다. 동일한 텍스트를 가진 여러 항목이 있으면 첫 번째 항목이 삭제 됩니다.

### <a name="return-value"></a>반환 값

항목이 있고 성공적으로 삭제 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="duplicatedata"></a>  CMFCToolBarComboBoxButton::DuplicateData

중복 사용자 정의 데이터입니다.

```
virtual void DuplicateData();
```

### <a name="remarks"></a>설명

기본적으로이 메서드는 없습니다. 모든 사용자 정의 데이터를 복사 하려는 경우에 파생된 클래스에서이 메서드를 재정의 합니다.

##  <a name="enablewindow"></a>  CMFCToolBarComboBoxButton::EnableWindow

사용 하거나 편집 및 콤보 상자를 사용 하지 않도록 설정 합니다.

```
virtual void EnableWindow(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
[in] TRUE는 편집 및 콤보 상자를 사용 하도록 설정 하려면 편집 및 콤보 상자를 사용 하지 않도록 설정 하려면 FALSE입니다.

### <a name="remarks"></a>설명

를 사용할 수 없을 때 컨트롤 없습니다 활성화 되며 사용자 입력을 받아들일 수 없습니다.

##  <a name="exporttomenubutton"></a>  CMFCToolBarComboBoxButton::ExportToMenuButton

복사 콤보 상자 단추 명령을 사용 하 여 지정된 된 메뉴에 응용 프로그램 문자열 테이블에서 문자열 id입니다.

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>매개 변수

*menuButton*<br/>
[out] 메뉴 단추에 대 한 참조입니다.

### <a name="return-value"></a>반환 값

항상 TRUE입니다.

##  <a name="finditem"></a>  CMFCToolBarComboBoxButton::FindItem

지정된 된 문자열을 포함 하는 목록 상자에서 첫 번째 항목의 인덱스를 반환 합니다.

```
int FindItem(LPCTSTR lpszText) const;
```

### <a name="parameters"></a>매개 변수

*lpszText*<br/>
[in] 목록 상자에 검색할 텍스트입니다.

### <a name="return-value"></a>반환 값

항목의 인덱스 또는 CB_ERR 항목이 없는 경우입니다.

### <a name="remarks"></a>설명

##  <a name="getbycmd"></a>  CMFCToolBarComboBoxButton::GetByCmd

지정 된 명령 ID가 있는 콤보 상자 단추에 대 한 포인터를 가져옵니다.

```
static CMFCToolBarComboBoxButton* GetByCmd(
    UINT uiCmd,
    BOOL bIsFocus=FALSE);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
[in] 콤보 상자 단추의 명령 ID입니다.

*bIsFocus*<br/>
[in] 포커스가 있는 단추;만 검색 하려면 true로 설정 모든 단추를 검색 하려면 FALSE입니다.

### <a name="return-value"></a>반환 값

콤보 상자 단추;에 대 한 포인터 또는 단추를 찾을 수 없으면 NULL입니다.

### <a name="remarks"></a>설명

##  <a name="getcombobox"></a>  CMFCToolBarComboBoxButton::GetComboBox

포인터를 반환 콤보 상자에서 콤보 상자 단추입니다.

```
CComboBox* GetComboBox() const;
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [CComboBox 클래스](../../mfc/reference/ccombobox-class.md) 메서드가 성공 하는 경우 개체, 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

##  <a name="getcontextmenuid"></a>  CMFCToolBarComboBoxButton::GetContextMenuID

콤보 상자 단추에 대 한 바로 가기 메뉴 리소스 ID를 가져옵니다.

```
UINT GetContextMenuID();
```

### <a name="return-value"></a>반환 값

바로 가기 메뉴 리소스 id입니다.

##  <a name="getcount"></a>  CMFCToolBarComboBoxButton::GetCount

목록 상자에서 항목 수를 반환합니다.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>반환 값

목록 상자에 있는 항목의 수입니다.

### <a name="remarks"></a>설명

##  <a name="getcountall"></a>  CMFCToolBarComboBoxButton::GetCountAll

지정한 명령 ID가 있는 콤보 상자 단추의 목록 상자에서 항목의 수를 가져옵니다.

```
static int GetCountAll(UINT uiCmd);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
[in] 콤보 상자 단추의 명령 ID입니다.

### <a name="return-value"></a>반환 값

목록 상자에서 항목 수 그렇지 않으면 CB_ERR 콤보 상자 단추 경우 찾을 수 없습니다.

### <a name="remarks"></a>설명

##  <a name="getcursel"></a>  CMFCToolBarComboBoxButton::GetCurSel

목록 상자에서 현재 선택한 항목의 인덱스를 가져옵니다.

```
int GetCurSel() const;
```

### <a name="return-value"></a>반환 값

목록 상자; 현재 선택된 된 항목의 인덱스 또는 CB_ERR 없는 항목을 선택 합니다.

### <a name="remarks"></a>설명

목록 상자 인덱스는 0부터 시작 합니다.

##  <a name="getcurselall"></a>  CMFCToolBarComboBoxButton::GetCurSelAll

지정 된 명령 ID가 있는 상자 단추는 콤보 목록 상자에서 현재 선택한 항목의 인덱스를 반환

```
static int GetCurSelAll(UINT uiCmd);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
[in] 콤보 상자 단추의 명령 ID입니다.

### <a name="return-value"></a>반환 값

목록 상자; 현재 선택된 된 항목의 인덱스 그렇지 않은 경우 선택 된 항목이 있으면 CB_ERR 또는 콤보 상자 단추가 없습니다.

### <a name="remarks"></a>설명

목록 상자 인덱스는 0부터 시작 합니다.

##  <a name="geteditctrl"></a>  CMFCToolBarComboBoxButton::GetEditCtrl

포인터를 반환 편집 상자에서 콤보 상자 단추입니다.

```
virtual CEdit* GetEditCtrl();
```

### <a name="return-value"></a>반환 값

메서드가 성공 하면 입력란에 대 한 포인터 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

##  <a name="gethwnd"></a>  CMFCToolBarComboBoxButton::GetHwnd

콤보 상자에 대 한 창 핸들을 반환합니다.

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>반환 값

창 핸들 또는 콤보 상자는 창 개체와 연결 되지 않은 경우 NULL입니다.

##  <a name="getitem"></a>  CMFCToolBarComboBoxButton::GetItem

목록 상자에서 지정된 된 인덱스에서 항목을 사용 하 여 연결 문자열을 반환 합니다.

```
LPCTSTR GetItem(int iIndex=-1) const;
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
[in] 목록 상자에 있는 항목의 0부터 시작 인덱스입니다.

### <a name="return-value"></a>반환 값

항목을 사용 하 여 연결 문자열에 대 한 포인터 그렇지 않은 경우 인덱스 매개 변수가 유효 하지 않은 경우 또는 인덱스 매개 변수가-1이 고 콤보 상자에서 선택한 항목이 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

-1 인덱스 매개 변수는 현재 선택 된 항목의 문자열을 반환 합니다.

##  <a name="getitemall"></a>  CMFCToolBarComboBoxButton::GetItemAll

지정한 명령 ID가 있는 콤보 상자 단추의 목록 상자에서 지정된 된 인덱스에서 항목을 사용 하 여 연결 된 문자열을 반환 합니다.

```
static LPCTSTR GetItemAll(
    UINT uiCmd,
    int iIndex=-1);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
[in] 콤보 상자 단추의 명령 ID입니다.

*iIndex*<br/>
[in] 목록 상자에 있는 항목의 0부터 시작 하는 인덱스입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 항목의 문자열에 대 한 포인터 콤보 상자 단추 발견 되지 않으면이 고, 그렇지 인덱스가 유효 하지 않은 경우 NULL을 여부나 인덱스가-1 및 콤보 상자에서 선택한 항목이 없습니다.

### <a name="remarks"></a>설명

현재 선택 된 항목의 문자열을 반환 하는 인덱스 값이-1입니다.

##  <a name="getitemdata"></a>  CMFCToolBarComboBoxButton::GetItemData

목록 상자에서 지정한 인덱스에서 항목에 연결 된 데이터를 반환 합니다.

```
DWORD_PTR GetItemData(int iIndex=-1) const;
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
[in] 목록 상자에 있는 항목의 0부터 시작 하는 인덱스입니다.

### <a name="return-value"></a>반환 값

항목과 연결 된 데이터 이거나 항목이 없는 경우 0입니다.

### <a name="remarks"></a>설명

-1 인덱스 매개 변수는 현재 선택 된 항목과 연결 된 데이터를 반환 합니다.

##  <a name="getitemdataall"></a>  CMFCToolBarComboBoxButton::GetItemDataAll

특정 명령 ID가 있는 콤보 상자 단추의 목록 상자에서 지정한 인덱스에서 항목에 연결 된 데이터를 반환 합니다.

```
static DWORD_PTR GetItemDataAll(
    UINT uiCmd,
    int iIndex=-1);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
[in] 콤보 상자 단추의 명령 ID입니다.

*iIndex*<br/>
[in] 목록 상자에 있는 항목의 0부터 시작 하는 인덱스입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 항목과 연결 된 데이터 그렇지 않은 경우 지정된 된 인덱스 유효 하지 않은 경우 0 또는 콤보 상자 단추 경우 CB_ERR가 없습니다.

### <a name="remarks"></a>설명

-1 인덱스 매개 변수는 현재 선택 된 항목과 연결 된 데이터를 반환 합니다.

##  <a name="getitemdataptrall"></a>  CMFCToolBarComboBoxButton::GetItemDataPtrAll

특정 명령 ID가 있는 콤보 상자 단추의 목록 상자에서 지정한 인덱스에서 항목에 연결 된 데이터를 반환 합니다. 이 데이터 포인터로 반환 됩니다.

```
static void* GetItemDataPtrAll(
    UINT uiCmd,
    int iIndex=-1);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
[in] 콤보 상자 단추의 명령 ID입니다.

*iIndex*<br/>
[in] 목록 상자에 있는 항목의 0부터 시작 하는 인덱스입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 항목과 연결 된 포인터 그렇지 않으면 오류가 없으면-1 발생 하거나 콤보 상자 단추 경우 NULL을 찾을 수 없습니다.

### <a name="remarks"></a>설명

##  <a name="getprompt"></a>  CMFCToolBarComboBoxButton::GetPrompt

콤보 상자 단추 프롬프트 문자열을 반환합니다.

```
virtual CString GetPrompt() const;
```

### <a name="return-value"></a>반환 값

프롬프트 문자열입니다.

### <a name="remarks"></a>설명

이 메서드가 현재 구현 되지 않습니다.

##  <a name="gettext"></a>  CMFCToolBarComboBoxButton::GetText

편집 상자에 텍스트를 가져옵니다.

```
LPCTSTR GetText() const;
```

### <a name="return-value"></a>반환 값

입력란 텍스트입니다.

### <a name="remarks"></a>설명

##  <a name="gettextall"></a>  CMFCToolBarComboBoxButton::GetTextAll

지정 된 명령 ID가 있는 콤보 상자 단추의 편집 상자에 텍스트를 가져옵니다.

```
static LPCTSTR GetTextAll(UINT uiCmd);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
[in] 특정 콤보 상자 단추의 명령 ID입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 입력란의 텍스트 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

##  <a name="hasfocus"></a>  CMFCToolBarComboBoxButton::HasFocus

콤보 상자에서 현재 포커스를가지고 있는지 여부를 나타냅니다.

```
virtual BOOL HasFocus() const;
```

### <a name="return-value"></a>반환 값

콤보 상자의 현재 포커스가; 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 또한 콤보 상자의 모든 자식 창에 현재 포커스를가지고 있으면 TRUE를 반환 합니다.

##  <a name="iscentervert"></a>  CMFCToolBarComboBoxButton::IsCenterVert

응용 프로그램에서 콤보 상자 단추의 세로 위치를 반환합니다.

```
static BOOL IsCenterVert();
```

### <a name="return-value"></a>반환 값

TRUE 이면 단추 가운데에 배치 됩니다. FALSE 이면 단추 위쪽에 맞춥니다.

### <a name="remarks"></a>설명

##  <a name="isflatmode"></a>  CMFCToolBarComboBoxButton::IsFlatMode

응용 프로그램에서 콤보 상자 단추의 평면 스타일 모양을 반환합니다.

```
static BOOL IsFlatMode();
```

### <a name="return-value"></a>반환 값

단추를 평면 스타일; 경우 TRUE 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

콤보 상자 단추에 대 한 기본 평면 스타일은 FALSE입니다.

##  <a name="isownerof"></a>  CMFCToolBarComboBoxButton::IsOwnerOf

지정된 된 핸들 콤보 상자 단추 또는 해당 자식 중 하나를 사용 하 여 연결 되는지 여부를 나타냅니다.

```
virtual BOOL IsOwnerOf(HWND hwnd);
```

### <a name="parameters"></a>매개 변수

*hwnd*<br/>
[in] 창 핸들입니다.

### <a name="return-value"></a>반환 값

핸들이 콤보 상자 단추 또는 해당 자식; 중 하나를 사용 하 여 연결 된 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="isribbonbutton"></a>  CMFCToolBarComboBoxButton::IsRibbonButton

콤보 상자 단추를 리본 패널에 있는지 여부를 나타냅니다.

```
BOOL IsRibbonButton() const;
```

### <a name="return-value"></a>반환 값

항상 FALSE입니다.

### <a name="remarks"></a>설명

기본적으로이 메서드는 항상 반환 FALSE, 즉, 콤보 상자 단추를 리본 패널에 표시 되지 않습니다.

##  <a name="iswindowvisible"></a>  CMFCToolBarComboBoxButton::IsWindowVisible

상자 단추를 콤보의 표시 여부 상태를 반환합니다.

```
virtual BOOL IsWindowVisible();
```

### <a name="return-value"></a>반환 값

콤보 상자 단추의 표시 여부 상태입니다.

##  <a name="notifycommand"></a>  CMFCToolBarComboBoxButton::NotifyCommand

콤보 상자 단추 메시지를 처리 하는지 여부를 나타냅니다.

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>매개 변수

*iNotifyCode*<br/>
[in] 명령과 사용 하 여 연결 된 알림 메시지입니다.

### <a name="return-value"></a>반환 값

여부 콤보 상자 단추 메시지를 처리 합니다.

##  <a name="onaddtocustomizepage"></a>  CMFCToolBarComboBoxButton::OnAddToCustomizePage

단추를 추가할 때 프레임 워크에서 호출 된 **사용자 지정** 대화 상자.

```
virtual void OnAddToCustomizePage();
```

##  <a name="oncalculatesize"></a>  CMFCToolBarComboBoxButton::OnCalculateSize

단추의 크기를 계산 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual SIZE OnCalculateSize(
    CDC* pDC,
    const CSize& sizeDefault,
    BOOL bHorz);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 콤보 상자 단추를 표시 하는 장치 컨텍스트.

*sizeDefault*<br/>
[in] 콤보 상자 단추의 기본 크기입니다.

*bHorz*<br/>
[in] 부모 도구 모음 도킹 상태입니다. 도구 모음 세로로 도킹 되 면 도구 모음은 가로 및 FALSE에 도킹 되 면 TRUE입니다.

### <a name="return-value"></a>반환 값

`SIZE` 콤보 상자 단추 픽셀에서의 크기를 포함 하는 구조입니다.

##  <a name="onchangeparentwnd"></a>  CMFCToolBarComboBoxButton::OnChangeParentWnd

새 도구 모음에 콤보 상자 단추를 삽입할 때 프레임 워크에서 호출 됩니다.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>매개 변수

*pWndParent*<br/>
[in] 새 부모 도구 모음에 대 한 포인터입니다.

##  <a name="onclick"></a>  CMFCToolBarComboBoxButton::OnClick

콤보 상자 단추를 클릭할 때 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
[in] 콤보 상자 단추의 부모 창에 대 한 포인터입니다.

*bDelay*<br/>
[in] 파생된 클래스에서 사용 하기 위해 예약 되어 있습니다.

### <a name="return-value"></a>반환 값

메서드는 이벤트를 처리 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="onctlcolor"></a>  CMFCToolBarComboBoxButton::OnCtlColor

사용자의 콤보 상자 단추 색을 설정 하려면 부모 도구 모음 색을 변경 하는 경우 프레임 워크에서 호출 됩니다.

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 콤보 상자 단추를 표시 하는 장치 컨텍스트.

*nCtlColor*<br/>
[in] 사용 되지 않습니다.

### <a name="return-value"></a>반환 값

프레임 워크를 사용 하 여 콤보 상자 단추의 배경을 칠하는 브러시에 대 한 핸들입니다.

### <a name="remarks"></a>설명

이 메서드는 또한 콤보 상자 단추 텍스트 색을 설정합니다.

##  <a name="ondraw"></a>  CMFCToolBarComboBoxButton::OnDraw

지정 된 스타일 및 옵션을 사용 하 여 콤보 상자 단추를 그리기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    CMFCToolBarImages* pImages,
    BOOL bHorz = TRUE,
    BOOL bCustomizeMode = FALSE,
    BOOL bHighlight = FALSE,
    BOOL bDrawBorder = TRUE,
    BOOL bGrayDisabledButtons = TRUE);
```

### <a name="parameters"></a>매개 변수

*Pdc*<br/>
[in] 단추를 표시 하는 장치 컨텍스트.

*rect*<br/>
[in] 단추의 경계 사각형입니다.

*pImages*<br/>
[in] 단추와 연결 된 이미지의 컬렉션입니다.

*bHorz*<br/>
[in] 부모 도구 모음 도킹 상태입니다. 도구 모음 세로로 도킹 되 면 도구 모음은 가로 및 FALSE에 도킹 되 면 TRUE입니다.

*bCustomizeMode*<br/>
[in] 응용 프로그램에서 사용자 지정 모드 인지 여부입니다.

*bHighlight*<br/>
[in] 콤보 상자 단추를 강조 표시를 그릴 것인지 지정 합니다.

*bDrawBorder*<br/>
[in] 테두리가 있는 콤보 상자 단추를 그리기 위한 것인지 지정 합니다.

*bGrayDisabledButtons*<br/>
[in] 그리기 true로 설정 하면 비활성화 된 단추가; 음영 처리 비활성된 이미지 컬렉션을 사용 하려면 FALSE입니다.

##  <a name="ondrawoncustomizelist"></a>  CMFCToolBarComboBoxButton::OnDrawOnCustomizeList

콤보 상자 단추를 그리기 위해 프레임 워크에서 호출 합니다 **명령** 창 합니다 **사용자 지정** 대화 상자.

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 콤보 상자 단추를 표시 하는 장치 컨텍스트.

*rect*<br/>
[in] 콤보 상자 단추의 경계 사각형입니다.

*bSelected*<br/>
[in] TRUE 이면 콤보 상자 단추를 선택 합니다. 그렇지 않으면 FALSE입니다.

### <a name="return-value"></a>반환 값

콤보 상자 단추에 픽셀에서 너비입니다.

##  <a name="onglobalfontschanged"></a>  CMFCToolBarComboBoxButton::OnGlobalFontsChanged

응용 프로그램 글꼴이 변경 될 때의 콤보 상자 단추 글꼴을 설정 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnGlobalFontsChanged();
```

##  <a name="onmove"></a>  CMFCToolBarComboBoxButton::OnMove

부모 도구 모음으로 이동 하는 경우 콤보 상자 단추 위치를 변경 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnMove();
```

##  <a name="onshow"></a>  CMFCToolBarComboBoxButton::OnShow

콤보 상자 단추를 숨기 거 나 표시 하는 경우 프레임 워크에서 호출 됩니다.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>매개 변수

*bShow*<br/>
[in] 콤보 상자 단추를 표시 하거나 숨기려면 여부입니다.

##  <a name="onsize"></a>  CMFCToolBarComboBoxButton::OnSize

부모 도구 모음 크기를 변경 하는 경우 콤보 상자 단추의 크기를 변경 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>매개 변수

*iSize*<br/>
[in] 콤보 상자 단추 새 너비입니다.

##  <a name="onupdatetooltip"></a>  CMFCToolBarComboBoxButton::OnUpdateToolTip

사용자 도구 설명 콤보 상자 단추에 대 한 변경 될 때 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,
    int iButtonIndex,
    CToolTipCtrl& wndToolTip,
    CString& str);
```

### <a name="parameters"></a>매개 변수

*pWndParent*<br/>
[in] 콤보 상자 단추에 대 한 부모 창에 대 한 포인터입니다.

*iButtonIndex*<br/>
[in] 콤보 상자 단추의 ID입니다.

*wndToolTip*<br/>
[in] 콤보 상자 단추를 사용 하 여 연결할 도구 설명입니다.

*str*<br/>
[in] 도구 설명 텍스트입니다.

### <a name="return-value"></a>반환 값

메서드는 이벤트를 처리 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="removeallitems"></a>  CMFCToolBarComboBoxButton::RemoveAllItems

목록 및 편집 상자에서 모든 항목을 삭제합니다.

```
void RemoveAllItems();
```

### <a name="remarks"></a>설명

제거 목록에서 항목을 모두 상자 및 콤보 상자 컨트롤을 편집 합니다.

##  <a name="selectitem"></a>  CMFCToolBarComboBoxButton::SelectItem

목록 상자에서 항목을 선택합니다.

```
BOOL SelectItem(
    int iIndex,
    BOOL bNotify=TRUE);

BOOL SelectItem(DWORD_PTR dwData);
BOOL SelectItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
[in] 목록 상자에 있는 항목의 0부터 시작 하는 인덱스입니다.

*bNotify*<br/>
[in] 에 게 알리려면 콤보 상자 단추를 선택 합니다. 그렇지 않으면 FALSE입니다.

*dwData*<br/>
[in] 목록 상자에서 항목에 연결 된 데이터입니다.

*lpszText*<br/>
[in] 목록 상자에 있는 항목의 텍스트입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="selectitemall"></a>  CMFCToolBarComboBoxButton::SelectItemAll

지정 된 명령 ID가 있는 콤보 상자 단추의 목록 상자에서 항목을 선택 합니다.

```
static BOOL SelectItemAll(
    UINT uiCmd,
    int iIndex);

static BOOL SelectItemAll(
    UINT uiCmd,
    DWORD_PTR dwData);

static BOOL SelectItemAll(
    UINT uiCmd,
    LPCTSTR lpszText);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
[in] 목록 상자를 포함 하는 콤보 상자 단추의 명령 ID입니다.

*iIndex*<br/>
[in] 목록 상자에서 항목의 0부터 시작 하는 인덱스입니다. 값이-1 목록 상자에서 모든 현재 선택 영역을 제거 하 고 편집 상자를 지웁니다.

*dwData*<br/>
[in] 목록 상자에 있는 항목의 데이터입니다.

*lpszText*<br/>
[in] 목록 상자에 있는 항목의 텍스트입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="serialize"></a>  CMFCToolBarComboBoxButton::Serialize

보관 파일에서이 개체를 읽거나 보관 파일에 씁니다.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>매개 변수

*ar*<br/>
[out에서] `CArchive` serialize 할 개체입니다.

### <a name="remarks"></a>설명

설정에는 `CArchive` 개체가 있는지 여부를 확인할이 메서드를 읽습니다 보관 파일에 씁니다.

##  <a name="setaccdata"></a>  CMFCToolBarComboBoxButton::SetACCData

지정 된 채웁니다 `CAccessibilityData` 콤보 상자 단추에서 내게 필요한 옵션 데이터를 사용 하 여 개체입니다.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>매개 변수

*pParent*<br/>
[in] 콤보 상자 단추의 부모 창입니다.

*data*<br/>
[out] `CAccessibilityData` 콤보 상자 단추에서 내게 필요한 옵션 데이터를 받는 개체입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="setcentervert"></a>  CMFCToolBarComboBoxButton::SetCenterVert

응용 프로그램에서 콤보 상자 단추의 세로 위치를 설정합니다.

```
static void SetCenterVert(BOOL bCenterVert=TRUE);
```

### <a name="parameters"></a>매개 변수

*bCenterVert*<br/>
[in] Center; 도구 모음에서 콤보 상자 단추를 true로 설정 하면 콤보 상자 단추를 도구 모음의 위쪽을 정렬 하려면 FALSE입니다.

### <a name="remarks"></a>설명

기본적으로 콤보 상자 단추는 위쪽에 정렬 됩니다.

##  <a name="setcontextmenuid"></a>  CMFCToolBarComboBoxButton::SetContextMenuID

콤보 상자 단추 바로 가기 메뉴 리소스 ID를 설정합니다.

```
void SetContextMenuID(UINT uiResID);
```

### <a name="parameters"></a>매개 변수

*uiResID*<br/>
[in] 바로 가기 메뉴 리소스 id입니다.

##  <a name="setdropdownheight"></a>  CMFCToolBarComboBoxButton::SetDropDownHeight

놓을 때 목록 상자의 높이 설정 합니다.

```
void SetDropDownHeight(int nHeight);
```

### <a name="parameters"></a>매개 변수

*nHeight*<br/>
[in] 목록 상자의 픽셀 높이입니다.

### <a name="remarks"></a>설명

기본 높이 150 픽셀입니다.

##  <a name="setflatmode"></a>  CMFCToolBarComboBoxButton::SetFlatMode

응용 프로그램의 평면 스타일 모양을 콤보 상자 단추를 설정합니다.

```
static void SetFlatMode(BOOL bFlat=TRUE);
```

### <a name="parameters"></a>매개 변수

*bFlat*<br/>
[in] 평면 스타일 모양을;에 대해 TRUE 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

콤보 상자 단추에 대 한 기본 평면 스타일은 FALSE입니다.

##  <a name="setstyle"></a>  CMFCToolBarComboBoxButton::SetStyle

상자 단추 콤보에 대 한 지정된 된 스타일을 설정 하 고 사용 하지 않는 경우 컨트롤을 다시 그립니다.

```
virtual void SetStyle(UINT nStyle);
```

### <a name="parameters"></a>매개 변수

*nStyle*<br/>
[in] 도구 모음 스타일의 비트 조합 (OR)입니다.

### <a name="remarks"></a>설명

도구 모음 단추 스타일의 목록을 참조 하세요. [ToolBar 컨트롤 스타일](../../mfc/reference/toolbar-control-styles.md)

##  <a name="settext"></a>  CMFCToolBarComboBoxButton::SetText

상자 단추 콤보의 편집 상자에 텍스트를 설정 합니다.

```
void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>매개 변수

*lpszText*<br/>
[in] 편집 상자에 텍스트를 포함 하는 문자열에 대 한 포인터입니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarButton 클래스](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CComboBox 클래스](../../mfc/reference/ccombobox-class.md)<br/>
[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[연습: 도구 모음에 컨트롤 넣기](../../mfc/walkthrough-putting-controls-on-toolbars.md)
