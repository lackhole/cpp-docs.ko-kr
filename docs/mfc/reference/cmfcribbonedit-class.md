---
title: CMFCRibbonEdit 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::CanBeStretched
- AFXRIBBONEDIT/CMFCRibbonEdit::CopyFrom
- AFXRIBBONEDIT/CMFCRibbonEdit::CreateEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::DestroyCtrl
- AFXRIBBONEDIT/CMFCRibbonEdit::DropDownList
- AFXRIBBONEDIT/CMFCRibbonEdit::EnableSpinButtons
- AFXRIBBONEDIT/CMFCRibbonEdit::GetCompactSize
- AFXRIBBONEDIT/CMFCRibbonEdit::GetEditText
- AFXRIBBONEDIT/CMFCRibbonEdit::GetIntermediateSize
- AFXRIBBONEDIT/CMFCRibbonEdit::GetTextAlign
- AFXRIBBONEDIT/CMFCRibbonEdit::GetWidth
- AFXRIBBONEDIT/CMFCRibbonEdit::HasCompactMode
- AFXRIBBONEDIT/CMFCRibbonEdit::HasFocus
- AFXRIBBONEDIT/CMFCRibbonEdit::HasLargeMode
- AFXRIBBONEDIT/CMFCRibbonEdit::HasSpinButtons
- AFXRIBBONEDIT/CMFCRibbonEdit::IsHighlighted
- AFXRIBBONEDIT/CMFCRibbonEdit::OnAfterChangeRect
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDraw
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDrawLabelAndImage
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDrawOnList
- AFXRIBBONEDIT/CMFCRibbonEdit::OnEnable
- AFXRIBBONEDIT/CMFCRibbonEdit::OnHighlight
- AFXRIBBONEDIT/CMFCRibbonEdit::OnKey
- AFXRIBBONEDIT/CMFCRibbonEdit::OnLButtonDown
- AFXRIBBONEDIT/CMFCRibbonEdit::OnLButtonUp
- AFXRIBBONEDIT/CMFCRibbonEdit::OnRTLChanged
- AFXRIBBONEDIT/CMFCRibbonEdit::OnShow
- AFXRIBBONEDIT/CMFCRibbonEdit::Redraw
- AFXRIBBONEDIT/CMFCRibbonEdit::SetACCData
- AFXRIBBONEDIT/CMFCRibbonEdit::SetEditText
- AFXRIBBONEDIT/CMFCRibbonEdit::SetTextAlign
- AFXRIBBONEDIT/CMFCRibbonEdit::SetWidth
helpviewer_keywords:
- CMFCRibbonEdit [MFC], CMFCRibbonEdit
- CMFCRibbonEdit [MFC], CanBeStretched
- CMFCRibbonEdit [MFC], CMFCRibbonEdit
- CMFCRibbonEdit [MFC], CopyFrom
- CMFCRibbonEdit [MFC], CreateEdit
- CMFCRibbonEdit [MFC], DestroyCtrl
- CMFCRibbonEdit [MFC], DropDownList
- CMFCRibbonEdit [MFC], EnableSpinButtons
- CMFCRibbonEdit [MFC], GetCompactSize
- CMFCRibbonEdit [MFC], GetEditText
- CMFCRibbonEdit [MFC], GetIntermediateSize
- CMFCRibbonEdit [MFC], GetTextAlign
- CMFCRibbonEdit [MFC], GetWidth
- CMFCRibbonEdit [MFC], HasCompactMode
- CMFCRibbonEdit [MFC], HasFocus
- CMFCRibbonEdit [MFC], HasLargeMode
- CMFCRibbonEdit [MFC], HasSpinButtons
- CMFCRibbonEdit [MFC], IsHighlighted
- CMFCRibbonEdit [MFC], OnAfterChangeRect
- CMFCRibbonEdit [MFC], OnDraw
- CMFCRibbonEdit [MFC], OnDrawLabelAndImage
- CMFCRibbonEdit [MFC], OnDrawOnList
- CMFCRibbonEdit [MFC], OnEnable
- CMFCRibbonEdit [MFC], OnHighlight
- CMFCRibbonEdit [MFC], OnKey
- CMFCRibbonEdit [MFC], OnLButtonDown
- CMFCRibbonEdit [MFC], OnLButtonUp
- CMFCRibbonEdit [MFC], OnRTLChanged
- CMFCRibbonEdit [MFC], OnShow
- CMFCRibbonEdit [MFC], Redraw
- CMFCRibbonEdit [MFC], SetACCData
- CMFCRibbonEdit [MFC], SetEditText
- CMFCRibbonEdit [MFC], SetTextAlign
- CMFCRibbonEdit [MFC], SetWidth
ms.assetid: 9b85f1f2-446b-454e-9af9-104fdad8a897
ms.openlocfilehash: 80ee43ae32416f9f62df419c4afbd46a0aa63cc8
ms.sourcegitcommit: 39debf8c525c3951af6913ee5e514617658f8859
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/10/2019
ms.locfileid: "58780485"
---
# <a name="cmfcribbonedit-class"></a>CMFCRibbonEdit 클래스

리본 표시줄에 있는 편집 컨트롤을 구현 합니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonEdit : public CMFCRibbonButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|`CMFCRibbonEdit` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCRibbonEdit::CanBeStretched](#canbestretched)|나타냅니다 여부를 높이 `CMFCRibbonEdit` 컨트롤 리본 행의 높이를 세로 방향으로 늘어날 수 있습니다.|
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|`CMFCRibbonEdit` 개체를 생성합니다.|
|[CMFCRibbonEdit::CopyFrom](#copyfrom)|지정 된 상태를 복사 `CMFCRibbonEdit` 개체를 현재 `CMFCRibbonEdit` 개체입니다.|
|[CMFCRibbonEdit::CreateEdit](#createedit)|에 대 한 새 입력란이 만들어집니다는 `CMFCRibbonEdit` 개체입니다.|
|[CMFCRibbonEdit::DestroyCtrl](#destroyctrl)|제거 된 `CMFCRibbonEdit` 개체입니다.|
|[CMFCRibbonEdit::DropDownList](#dropdownlist)|드롭다운 목록 상자를 삭제합니다.|
|[CMFCRibbonEdit::EnableSpinButtons](#enablespinbuttons)|사용 하도록 설정 하 고 텍스트 상자에 대 한 스핀 단추의 범위를 설정 합니다.|
|[CMFCRibbonEdit::GetCompactSize](#getcompactsize)|Compact 크기를 검색 합니다 `CFMCRibbonEdit` 개체입니다.|
|[CMFCRibbonEdit::GetEditText](#getedittext)|텍스트 상자에 텍스트를 검색합니다.|
|[CMFCRibbonEdit::GetIntermediateSize](#getintermediatesize)|중간 크기를 검색 합니다 `CMFCRibbonEdit` 개체입니다.|
|[CMFCRibbonEdit::GetTextAlign](#gettextalign)|텍스트 상자에 텍스트의 맞춤을 검색합니다.|
|[CMFCRibbonEdit::GetWidth](#getwidth)|너비 (픽셀) 검색 합니다 `CMFCRibbonEdit` 제어 합니다.|
|[CMFCRibbonEdit::HasCompactMode](#hascompactmode)|나타냅니다 표시에 대 한 크기 조정 여부를 `CMFCRibbonEdit` 컨트롤이 압축 될 수 있습니다.|
|[CMFCRibbonEdit::HasFocus](#hasfocus)|나타냅니다 여부는 `CMFCRIbbonEdit` 컨트롤에 포커스가 합니다.|
|[CMFCRibbonEdit::HasLargeMode](#haslargemode)|나타냅니다 표시에 대 한 크기 조정 여부를 `CMFCRibbonEdit` 컨트롤 클 수 있습니다.|
|[CMFCRibbonEdit::HasSpinButtons](#hasspinbuttons)|입력란은 스핀 단추에 있는지 여부를 나타냅니다.|
|[CMFCRibbonEdit::IsHighlighted](#ishighlighted)|나타냅니다 여부는 `CMFCRibbonEdit` 컨트롤 강조 표시 됩니다.|
|[CMFCRibbonEdit::OnAfterChangeRect](#onafterchangerect)|프레임 워크에서 호출 하면의 표시 사각형의 크기는 `CMFCRibbonEdit` 컨트롤이 변경 합니다.|
|[CMFCRibbonEdit::OnDraw](#ondraw)|그리기 위해 프레임 워크에서 호출 된 `CMFCRibbonEdit` 제어 합니다.|
|[CMFCRibbonEdit::OnDrawLabelAndImage](#ondrawlabelandimage)|레이블 및 이미지에 대 한 프레임 워크에서 호출 된 `CMFCRibbonEdit` 제어 합니다.|
|[CMFCRibbonEdit::OnDrawOnList](#ondrawonlist)|그리기 위해 프레임 워크에서 호출 된 `CMFCRibbonEdit` 명령 목록 상자에서 제어 합니다.|
|[CMFCRibbonEdit::OnEnable](#onenable)|사용 하도록 설정 하거나 사용 하지 않도록 하기 위해 프레임 워크에서 호출을 `CMFCRibbonEdit` 제어 합니다.|
|[CMFCRibbonEdit::OnHighlight](#onhighlight)|포인터가 들어가거나 범위를 벗어날 때 프레임 워크에서 호출 된 `CMFCRibbonEdit` 제어 합니다.|
|[CMFCRibbonEdit::OnKey](#onkey)|Keytip을 누를 때 프레임 워크에서 호출 및 `CMFCRibbonEdit` 컨트롤에 포커스가 있습니다.|
|[CMFCRibbonEdit::OnLButtonDown](#onlbuttondown)|업데이트 하기 위해 프레임 워크에서 호출 된 `CMFCRibbonEdit` 컨트롤에서 마우스 왼쪽된 단추를 누를 때 제어 합니다.|
|[CMFCRibbonEdit::OnLButtonUp](#onlbuttonup)|마우스 왼쪽된 단추를 놓을 때 프레임 워크에서 호출 됩니다.|
|[CMFCRibbonEdit::OnRTLChanged](#onrtlchanged)|업데이트 하기 위해 프레임 워크에서 호출을 `CMFCRibbonEdit` 레이아웃 방향을 변경 하는 경우를 제어 합니다.|
|[CMFCRibbonEdit::OnShow](#onshow)|표시 하거나 숨기기 위해 프레임 워크에서 호출 된 `CMFCRibbonEdit` 제어 합니다.|
|[CMFCRibbonEdit::Redraw](#redraw)|표시를 업데이트 합니다 `CMFCRibbonEdit` 제어 합니다.|
|[CMFCRibbonEdit::SetACCData](#setaccdata)|설정에 대 한 내게 필요한 옵션 데이터는 `CMFCRibbonEdit` 개체입니다.|
|[CMFCRibbonEdit::SetEditText](#setedittext)|텍스트 상자에 텍스트를 설정합니다.|
|[CMFCRibbonEdit::SetTextAlign](#settextalign)|입력란의 텍스트 맞춤을 설정합니다.|
|[CMFCRibbonEdit::SetWidth](#setwidth)|입력란의 너비를 설정 합니다 `CMFCRibbonEdit` 제어 합니다.|

## <a name="remarks"></a>설명

## <a name="example"></a>예제

다음 예제에서는 생성 하는 방법에 설명 된 `CMFCRibbonEdit` 개체 편집 컨트롤 옆에 있는 스핀 단추를 표시 하 고 편집 컨트롤의 텍스트를 설정 합니다. 이 코드 조각은의 일부인 합니다 [MS Office 2007 데모 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_MSOffice2007Demo#7](../../mfc/reference/codesnippet/cpp/cmfcribbonedit-class_1.cpp)]

## <a name="requirements"></a>요구 사항

**헤더:** afxRibbonEdit.h

##  <a name="canbestretched"></a>  CMFCRibbonEdit::CanBeStretched

나타냅니다 여부를 높이 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤 리본 행의 높이를 세로 방향으로 늘어날 수 있습니다.

```
virtual BOOL CanBeStretched();
```

### <a name="return-value"></a>반환 값

항상 FALSE를 반환합니다.

### <a name="remarks"></a>설명

##  <a name="cmfcribbonedit"></a>  CMFCRibbonEdit::CMFCRibbonEdit

생성 된 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 개체입니다.

```
CMFCRibbonEdit(
    UINT nID,
    int nWidth,
    LPCTSTR lpszLabel = NULL,
    int nImage = -1);

CMFCRibbonEdit();
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
[in] 명령에 대 한 ID는 `CMFCRibbonEdit` 제어 합니다.

*nWidth*<br/>
[in] 픽셀에 대 한 입력란의 너비는 `CMFCRibbonEdit` 제어 합니다.

*lpszLabel*<br/>
[in] 에 대 한 레이블을 `CMFCRibbonEdit` 제어 합니다.

*nImage*<br/>
[in] 사용할 작은 이미지의 인덱스를 `CMFCRibbonEdit` 제어 합니다. 작은 이미지의 컬렉션은 부모 리본 범주에 따라 유지 됩니다.

### <a name="remarks"></a>설명

`CMFCRibbonEdit` 컨트롤은 큰 이미지를 사용 하지 않습니다.

##  <a name="copyfrom"></a>  CMFCRibbonEdit::CopyFrom

지정 된 상태를 복사 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 개체를 현재 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 개체입니다.

```
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>매개 변수

*src*<br/>
[in] 원본 `CMFCRibbonEdit` 개체입니다.

### <a name="remarks"></a>설명

합니다 *src* 매개 변수 형식 이어야 합니다 `CMFCRibbonEdit`합니다.

##  <a name="createedit"></a>  CMFCRibbonEdit::CreateEdit

에 대 한 텍스트 상자를 새로 만들어 합니다 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 개체입니다.

```
virtual CMFCRibbonRichEditCtrl* CreateEdit(
    CWnd* pWndParent,
    DWORD dwEditStyle);
```

### <a name="parameters"></a>매개 변수

*pWndParent*<br/>
[in] 부모 창에 대 한 포인터를 `CMFCRibbonEdit` 개체입니다.

*dwEditStyle*<br/>
[in] 입력란의 스타일을 지정 합니다. 주의 섹션에서 나열 된 창 스타일을 결합할 수 있습니다 합니다 [컨트롤 스타일 편집](/windows/desktop/Controls/edit-control-styles) Windows SDK에 나와 있는 합니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 새 텍스트 상자에 대 한 포인터 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

사용자 지정 텍스트 상자를 만들고 파생된 클래스에서이 메서드를 재정의 합니다.

다음을 적용할 수 있습니다 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 텍스트 상자에:

- **WS_CHILD**

- **WS_VISIBLE**

- **WS_DISABLED**

- **WS_GROUP**

- **WS_TABSTOP**

##  <a name="destroyctrl"></a>  CMFCRibbonEdit::DestroyCtrl

제거 된 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 개체입니다.

```
virtual void DestroyCtrl();
```

### <a name="remarks"></a>설명

##  <a name="dropdownlist"></a>  CMFCRibbonEdit::DropDownList

드롭다운 목록 상자를 삭제합니다.

```
virtual void DropDownList();
```

### <a name="remarks"></a>설명

기본적으로이 메서드는 없습니다. 드롭다운 목록 상자에이 메서드를 재정의 합니다.

##  <a name="enablespinbuttons"></a>  CMFCRibbonEdit::EnableSpinButtons

사용 하도록 설정 하 고 텍스트 상자에 대 한 스핀 단추의 범위를 설정 합니다.

```
void EnableSpinButtons(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>매개 변수

*nMin*<br/>
[in] 최소 값 스핀 단추입니다.

*nMax*<br/>
[in] 최대 값 스핀 단추입니다.

### <a name="remarks"></a>설명

스핀 단추 위쪽 및 아래쪽 화살표를 나타내고 고정된 값 집합을 통해 이동 하는 사용자 합니다.

##  <a name="getcompactsize"></a>  CMFCRibbonEdit::GetCompactSize

Compact 크기를 검색 합니다 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 개체입니다.

```
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터를 `CMFCRibbonEdit` 개체입니다.

### <a name="return-value"></a>반환 값

Compact 크기는 `CMFCRibbonEdit` 개체입니다.

### <a name="remarks"></a>설명

##  <a name="getedittext"></a>  CMFCRibbonEdit::GetEditText

텍스트 상자에 텍스트를 검색합니다.

```
CString GetEditText() const;
```

### <a name="return-value"></a>반환 값

텍스트 상자의 텍스트입니다.

### <a name="remarks"></a>설명

##  <a name="getintermediatesize"></a>  CMFCRibbonEdit::GetIntermediateSize

중간 크기를 검색 합니다 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 개체입니다.

```
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터를 `CMFCRibbonEdit` 개체입니다.

### <a name="return-value"></a>반환 값

중간 크기의 `CMFCRibbonEdit` 개체입니다.

### <a name="remarks"></a>설명

##  <a name="gettextalign"></a>  CMFCRibbonEdit::GetTextAlign

텍스트 상자에 텍스트의 맞춤을 검색합니다.

```
int GetTextAlign() const;
```

### <a name="return-value"></a>반환 값

텍스트 맞춤 값을 열거 합니다. 가능한 값에 대 한 설명 섹션을 참조 합니다.

### <a name="remarks"></a>설명

반환된 된 값에는 다음 편집 컨트롤 스타일 중 하나입니다.

- **ES_LEFT** 왼쪽 맞춤

- **ES_CENTER** 가운데 맞춤에 대 한

- **ES_RIGHT** 오른쪽 맞춤

이러한 스타일에 대 한 자세한 내용은 참조 하세요. [컨트롤 스타일 편집](/windows/desktop/Controls/edit-control-styles)합니다.

##  <a name="getwidth"></a>  CMFCRibbonEdit::GetWidth

너비 (픽셀) 검색 합니다 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 제어 합니다.

```
int GetWidth(BOOL bInFloatyMode = FALSE) const;
```

### <a name="parameters"></a>매개 변수

*bInFloatyMode*<br/>
[in] True는 `CMFCRibbonEdit` 부동 모드에서 컨트롤은, 그렇지 않으면 FALSE입니다.

### <a name="return-value"></a>반환 값

픽셀에서 너비의는 `CMFCRibbonEdit` 제어 합니다.

### <a name="remarks"></a>설명

##  <a name="hascompactmode"></a>  CMFCRibbonEdit::HasCompactMode

나타냅니다 표시에 대 한 크기 조정 여부를 합니다 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤 압축 될 수 있습니다.

```
virtual BOOL HasCompactMode() const;
```

### <a name="return-value"></a>반환 값

항상 TRUE를 반환 합니다.

### <a name="remarks"></a>설명

기본적으로이 메서드는 항상 TRUE를 반환 합니다. 표시 크기 compact 수 있는지 여부를 나타내기 위해이 메서드를 재정의 합니다.

##  <a name="hasfocus"></a>  CMFCRibbonEdit::HasFocus

나타냅니다 여부를 합니다 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤에 포커스가 있습니다.

```
virtual BOOL HasFocus() const;
```

### <a name="return-value"></a>반환 값

True는 `CMFCRibbonEdit` 컨트롤에 포커스가, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="haslargemode"></a>  CMFCRibbonEdit::HasLargeMode

나타냅니다 표시에 대 한 크기 조정 여부를 합니다 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤 클 수 있습니다.

```
virtual BOOL HasLargeMode() const;
```

### <a name="return-value"></a>반환 값

항상 FALSE를 반환합니다.

### <a name="remarks"></a>설명

기본적으로이 메서드는 항상 FALSE를 반환합니다. 표시 크기를 큰 수 있는지 여부를 나타내기 위해이 메서드를 재정의 합니다.

##  <a name="hasspinbuttons"></a>  CMFCRibbonEdit::HasSpinButtons

입력란은 스핀 단추에 있는지 여부를 나타냅니다.

```
virtual BOOL HasSpinButtons() const;
```

### <a name="return-value"></a>반환 값

TRUE 이면 텍스트 상자에는 스핀 단추 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="ishighlighted"></a>  CMFCRibbonEdit::IsHighlighted

나타냅니다 여부는 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤 강조 표시 됩니다.

```
virtual BOOL IsHighlighted() const;
```

### <a name="return-value"></a>반환 값

True는 `CMFCRibbonEdit` 컨트롤은 강조 표시 된, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="onafterchangerect"></a>  CMFCRibbonEdit::OnAfterChangeRect

프레임 워크에서 호출 하면에 대 한 표시 사각형의 크기를 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 변경 제어 합니다.

```
virtual void OnAfterChangeRect(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터를 `CMFCRibbonEdit` 제어 합니다.

### <a name="remarks"></a>설명

##  <a name="ondraw"></a>  CMFCRibbonEdit::OnDraw

그리기 위해 프레임 워크에서 호출 된 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 제어 합니다.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터를 `CMFCRibbonEdit` 제어 합니다.

### <a name="remarks"></a>설명

##  <a name="ondrawlabelandimage"></a>  CMFCRibbonEdit::OnDrawLabelAndImage

레이블 및 이미지에 대 한 프레임 워크에서 호출 된 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 제어 합니다.

```
virtual void OnDrawLabelAndImage(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터를 `CMFCRibbonEdit` 제어 합니다.

### <a name="remarks"></a>설명

##  <a name="ondrawonlist"></a>  CMFCRibbonEdit::OnDrawOnList

그리기 위해 프레임 워크에서 호출 된 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 명령 목록 상자에서 제어 합니다.

```
virtual void OnDrawOnList(
    CDC* pDC,
    CString strText,
    int nTextOffset,
    CRect rect,
    BOOL bIsSelected,
    BOOL bHighlighted);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터를 `CMFCRibbonEdit` 제어 합니다.

*strText*<br/>
[in] 텍스트를 표시할 [ ] (../../mfc/reference/cmfcribbonedit-class.md "cmfcribbonedit 클래스")합니다.

*nTextOffset*<br/>
[in] 텍스트를 표시할 목록 상자의 왼쪽에서의 픽셀 단위의 거리입니다.

*rect*<br/>
[in] 에 대 한 표시 사각형을 `CMFCRibbonEdit` 제어 합니다.

*bIsSelected*<br/>
[in] 이 매개 변수 사용 되지 않습니다.

*bHighlighted*<br/>
[in] 이 매개 변수 사용 되지 않습니다.

### <a name="remarks"></a>설명

명령 목록 상자는 사용자는 빠른 실행 도구 모음을 사용자 지정할 수 있도록 리본 컨트롤을 표시 합니다.

##  <a name="onenable"></a>  CMFCRibbonEdit::OnEnable

사용 하도록 설정 하거나 사용 하지 않도록 하기 위해 프레임 워크에서 호출 합니다 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 제어 합니다.

```
virtual void OnEnable(BOOL bEnable);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
[in] 컨트롤을 사용 하도록 설정 컨트롤을 사용 하지 않도록 설정 하려면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="onhighlight"></a>  CMFCRibbonEdit::OnHighlight

포인터가 들어가거나 범위를 벗어날 때 프레임 워크에서 호출 된 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 제어 합니다.

```
virtual void OnHighlight(BOOL bHighlight);
```

### <a name="parameters"></a>매개 변수

*bHighlight*<br/>
[in] 포인터의 범위에 있으면 TRUE를 `CMFCRibbonEdit` 컨트롤, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="onkey"></a>  CMFCRibbonEdit::OnKey

Keytip을 누를 때 프레임 워크에서 호출 하며 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤에 포커스가 있습니다.

```
virtual BOOL OnKey(BOOL bIsMenuKey);
```

### <a name="parameters"></a>매개 변수

*bIsMenuKey*<br/>
[in] Keytip을 팝업 메뉴를 표시 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="return-value"></a>반환 값

이벤트가 처리 되었으면 TRUE 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="onlbuttondown"></a>  CMFCRibbonEdit::OnLButtonDown

업데이트 하기 위해 프레임 워크에서 호출 된 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤에서 마우스 왼쪽된 단추를 누를 때 제어 합니다.

```
virtual void OnLButtonDown(CPoint point);
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
[in] 이 매개 변수 사용 되지 않습니다.

### <a name="remarks"></a>설명

##  <a name="onlbuttonup"></a>  CMFCRibbonEdit::OnLButtonUp

마우스 왼쪽된 단추를 놓을 때 프레임 워크에서 호출 됩니다.

```
virtual void OnLButtonUp(CPoint point);
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
[in] 이 매개 변수 사용 되지 않습니다.

### <a name="remarks"></a>설명

##  <a name="onrtlchanged"></a>  CMFCRibbonEdit::OnRTLChanged

업데이트 하기 위해 프레임 워크에서 호출 합니다 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 레이아웃 방향을 변경 하는 경우를 제어 합니다.

```
virtual void OnRTLChanged(BOOL bIsRTL);
```

### <a name="parameters"></a>매개 변수

*bIsRTL*<br/>
[in] 레이아웃이 오른쪽에서 왼쪽; 면 TRUE입니다. 레이아웃이 왼쪽에서 오른쪽 면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="onshow"></a>  CMFCRibbonEdit::OnShow

표시 하거나 숨기기 위해 프레임 워크에서 호출 된 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 제어 합니다.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>매개 변수

*bShow*<br/>
[in] 컨트롤을 표시 컨트롤을 숨기려면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="redraw"></a>  CMFCRibbonEdit::Redraw

표시를 업데이트 합니다 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 제어 합니다.

```
virtual void Redraw();
```

### <a name="remarks"></a>설명

이 메서드가 다시에 대 한 표시 사각형을 그립니다. 합니다 `CMFCRibbonEdit` 개체를 직접 호출 하 여 [CWnd::RedrawWindow](/windows/desktop/api/winuser/nf-winuser-redrawwindow) RDW_INVALIDATE, RDW_ERASE, 및 RDW_UPDATENOW 플래그를 사용 하 여 설정 합니다.

##  <a name="setaccdata"></a>  CMFCRibbonEdit::SetACCData

에 대 한 내게 필요한 옵션 데이터를 설정 합니다 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 개체입니다.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>매개 변수

*pParent*<br/>
에 대 한 부모 창에 대 한 포인터를 `CMFCRibbonEdit` 개체입니다.

*데이터*<br/>
에 대 한 내게 필요한 옵션 데이터는 `CMFCRibbonEdit` 개체입니다.

### <a name="return-value"></a>반환 값

항상 TRUE를 반환 합니다.

### <a name="remarks"></a>설명

##  <a name="setedittext"></a>  CMFCRibbonEdit::SetEditText

텍스트 상자에 텍스트를 설정합니다.

```
void SetEditText(CString strText);
```

### <a name="parameters"></a>매개 변수

*strText*<br/>
[in] 텍스트 상자에 대 한 텍스트입니다.

##  <a name="settextalign"></a>  CMFCRibbonEdit::SetTextAlign

입력란의 텍스트 맞춤을 설정합니다.

```
void SetTextAlign(int nAlign);
```

### <a name="parameters"></a>매개 변수

*nAlign*<br/>
[in] 텍스트 맞춤 값을 열거 합니다. 가능한 값에 대 한 설명 섹션을 참조 합니다.

### <a name="remarks"></a>설명

매개 변수 *nAlign* 컨트롤 스타일 편집을 다음 중 하나입니다.

- ES_LEFT 왼쪽 맞춤

- ES_CENTER 가운데 맞춤에 대 한

- 오른쪽 맞춤에 대 한 ES_RIGHT

이러한 스타일에 대 한 자세한 내용은 참조 하세요. [컨트롤 스타일 편집](/windows/desktop/Controls/edit-control-styles)합니다.

##  <a name="setwidth"></a>  CMFCRibbonEdit::SetWidth

입력란의 너비를 설정 합니다 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 제어 합니다.

```
void SetWidth(
    int nWidth,
    BOOL bInFloatyMode = FALSE);
```

### <a name="parameters"></a>매개 변수

*nWidth*<br/>
[in] 입력란의 픽셀에서 너비입니다.

*bInFloatyMode*<br/>
부동 모드에 대 한 너비를 설정. 일반 모드에 대 한 너비를 설정 하려면 FALSE입니다.

### <a name="remarks"></a>설명

`CMFCRibbonEdit` 컨트롤에는 디스플레이 모드에 따라 두 너비: 모드와 일반 모드를 부동 합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton 클래스](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[CMFCRibbonBar 클래스](../../mfc/reference/cmfcribbonbar-class.md)
