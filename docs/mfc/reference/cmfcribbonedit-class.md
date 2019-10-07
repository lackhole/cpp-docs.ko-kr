---
title: Cmfc리본 Edit 클래스
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
ms.openlocfilehash: 4f973074fbec3d04b1c1a74852b02ff2564217c1
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504945"
---
# <a name="cmfcribbonedit-class"></a>Cmfc리본 Edit 클래스

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

|이름|Description|
|----------|-----------------|
|[CMFCRibbonEdit::CanBeStretched](#canbestretched)|`CMFCRibbonEdit` 컨트롤의 높이가 리본 행의 높이로 세로 방향으로 증가할 수 있는지 여부를 나타냅니다.|
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|`CMFCRibbonEdit` 개체를 생성합니다.|
|[CMFCRibbonEdit::CopyFrom](#copyfrom)|지정 `CMFCRibbonEdit` 된 개체의 상태를 현재 `CMFCRibbonEdit` 개체에 복사 합니다.|
|[CMFCRibbonEdit::CreateEdit](#createedit)|`CMFCRibbonEdit` 개체에 대 한 새 텍스트 상자를 만듭니다.|
|[CMFCRibbonEdit::DestroyCtrl](#destroyctrl)|개체를 `CMFCRibbonEdit` 소멸 시킵니다.|
|[CMFCRibbonEdit::DropDownList](#dropdownlist)|목록 상자를 삭제 합니다.|
|[CMFCRibbonEdit::EnableSpinButtons](#enablespinbuttons)|텍스트 상자의 스핀 단추 범위를 설정 하 고 설정 합니다.|
|[CMFCRibbonEdit::GetCompactSize](#getcompactsize)|`CFMCRibbonEdit` 개체의 컴팩트 크기를 검색 합니다.|
|[CMFCRibbonEdit::GetEditText](#getedittext)|텍스트 상자에서 텍스트를 검색 합니다.|
|[CMFCRibbonEdit::GetIntermediateSize](#getintermediatesize)|`CMFCRibbonEdit` 개체의 중간 크기를 검색 합니다.|
|[CMFCRibbonEdit::GetTextAlign](#gettextalign)|텍스트 상자의 텍스트 맞춤을 검색 합니다.|
|[CMFCRibbonEdit::GetWidth](#getwidth)|`CMFCRibbonEdit` 컨트롤의 너비 (픽셀)를 검색 합니다.|
|[CMFCRibbonEdit::HasCompactMode](#hascompactmode)|`CMFCRibbonEdit` 컨트롤의 표시 크기를 압축할 수 있는지 여부를 나타냅니다.|
|[CMFCRibbonEdit::HasFocus](#hasfocus)|`CMFCRIbbonEdit` 컨트롤에 포커스가 있는지 여부를 나타냅니다.|
|[CMFCRibbonEdit::HasLargeMode](#haslargemode)|`CMFCRibbonEdit` 컨트롤의 표시 크기를 클 수 있는지 여부를 나타냅니다.|
|[CMFCRibbonEdit::HasSpinButtons](#hasspinbuttons)|텍스트 상자에 스핀 단추가 있는지 여부를 나타냅니다.|
|[CMFCRibbonEdit::IsHighlighted](#ishighlighted)|`CMFCRibbonEdit` 컨트롤이 강조 표시 되는지 여부를 나타냅니다.|
|[CMFCRibbonEdit::OnAfterChangeRect](#onafterchangerect)|`CMFCRibbonEdit` 컨트롤의 표시 사각형 크기가 변경 될 때 프레임 워크에서 호출 됩니다.|
|[CMFCRibbonEdit::OnDraw](#ondraw)|`CMFCRibbonEdit` 컨트롤을 그리기 위해 프레임 워크에서 호출 됩니다.|
|[CMFCRibbonEdit::OnDrawLabelAndImage](#ondrawlabelandimage)|`CMFCRibbonEdit` 컨트롤의 레이블과 이미지를 그리기 위해 프레임 워크에서 호출 됩니다.|
|[CMFCRibbonEdit::OnDrawOnList](#ondrawonlist)|명령 목록 상자에 `CMFCRibbonEdit` 컨트롤을 그리기 위해 프레임 워크에서 호출 됩니다.|
|[CMFCRibbonEdit::OnEnable](#onenable)|`CMFCRibbonEdit` 컨트롤을 활성화 하거나 비활성화 하기 위해 프레임 워크에서 호출 됩니다.|
|[CMFCRibbonEdit::OnHighlight](#onhighlight)|포인터가 `CMFCRibbonEdit` 컨트롤의 범위를 들어가거나 벗어날 때 프레임 워크에서 호출 됩니다.|
|[CMFCRibbonEdit::OnKey](#onkey)|사용자가 keytip `CMFCRibbonEdit` 을 누르고 컨트롤에 포커스가 있을 때 프레임 워크에서 호출 됩니다.|
|[CMFCRibbonEdit::OnLButtonDown](#onlbuttondown)|사용자가 컨트롤의 왼쪽 마우스 단추 `CMFCRibbonEdit` 를 누를 때 컨트롤을 업데이트 하기 위해 프레임 워크에서 호출 됩니다.|
|[CMFCRibbonEdit::OnLButtonUp](#onlbuttonup)|사용자가 마우스 왼쪽 단추를 놓을 때 프레임 워크에서 호출 됩니다.|
|[CMFCRibbonEdit::OnRTLChanged](#onrtlchanged)|레이아웃의 방향이 변경 될 때 컨트롤 `CMFCRibbonEdit` 을 업데이트 하기 위해 프레임 워크에서 호출 됩니다.|
|[CMFCRibbonEdit::OnShow](#onshow)|`CMFCRibbonEdit` 컨트롤을 표시 하거나 숨기도록 프레임 워크에서 호출 됩니다.|
|[CMFCRibbonEdit::Redraw](#redraw)|`CMFCRibbonEdit` 컨트롤의 표시를 업데이트 합니다.|
|[CMFCRibbonEdit::SetACCData](#setaccdata)|`CMFCRibbonEdit` 개체에 대 한 내게 필요한 옵션 데이터를 설정 합니다.|
|[CMFCRibbonEdit::SetEditText](#setedittext)|텍스트 상자의 텍스트를 설정 합니다.|
|[CMFCRibbonEdit::SetTextAlign](#settextalign)|텍스트 상자의 텍스트 맞춤을 설정 합니다.|
|[CMFCRibbonEdit::SetWidth](#setwidth)|`CMFCRibbonEdit` 컨트롤의 텍스트 상자 너비를 설정 합니다.|

## <a name="remarks"></a>설명

## <a name="example"></a>예제

다음 예제에서는 `CMFCRibbonEdit` 개체를 생성 하 고, 편집 컨트롤 옆에 스핀 단추를 표시 하 고, 편집 컨트롤의 텍스트를 설정 하는 방법을 보여 줍니다. 이 코드 조각은 [MS Office 2007 Demo 샘플](../../overview/visual-cpp-samples.md)의 일부입니다.

[!code-cpp[NVC_MFC_MSOffice2007Demo#7](../../mfc/reference/codesnippet/cpp/cmfcribbonedit-class_1.cpp)]

## <a name="requirements"></a>요구 사항

**헤더:** afxRibbonEdit

##  <a name="canbestretched"></a>  CMFCRibbonEdit::CanBeStretched

[Cmfcribbon edit](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤의 높이가 리본 행의 높이로 세로 방향으로 증가할 수 있는지 여부를 나타냅니다.

```
virtual BOOL CanBeStretched();
```

### <a name="return-value"></a>반환 값

항상 FALSE를 반환 합니다.

### <a name="remarks"></a>설명

##  <a name="cmfcribbonedit"></a>  CMFCRibbonEdit::CMFCRibbonEdit

[Cmfc리본 편집](../../mfc/reference/cmfcribbonedit-class.md) 개체를 생성 합니다.

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
진행 `CMFCRibbonEdit` 컨트롤의 명령 ID입니다.

*nWidth*<br/>
진행 `CMFCRibbonEdit` 컨트롤에 대 한 텍스트 상자의 너비 (픽셀)입니다.

*lpszLabel*<br/>
진행 `CMFCRibbonEdit` 컨트롤의 레이블입니다.

*nImage*<br/>
진행 `CMFCRibbonEdit` 컨트롤에 사용할 작은 이미지의 인덱스입니다. 작은 이미지의 컬렉션은 부모 리본 범주에 의해 유지 관리 됩니다.

### <a name="remarks"></a>설명

컨트롤 `CMFCRibbonEdit` 에서 긴 이미지를 사용 하지 않습니다.

##  <a name="copyfrom"></a>  CMFCRibbonEdit::CopyFrom

지정 된 [Cmfc리본 edit](../../mfc/reference/cmfcribbonedit-class.md) 개체의 상태를 현재 [cmfc리본 edit](../../mfc/reference/cmfcribbonedit-class.md) 개체에 복사 합니다.

```
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>매개 변수

*src*<br/>
진행 원본 `CMFCRibbonEdit` 개체입니다.

### <a name="remarks"></a>설명

*Src* 매개 변수는 형식 `CMFCRibbonEdit`이어야 합니다.

##  <a name="createedit"></a>  CMFCRibbonEdit::CreateEdit

[Cmfc리본 편집](../../mfc/reference/cmfcribbonedit-class.md) 개체에 대 한 새 텍스트 상자를 만듭니다.

```
virtual CMFCRibbonRichEditCtrl* CreateEdit(
    CWnd* pWndParent,
    DWORD dwEditStyle);
```

### <a name="parameters"></a>매개 변수

*pWndParent*<br/>
진행 `CMFCRibbonEdit` 개체의 부모 창에 대 한 포인터입니다.

*dwEditStyle*<br/>
진행 텍스트 상자의 스타일을 지정 합니다. 설명 섹션에 나열 된 창 스타일을 Windows SDK에 설명 된 [편집 컨트롤 스타일](/windows/win32/Controls/edit-control-styles) 과 결합할 수 있습니다.

### <a name="return-value"></a>반환 값

메서드가 성공한 경우 새 텍스트 상자에 대 한 포인터입니다. 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

파생 클래스에서이 메서드를 재정의 하 여 사용자 지정 텍스트 상자를 만듭니다.

텍스트 상자에 다음 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 을 적용할 수 있습니다.

- **WS_CHILD**

- **WS_VISIBLE**

- **WS_DISABLED**

- **WS_GROUP**

- **WS_TABSTOP**

##  <a name="destroyctrl"></a>  CMFCRibbonEdit::DestroyCtrl

[Cmfc리본 edit](../../mfc/reference/cmfcribbonedit-class.md) 개체를 소멸 시킵니다.

```
virtual void DestroyCtrl();
```

### <a name="remarks"></a>설명

##  <a name="dropdownlist"></a>  CMFCRibbonEdit::DropDownList

목록 상자를 삭제 합니다.

```
virtual void DropDownList();
```

### <a name="remarks"></a>설명

기본적으로이 메서드는 아무 작업도 수행 하지 않습니다. 목록 상자를 드롭다운 하려면이 메서드를 재정의 합니다.

##  <a name="enablespinbuttons"></a>  CMFCRibbonEdit::EnableSpinButtons

텍스트 상자의 스핀 단추 범위를 설정 하 고 설정 합니다.

```
void EnableSpinButtons(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>매개 변수

*nMin*<br/>
진행 스핀 단추의 최소값입니다.

*nMax*<br/>
진행 스핀 단추의 최대값입니다.

### <a name="remarks"></a>설명

스핀 단추 위쪽 및 아래쪽 화살표를 표시 하 고 사용자가 고정 된 값 집합을 이동할 수 있도록 합니다.

##  <a name="getcompactsize"></a>  CMFCRibbonEdit::GetCompactSize

[Cmfc리본 edit](../../mfc/reference/cmfcribbonedit-class.md) 개체의 컴팩트 크기를 검색 합니다.

```
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
진행 `CMFCRibbonEdit` 개체의 장치 컨텍스트에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

`CMFCRibbonEdit` 개체의 압축 크기입니다.

### <a name="remarks"></a>설명

##  <a name="getedittext"></a>  CMFCRibbonEdit::GetEditText

텍스트 상자에서 텍스트를 검색 합니다.

```
CString GetEditText() const;
```

### <a name="return-value"></a>반환 값

텍스트 상자의 텍스트입니다.

### <a name="remarks"></a>설명

##  <a name="getintermediatesize"></a>  CMFCRibbonEdit::GetIntermediateSize

[Cmfc리본 edit](../../mfc/reference/cmfcribbonedit-class.md) 개체의 중간 크기를 검색 합니다.

```
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
진행 `CMFCRibbonEdit` 개체의 장치 컨텍스트에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

`CMFCRibbonEdit` 개체의 중간 크기입니다.

### <a name="remarks"></a>설명

##  <a name="gettextalign"></a>  CMFCRibbonEdit::GetTextAlign

텍스트 상자의 텍스트 맞춤을 검색 합니다.

```
int GetTextAlign() const;
```

### <a name="return-value"></a>반환 값

텍스트 맞춤 열거 값입니다. 가능한 값은 설명 섹션을 참조 하세요.

### <a name="remarks"></a>설명

반환 되는 값은 다음 편집 컨트롤 스타일 중 하나입니다.

- 왼쪽 맞춤에 대 한 **ES_LEFT**

- 가운데 맞춤에 대 한 **ES_CENTER**

- 오른쪽 맞춤에 대 한 **ES_RIGHT**

이러한 스타일에 대 한 자세한 내용은 [컨트롤 스타일 편집](/windows/win32/Controls/edit-control-styles)을 참조 하세요.

##  <a name="getwidth"></a>  CMFCRibbonEdit::GetWidth

[Cmfc리본 edit](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤의 너비 (픽셀 단위)를 검색 합니다.

```
int GetWidth(BOOL bInFloatyMode = FALSE) const;
```

### <a name="parameters"></a>매개 변수

*bInFloatyMode*<br/>
진행 `CMFCRibbonEdit` 컨트롤이 부동 모드 이면 TRUE이 고, 그렇지 않으면 FALSE입니다.

### <a name="return-value"></a>반환 값

`CMFCRibbonEdit` 컨트롤의 너비 (픽셀)입니다.

### <a name="remarks"></a>설명

##  <a name="hascompactmode"></a>  CMFCRibbonEdit::HasCompactMode

[Cmfc리본 편집](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤의 표시 크기를 압축할 수 있는지 여부를 나타냅니다.

```
virtual BOOL HasCompactMode() const;
```

### <a name="return-value"></a>반환 값

항상 TRUE를 반환 합니다.

### <a name="remarks"></a>설명

기본적으로이 메서드는 항상 TRUE를 반환 합니다. 표시 크기를 압축할 수 있는지 여부를 나타내려면이 메서드를 재정의 합니다.

##  <a name="hasfocus"></a>  CMFCRibbonEdit::HasFocus

[Cmfc리본 편집](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤에 포커스가 있는지 여부를 나타냅니다.

```
virtual BOOL HasFocus() const;
```

### <a name="return-value"></a>반환 값

`CMFCRibbonEdit` 컨트롤에 포커스가 있으면 TRUE이 고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="haslargemode"></a>  CMFCRibbonEdit::HasLargeMode

[Cmfc리본 편집](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤의 표시 크기를 클 수 있는지 여부를 나타냅니다.

```
virtual BOOL HasLargeMode() const;
```

### <a name="return-value"></a>반환 값

항상 FALSE를 반환 합니다.

### <a name="remarks"></a>설명

기본적으로이 메서드는 항상 FALSE를 반환 합니다. 표시 크기를 클 수 있는지 여부를 나타내려면이 메서드를 재정의 합니다.

##  <a name="hasspinbuttons"></a>  CMFCRibbonEdit::HasSpinButtons

텍스트 상자에 스핀 단추가 있는지 여부를 나타냅니다.

```
virtual BOOL HasSpinButtons() const;
```

### <a name="return-value"></a>반환 값

텍스트 상자에 스핀 단추가 있으면 TRUE이 고, 그렇지 않으면입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="ishighlighted"></a>  CMFCRibbonEdit::IsHighlighted

[Cmfc리본 편집](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤이 강조 표시 되는지 여부를 나타냅니다.

```
virtual BOOL IsHighlighted() const;
```

### <a name="return-value"></a>반환 값

`CMFCRibbonEdit` 컨트롤이 강조 표시 되 면 TRUE이 고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="onafterchangerect"></a>  CMFCRibbonEdit::OnAfterChangeRect

[Cmfc리본 편집](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤의 표시 사각형 크기가 변경 될 때 프레임 워크에서 호출 됩니다.

```
virtual void OnAfterChangeRect(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
진행 `CMFCRibbonEdit` 컨트롤의 장치 컨텍스트에 대 한 포인터입니다.

### <a name="remarks"></a>설명

##  <a name="ondraw"></a>  CMFCRibbonEdit::OnDraw

[Cmfc리본 edit](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤을 그리기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
진행 `CMFCRibbonEdit` 컨트롤의 장치 컨텍스트에 대 한 포인터입니다.

### <a name="remarks"></a>설명

##  <a name="ondrawlabelandimage"></a>  CMFCRibbonEdit::OnDrawLabelAndImage

[Cmfc리본 edit](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤의 레이블과 이미지를 그리기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnDrawLabelAndImage(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
진행 `CMFCRibbonEdit` 컨트롤의 장치 컨텍스트에 대 한 포인터입니다.

### <a name="remarks"></a>설명

##  <a name="ondrawonlist"></a>  CMFCRibbonEdit::OnDrawOnList

명령 목록 상자에 [Cmfc리본 edit](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤을 그리기 위해 프레임 워크에서 호출 됩니다.

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
진행 `CMFCRibbonEdit` 컨트롤의 장치 컨텍스트에 대 한 포인터입니다.

*strText*<br/>
진행 표시 텍스트 [ ] (../../mfc/reference/cmfcribbonedit-class.md "cmfc리본 edit 클래스")입니다.

*nTextOffset*<br/>
진행 목록 상자의 좌 변에 표시 텍스트 까지의 거리 (픽셀)입니다.

*rect*<br/>
진행 `CMFCRibbonEdit` 컨트롤의 표시 사각형입니다.

*bIsSelected*<br/>
진행 이 매개 변수는 사용 되지 않습니다.

*bHighlighted 표시*<br/>
진행 이 매개 변수는 사용 되지 않습니다.

### <a name="remarks"></a>설명

명령 목록 상자에는 사용자가 빠른 실행 도구 모음을 사용자 지정할 수 있는 리본 컨트롤이 표시 됩니다.

##  <a name="onenable"></a>  CMFCRibbonEdit::OnEnable

[Cmfc리본 edit](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤을 사용 하거나 사용 하지 않도록 프레임 워크에서 호출 됩니다.

```
virtual void OnEnable(BOOL bEnable);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
진행 컨트롤을 사용 하려면 TRUE이 고, 그렇지 않으면입니다. 컨트롤을 사용 하지 않도록 설정 하려면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="onhighlight"></a>  CMFCRibbonEdit::OnHighlight

포인터가 [Cmfc리본 편집](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤의 범위를 들어가거나 벗어날 때 프레임 워크에서 호출 됩니다.

```
virtual void OnHighlight(BOOL bHighlight);
```

### <a name="parameters"></a>매개 변수

*bHighlight*<br/>
진행 포인터가 `CMFCRibbonEdit` 컨트롤의 범위에 있으면 TRUE이 고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="onkey"></a>  CMFCRibbonEdit::OnKey

사용자가 keytip을 누르고 [Cmfc리본 edit](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤에 포커스가 있을 때 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnKey(BOOL bIsMenuKey);
```

### <a name="parameters"></a>매개 변수

*bIsMenuKey*<br/>
진행 Keytip에 팝업 메뉴가 표시 되 면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="return-value"></a>반환 값

이벤트가 처리 되었으면 TRUE이 고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="onlbuttondown"></a>  CMFCRibbonEdit::OnLButtonDown

사용자가 컨트롤의 왼쪽 마우스 단추를 누를 때 [Cmfc리본 edit](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤을 업데이트 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnLButtonDown(CPoint point);
```

### <a name="parameters"></a>매개 변수

*point*<br/>
진행 이 매개 변수는 사용 되지 않습니다.

### <a name="remarks"></a>설명

##  <a name="onlbuttonup"></a>  CMFCRibbonEdit::OnLButtonUp

사용자가 마우스 왼쪽 단추를 놓을 때 프레임 워크에서 호출 됩니다.

```
virtual void OnLButtonUp(CPoint point);
```

### <a name="parameters"></a>매개 변수

*point*<br/>
진행 이 매개 변수는 사용 되지 않습니다.

### <a name="remarks"></a>설명

##  <a name="onrtlchanged"></a>  CMFCRibbonEdit::OnRTLChanged

레이아웃의 방향이 변경 될 때 [Cmfc리본 edit](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤을 업데이트 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnRTLChanged(BOOL bIsRTL);
```

### <a name="parameters"></a>매개 변수

*bIsRTL*<br/>
진행 레이아웃이 오른쪽에서 왼쪽 이면 TRUE입니다. 레이아웃이 왼쪽에서 오른쪽 이면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="onshow"></a>  CMFCRibbonEdit::OnShow

[Cmfc리본 edit](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤을 표시 하거나 숨기도록 프레임 워크에서 호출 됩니다.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>매개 변수

*bShow*<br/>
진행 컨트롤을 표시 하려면 TRUE입니다. 컨트롤을 숨기려면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="redraw"></a>  CMFCRibbonEdit::Redraw

[Cmfc리본 편집](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤의 표시를 업데이트 합니다.

```
virtual void Redraw();
```

### <a name="remarks"></a>설명

이 메서드는 RDW_INVALIDATE, RDW_ERASE 및 RDW_UPDATENOW `CMFCRibbonEdit` 플래그가 설정 된 [CWnd:: redrawwindow](/windows/win32/api/winuser/nf-winuser-redrawwindow) 를 간접적으로 호출 하 여 개체에 대 한 표시 사각형을 다시 그립니다.

##  <a name="setaccdata"></a>  CMFCRibbonEdit::SetACCData

[Cmfc리본 편집](../../mfc/reference/cmfcribbonedit-class.md) 개체에 대 한 내게 필요한 옵션 데이터를 설정 합니다.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>매개 변수

*pParent*<br/>
`CMFCRibbonEdit` 개체의 부모 창에 대 한 포인터입니다.

*data*<br/>
`CMFCRibbonEdit` 개체에 대 한 내게 필요한 옵션 데이터입니다.

### <a name="return-value"></a>반환 값

항상 TRUE를 반환 합니다.

### <a name="remarks"></a>설명

##  <a name="setedittext"></a>  CMFCRibbonEdit::SetEditText

텍스트 상자의 텍스트를 설정 합니다.

```
void SetEditText(CString strText);
```

### <a name="parameters"></a>매개 변수

*strText*<br/>
진행 텍스트 상자의 텍스트입니다.

##  <a name="settextalign"></a>  CMFCRibbonEdit::SetTextAlign

텍스트 상자의 텍스트 맞춤을 설정 합니다.

```
void SetTextAlign(int nAlign);
```

### <a name="parameters"></a>매개 변수

*nAlign*<br/>
진행 텍스트 맞춤 열거 값입니다. 가능한 값은 설명 섹션을 참조 하세요.

### <a name="remarks"></a>설명

*Nalign* 매개 변수는 다음 편집 컨트롤 스타일 중 하나입니다.

- 왼쪽 맞춤에 대 한 ES_LEFT

- 가운데 맞춤에 대 한 ES_CENTER

- 오른쪽 맞춤에 대 한 ES_RIGHT

이러한 스타일에 대 한 자세한 내용은 [컨트롤 스타일 편집](/windows/win32/Controls/edit-control-styles)을 참조 하세요.

##  <a name="setwidth"></a>  CMFCRibbonEdit::SetWidth

[Cmfc리본 편집](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤에 대 한 텍스트 상자의 너비를 설정 합니다.

```
void SetWidth(
    int nWidth,
    BOOL bInFloatyMode = FALSE);
```

### <a name="parameters"></a>매개 변수

*nWidth*<br/>
진행 텍스트 상자의 너비 (픽셀)입니다.

*bInFloatyMode*<br/>
부동 모드의 너비를 설정 하려면 TRUE로 설정 합니다. FALSE를 설정 하 여 일반 모드의 너비를 설정 합니다.

### <a name="remarks"></a>설명

컨트롤 `CMFCRibbonEdit` 에는 표시 모드 (부동 모드 및 일반 모드)에 따라 두 개의 너비가 있습니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton 클래스](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[CMFCRibbonBar 클래스](../../mfc/reference/cmfcribbonbar-class.md)
