---
title: CComboBoxEx 클래스
ms.date: 11/04/2016
f1_keywords:
- CComboBoxEx
- AFXCMN/CComboBoxEx
- AFXCMN/CComboBoxEx::CComboBoxEx
- AFXCMN/CComboBoxEx::Create
- AFXCMN/CComboBoxEx::CreateEx
- AFXCMN/CComboBoxEx::DeleteItem
- AFXCMN/CComboBoxEx::GetComboBoxCtrl
- AFXCMN/CComboBoxEx::GetEditCtrl
- AFXCMN/CComboBoxEx::GetExtendedStyle
- AFXCMN/CComboBoxEx::GetImageList
- AFXCMN/CComboBoxEx::GetItem
- AFXCMN/CComboBoxEx::HasEditChanged
- AFXCMN/CComboBoxEx::InsertItem
- AFXCMN/CComboBoxEx::SetExtendedStyle
- AFXCMN/CComboBoxEx::SetImageList
- AFXCMN/CComboBoxEx::SetItem
- AFXCMN/CComboBoxEx::SetWindowTheme
helpviewer_keywords:
- CComboBoxEx [MFC], CComboBoxEx
- CComboBoxEx [MFC], Create
- CComboBoxEx [MFC], CreateEx
- CComboBoxEx [MFC], DeleteItem
- CComboBoxEx [MFC], GetComboBoxCtrl
- CComboBoxEx [MFC], GetEditCtrl
- CComboBoxEx [MFC], GetExtendedStyle
- CComboBoxEx [MFC], GetImageList
- CComboBoxEx [MFC], GetItem
- CComboBoxEx [MFC], HasEditChanged
- CComboBoxEx [MFC], InsertItem
- CComboBoxEx [MFC], SetExtendedStyle
- CComboBoxEx [MFC], SetImageList
- CComboBoxEx [MFC], SetItem
- CComboBoxEx [MFC], SetWindowTheme
ms.assetid: 33ca960a-2409-478c-84a4-a2ee8ecfe8f7
ms.openlocfilehash: c3fd57510a38d597b827f80ab98a0be280ad31e3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62254100"
---
# <a name="ccomboboxex-class"></a>CComboBoxEx 클래스

이미지 목록에 대한 지원을 제공하여 콤보 상자 컨트롤을 확장합니다.

## <a name="syntax"></a>구문

```
class CComboBoxEx : public CComboBox
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CComboBoxEx::CComboBoxEx](#ccomboboxex)|`CComboBoxEx` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComboBoxEx::Create](#create)|콤보 상자를 만들고 연결 하는 `CComboBoxEx` 개체입니다.|
|[CComboBoxEx::CreateEx](#createex)|지정 된 Windows 확장된 스타일을 사용 하 여 콤보 상자를 만들고 연결 하는 `ComboBoxEx` 개체입니다.|
|[CComboBoxEx::DeleteItem](#deleteitem)|항목을 제거는 `ComboBoxEx` 제어 합니다.|
|[CComboBoxEx::GetComboBoxCtrl](#getcomboboxctrl)|자식 콤보 상자 컨트롤에 대 한 포인터를 검색합니다.|
|[CComboBoxEx::GetEditCtrl](#geteditctrl)|편집 컨트롤 부분에 대 한 핸들을 검색 한 `ComboBoxEx` 제어 합니다.|
|[CComboBoxEx::GetExtendedStyle](#getextendedstyle)|검색에 사용 되는 확장된 스타일을 `ComboBoxEx` 제어 합니다.|
|[CComboBoxEx::GetImageList](#getimagelist)|에 할당 된 이미지 목록에 대 한 포인터를 검색 한 `ComboBoxEx` 제어 합니다.|
|[CComboBoxEx::GetItem](#getitem)|검색 항목에 대 한 정보를 지정 된 `ComboBoxEx` 항목입니다.|
|[CComboBoxEx::HasEditChanged](#haseditchanged)|사용자의 내용이 변경 되었는지 여부를 결정 합니다 `ComboBoxEx` 입력 하 여 컨트롤을 편집 합니다.|
|[CComboBoxEx::InsertItem](#insertitem)|에 새 항목이 삽입 된 `ComboBoxEx` 제어 합니다.|
|[CComboBoxEx::SetExtendedStyle](#setextendedstyle)|설정 내에서 확장된 스타일을 `ComboBoxEx` 제어 합니다.|
|[CComboBoxEx::SetImageList](#setimagelist)|에 대 한 이미지 목록을 설정 하는 `ComboBoxEx` 제어 합니다.|
|[CComboBoxEx::SetItem](#setitem)|항목에 대해 특성을 설정 하는 `ComboBoxEx` 컨트롤입니다.|
|[CComboBoxEx::SetWindowTheme](#setwindowtheme)|비주얼 스타일의 확장 된 콤보 상자 컨트롤을 설정합니다.|

## <a name="remarks"></a>설명

사용 하 여 `CComboBoxEx` 콤보 상자 컨트롤을 만들려면 더 이상 구현 해야 사용자 고유의 이미지 그리기 코드입니다. 대신 `CComboBoxEx` 이미지 목록의 이미지 액세스 합니다.

## <a name="image-list-support"></a>이미지 목록 지원

표준 콤보 상자에서 콤보 상자의 소유자가 소유자 그리기 컨트롤 콤보 상자를 만들어 이미지 그리기를 담당 합니다. 사용 하는 경우 `CComboBoxEx`은 암시적 CBS_OWNERDRAWFIXED 및 CBS_HASSTRINGS 그리기 스타일을 설정할 필요가 없습니다. 그렇지 않으면 그리기 작업을 수행 하는 코드를 작성 해야 합니다. `CComboBoxEx` 컨트롤 항목당 최대 3 개의 이미지를 지원 합니다: 선택 되지 않은 상태 여 서 및 오버레이 이미지에 대 한 선택된 상태에 대 한 하나.

## <a name="styles"></a>스타일

`CComboBoxEx` CBS_SIMPLE, CBS_DROPDOWN, CBS_DROPDOWNLIST, 및 WS_CHILD 스타일을 지원합니다. 창을 만들 때 전달 된 다른 모든 스타일 컨트롤에서 무시 됩니다. 창이 만들어진 후 수 다른 콤보 상자 스타일 호출 하 여 제공 합니다 `CComboBoxEx` 멤버 함수 [SetExtendedStyle](#setextendedstyle)합니다. 이러한 스타일을 사용 하 여 다음을 수행할 수 있습니다.

- 대/소문자 구분 되도록 목록의 문자열 검색을 설정 합니다.

- 콤보 상자 컨트롤 만들기 ('/'), 슬래시를 사용 하는 백슬래시 ('\\'), 및 마침표 ('. ') 단어 구분 기호 문자로 합니다. 이 바로 가기 키 CTRL + 화살표를 사용 하 여 단어를 이동할 수가 있습니다.

- 콤보 상자 컨트롤을 표시 또는 이미지를 표시 하지를 설정 합니다. 이미지가 표시 되 면 콤보 상자는 이미지를 수용 하는 텍스트 들여쓰기를 제거할 수 있습니다.

- 포함 된 광범위 한 콤보 상자 클리핑 하므로 크기 조정 포함 하 여 좁은 콤보 상자 컨트롤을 만듭니다.

이러한 스타일 플래그에 자세히 설명 되어 [CComboBoxEx 사용 하 여](../../mfc/using-ccomboboxex.md)입니다.

## <a name="item-retention-and-callback-item-attributes"></a>보존 및 콜백 항목 특성 항목

항목 및 이미지, 들여쓰기 값 및 텍스트 문자열에 대 한 인덱스와 같은 항목 정보를 Win32 구조에 저장 됩니다 [COMBOBOXEXITEM](/windows/desktop/api/commctrl/ns-commctrl-tagcomboboxexitema)Windows SDK에 설명 된 대로 합니다. 또한 구조에는 콜백 플래그에 해당 하는 멤버가 들어 있습니다.

에 대 한 자세한 개념적 토론을 참조 하세요 [CComboBoxEx 사용 하 여](../../mfc/using-ccomboboxex.md)입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CComboBox](../../mfc/reference/ccombobox-class.md)

`CComboBoxEx`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

##  <a name="ccomboboxex"></a>  CComboBoxEx::CComboBoxEx

만들려면이 멤버 함수 호출을 `CComboBoxEx` 개체입니다.

```
CComboBoxEx();
```

##  <a name="create"></a>  CComboBoxEx::Create

콤보 상자를 만들고 연결 하는 `CComboBoxEx` 개체입니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
콤보 상자에 적용 되는 콤보 상자 스타일의 조합을 지정 합니다. 참조 **주의** 아래 스타일에 대 한 자세한 내용은 합니다.

*rect*<br/>
에 대 한 참조를 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](/previous-versions/dd162897\(v=vs.85\)) 콤보 상자의 크기와 위치는 구조입니다.

*pParentWnd*<br/>
에 대 한 포인터를 [CWnd](../../mfc/reference/cwnd-class.md) 콤보 상자의 부모 창 개체 (일반적으로 `CDialog`). NULL이 아니어야 합니다.

*nID*<br/>
콤보 상자 컨트롤 ID를 지정 합니다.

### <a name="return-value"></a>반환 값

개체가 성공적으로 만들어진 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

만들기는 `CComboBoxEx` 두 단계로 개체:

1. 호출 [CComboBoxEx](#ccomboboxex) 생성 하는 `CComboBoxEx` 개체입니다.

1. 확장 된 Windows 콤보 상자를 만들고에 연결 하는이 멤버 함수를 호출 합니다 `CComboBoxEx` 개체입니다.

호출 하는 경우 `Create`, MFC 공용 컨트롤을 초기화 합니다.

콤보 상자를 만들 때 다음 콤보 상자 스타일 중 일부 또는 모두를 지정할 수 있습니다.

- CBS_SIMPLE

- CBS_DROPDOWN

- CBS_DROPDOWNLIST

- CBS_AUTOHSCROLL

- WS_CHILD

창을 만들 때 전달 된 다른 모든 스타일은 무시 됩니다. `ComboBoxEx` 컨트롤은 또한 추가 기능을 제공 하는 확장된 스타일을 지원 합니다. 이러한 스타일에 설명 되어 있습니다 [ComboBoxEx 컨트롤 확장된 스타일](/windows/desktop/Controls/comboboxex-control-extended-styles), Windows SDK에 있습니다. 호출 하 여 이러한 스타일을 설정 [SetExtendedStyle](#setextendedstyle)합니다.

컨트롤을 사용 하 여 확장된 창 스타일을 사용 하려는 경우 호출할 [CreateEx](#createex) 대신 `Create`합니다.

##  <a name="createex"></a>  CComboBoxEx::CreateEx

확장 된 콤보 상자 컨트롤 (자식 창)을 만들고 사용 하 여 연결 하려면이 함수를 호출 합니다 `CComboBoxEx` 개체입니다.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwExStyle*<br/>
만들려는 컨트롤의 확장된 스타일을 지정 합니다. 확장 된 Windows 스타일의 목록은 참조 하세요. 합니다 *dwExStyle* 에 대 한 매개 변수 [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Windows SDK의 합니다.

*dwStyle*<br/>
콤보 상자 컨트롤의 스타일입니다. 참조 [만들기](#create) 스타일의 목록은 합니다.

*rect*<br/>
에 대 한 참조를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 크기와의 클라이언트 좌표에서 만든 창의 위치를 설명 하는 구조 *pParentWnd*합니다.

*pParentWnd*<br/>
컨트롤의 부모 창에 대 한 포인터입니다.

*nID*<br/>
컨트롤의 자식 창 id입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

사용 하 여 `CreateEx` of `Create` Windows 확장된 스타일 앞으로 지정 된 Windows 확장된 스타일을 적용할 **WS_EX_** 합니다.

`CreateEx` 지정 된 Windows 확장된 스타일을 사용 하 여 컨트롤을 만듭니다 *dwExStyle*합니다. 설정 해야 확장된 스타일 관련 하 여 확장 된 콤보 상자 컨트롤에 [SetExtendedStyle](#setextendedstyle)합니다. 사용 예를 들어 `CreateEx` 이러한 스타일 WS_EX_CONTEXTHELP와 이지만 사용 하 여 `SetExtendedStyle` CBES_EX_CASESENSITIVE로 이러한 스타일을 설정 하려면. 자세한 내용은 참조 항목에서 설명 하는 스타일 [ComboBoxEx 컨트롤 확장 스타일](/windows/desktop/Controls/comboboxex-control-extended-styles) Windows SDK에 있습니다.

##  <a name="deleteitem"></a>  CComboBoxEx::DeleteItem

항목을 제거는 `ComboBoxEx` 제어 합니다.

```
int DeleteItem(int iIndex);
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
제거할 항목의 0부터 시작 인덱스입니다.

### <a name="return-value"></a>반환 값

컨트롤에 남아 있는 항목의 수입니다. 하는 경우 *iIndex* 는 잘못 된 경우 함수 반환 CB_ERR 합니다.

### <a name="remarks"></a>설명

메시지의 기능을 구현 하는이 멤버 함수 [CBEM_DELETEITEM](/windows/desktop/Controls/cbem-deleteitem)Windows SDK에 설명 된 대로 합니다. DeleteItem, 호출 하는 경우는 [WM_NOTIFY](/windows/desktop/controls/wm-notify) CBEN_DELETEITEM 알림 메시지를 부모 창에 보내집니다.

##  <a name="getcomboboxctrl"></a>  CComboBoxEx::GetComboBoxCtrl

내에서 콤보 상자 컨트롤에 대 한 포인터를 가져오려면이 멤버 함수 호출을 `CComboBoxEx` 개체입니다.

```
CComboBox* GetComboBoxCtrl();
```

### <a name="return-value"></a>반환 값

`CComboBox` 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

합니다 `CComboBoxEx` 컨트롤을 캡슐화 하는 부모 창으로 이루어져는 `CComboBox`합니다.

`CComboBox` 반환 값에서 가리키는 개체는 임시 개체 이며 다음 유휴 처리 시간 동안 제거 됩니다.

##  <a name="geteditctrl"></a>  CComboBoxEx::GetEditCtrl

콤보 상자의 편집 컨트롤에 포인터를 얻으려면이 멤버 함수를 호출 합니다.

```
CEdit* GetEditCtrl();
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [CEdit](../../mfc/reference/cedit-class.md) 개체입니다.

### <a name="remarks"></a>설명

`CComboBoxEx` CBS_DROPDOWN 스타일으로 생성 될 때 컨트롤에서 편집 상자를 사용 합니다.

`CEdit` 반환 값에서 가리키는 개체는 임시 개체 이며 다음 유휴 처리 시간 동안 제거 됩니다.

##  <a name="getextendedstyle"></a>  CComboBoxEx::GetExtendedStyle

이 멤버 함수에 사용 된 확장된 스타일을 가져오려면 호출을 `CComboBoxEx` 제어 합니다.

```
DWORD GetExtendedStyle() const;
```

### <a name="return-value"></a>반환 값

콤보 상자 컨트롤에 사용 되는 확장된 스타일을 포함 하는 DWORD 값입니다.

### <a name="remarks"></a>설명

참조 [ComboBoxEx 컨트롤 확장 스타일](/windows/desktop/Controls/comboboxex-control-extended-styles) 이러한 스타일에 대 한 자세한 내용은 Windows SDK에 있습니다.

##  <a name="getimagelist"></a>  CComboBoxEx::GetImageList

사용 하는 이미지 목록에 대 한 포인터를 가져오려면이 멤버 함수 호출을 `CComboBoxEx` 제어 합니다.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [CImageList](../../mfc/reference/cimagelist-class.md) 개체입니다. 실패 한 경우이 멤버 함수는 NULL을 반환 합니다.

### <a name="remarks"></a>설명

`CImageList` 반환 값에서 가리키는 개체는 임시 개체 이며 다음 유휴 처리 시간 동안 제거 됩니다.

##  <a name="getitem"></a>  CComboBoxEx::GetItem

검색 항목에 대 한 정보를 지정 된 `ComboBoxEx` 항목입니다.

```
BOOL GetItem(COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>매개 변수

*pCBItem*<br/>
에 대 한 포인터를 [COMBOBOXEXITEM](/windows/desktop/api/commctrl/ns-commctrl-tagcomboboxexitema) 항목 정보를 받는 구조체입니다.

### <a name="return-value"></a>반환 값

작업에 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

메시지의 기능을 구현 하는이 멤버 함수 [CBEM_GETITEM](/windows/desktop/Controls/cbem-getitem)Windows SDK에 설명 된 대로 합니다.

##  <a name="haseditchanged"></a>  CComboBoxEx::HasEditChanged

사용자의 내용이 변경 되었는지 여부를 결정 합니다 `ComboBoxEx` 입력 하 여 컨트롤을 편집 합니다.

```
BOOL HasEditChanged();
```

### <a name="return-value"></a>반환 값

사용자가 컨트롤의 편집 상자에 입력 한 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

메시지의 기능을 구현 하는이 멤버 함수 [CBEM_HASEDITCHANGED](/windows/desktop/Controls/cbem-haseditchanged)Windows SDK에 설명 된 대로 합니다.

##  <a name="insertitem"></a>  CComboBoxEx::InsertItem

에 새 항목이 삽입 된 `ComboBoxEx` 제어 합니다.

```
int InsertItem(const COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>매개 변수

*pCBItem*<br/>
에 대 한 포인터를 [COMBOBOXEXITEM](/windows/desktop/api/commctrl/ns-commctrl-tagcomboboxexitema) 항목 정보를 받는 구조체입니다. 이 구조는 항목에 대 한 콜백 플래그 값을 포함 합니다.

### <a name="return-value"></a>반환 값

성공할 경우 새 항목이 삽입 된 인덱스 그렇지 않으면-1입니다.

### <a name="remarks"></a>설명

호출 하는 경우 `InsertItem`, a [WM_NOTIFY](/windows/desktop/controls/wm-notify) 메시지 [CBEN_INSERTITEM](/windows/desktop/Controls/cben-insertitem) 부모 창에 알림이 전송 됩니다.

##  <a name="setextendedstyle"></a>  CComboBoxEx::SetExtendedStyle

컨트롤 확장 된 콤보 상자에 사용 된 확장된 스타일을 설정 하려면이 멤버 함수를 호출 합니다.

```
DWORD SetExtendedStyle(
    DWORD dwExMask,
    DWORD dwExStyles);
```

### <a name="parameters"></a>매개 변수

*dwExMask*<br/>
에 스타일을 나타내는 DWORD 값 *dwExStyles* 영향을 받게 될 합니다. 확장 된 스타일에만 *dwExMask* 변경 됩니다. 다른 모든 스타일은 그대로 유지 됩니다. 이 매개 변수가 0 이면 모든 스타일의 경우 *dwExStyles* 영향을 받게 됩니다.

*dwExStyles*<br/>
콤보 상자 컨트롤을 포함 하는 DWORD 값 확장 스타일을 컨트롤에 설정 합니다.

### <a name="return-value"></a>반환 값

컨트롤에 대해 이전에 사용 된 확장된 스타일을 포함 하는 DWORD 값입니다.

### <a name="remarks"></a>설명

참조 [ComboBoxEx 컨트롤 확장 스타일](/windows/desktop/Controls/comboboxex-control-extended-styles) 이러한 스타일에 대 한 자세한 내용은 Windows SDK에 있습니다.

확장된 창 스타일을 사용 하 여 컨트롤 확장 된 콤보 상자를 만들려면 사용 [CreateEx](#createex)합니다.

##  <a name="setimagelist"></a>  CComboBoxEx::SetImageList

에 대 한 이미지 목록을 설정 하는 `ComboBoxEx` 제어 합니다.

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>매개 변수

*pImageList*<br/>
에 대 한 포인터를 `CImageList` 개체를 사용 하 여 이미지를 포함 하는 `CComboBoxEx` 제어 합니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [CImageList](../../mfc/reference/cimagelist-class.md) 이전에 사용 되는 이미지가 포함 된 개체는 `CComboBoxEx` 제어 합니다. 이미지 목록이 없는 이전에 설정 된 경우 NULL입니다.

### <a name="remarks"></a>설명

메시지의 기능을 구현 하는이 멤버 함수 [CBEM_SETIMAGELIST](/windows/desktop/Controls/cbem-setimagelist)Windows SDK에 설명 된 대로 합니다. 기본 편집 컨트롤의 높이 변경 하는 경우 Win32 함수 호출 [SetWindowPos](/windows/desktop/api/winuser/nf-winuser-setwindowpos) 호출한 후 컨트롤 크기를 조정 하려면 `SetImageList`, 또는 제대로 표시 되지 것입니다.

`CImageList` 반환 값에서 가리키는 개체는 임시 개체 이며 다음 유휴 처리 시간 동안 제거 됩니다.

##  <a name="setitem"></a>  CComboBoxEx::SetItem

항목에 대해 특성을 설정 하는 `ComboBoxEx` 컨트롤입니다.

```
BOOL SetItem(const COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>매개 변수

*pCBItem*<br/>
에 대 한 포인터를 [COMBOBOXEXITEM](/windows/desktop/api/commctrl/ns-commctrl-tagcomboboxexitema) 항목 정보를 받는 구조체입니다.

### <a name="return-value"></a>반환 값

작업에 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

메시지의 기능을 구현 하는이 멤버 함수 [CBEM_SETITEM](/windows/desktop/Controls/cbem-setitem)Windows SDK에 설명 된 대로 합니다.

##  <a name="setwindowtheme"></a>  CComboBoxEx::SetWindowTheme

비주얼 스타일의 확장 된 콤보 상자 컨트롤을 설정합니다.

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>매개 변수

*pszSubAppName*<br/>
확장 된 콤보 상자 비주얼 스타일 집합을 포함 하는 유니코드 문자열 포인터입니다.

### <a name="return-value"></a>반환 값

반환 값은 사용 되지 않습니다.

### <a name="remarks"></a>설명

이 멤버 함수는의 기능을 에뮬레이션 합니다 [CBEM_SETWINDOWTHEME](/windows/desktop/Controls/cbem-setwindowtheme) Windows SDK에 설명 된 대로 메시지입니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 MFCIE](../../overview/visual-cpp-samples.md)<br/>
[CComboBox 클래스](../../mfc/reference/ccombobox-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CComboBox 클래스](../../mfc/reference/ccombobox-class.md)
