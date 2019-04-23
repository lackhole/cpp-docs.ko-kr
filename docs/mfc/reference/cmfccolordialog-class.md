---
title: CMFCColorDialog 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog::CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog::GetColor
- AFXCOLORDIALOG/CMFCColorDialog::GetPalette
- AFXCOLORDIALOG/CMFCColorDialog::RebuildPalette
- AFXCOLORDIALOG/CMFCColorDialog::SetCurrentColor
- AFXCOLORDIALOG/CMFCColorDialog::SetNewColor
- AFXCOLORDIALOG/CMFCColorDialog::SetPageOne
- AFXCOLORDIALOG/CMFCColorDialog::SetPageTwo
helpviewer_keywords:
- CMFCColorDialog [MFC], CMFCColorDialog
- CMFCColorDialog [MFC], GetColor
- CMFCColorDialog [MFC], GetPalette
- CMFCColorDialog [MFC], RebuildPalette
- CMFCColorDialog [MFC], SetCurrentColor
- CMFCColorDialog [MFC], SetNewColor
- CMFCColorDialog [MFC], SetPageOne
- CMFCColorDialog [MFC], SetPageTwo
ms.assetid: 235bbbbc-a3b1-46e0-801b-fb55093ec579
ms.openlocfilehash: 1b9f57e46d5ac74dd52f7ddb7ebd90f8888891e3
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58772753"
---
# <a name="cmfccolordialog-class"></a>CMFCColorDialog 클래스

`CMFCColorDialog` 클래스 색 선택 대화 상자를 나타냅니다.

## <a name="syntax"></a>구문

```
class CMFCColorDialog : public CDialogEx
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMFCColorDialog::CMFCColorDialog](#cmfccolordialog)|`CMFCColorDialog` 개체를 생성합니다.|
|`CMFCColorDialog::~CMFCColorDialog`|소멸자|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCColorDialog::GetColor](#getcolor)|현재 선택한 색을 반환합니다.|
|[CMFCColorDialog::GetPalette](#getpalette)|색의 색상표를 반환합니다.|
|`CMFCColorDialog::PreTranslateMessage`|디스패치 되기 전에 창 메시지를 변환 합니다 [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) 하 고 [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows 함수입니다. 구문 및 자세한 내용은 [cwnd:: Pretranslatemessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)합니다. ( `CDialogEx::PreTranslateMessage`을 재정의합니다.)|
|[CMFCColorDialog::RebuildPalette](#rebuildpalette)|색상표는 시스템 색상표에서 파생 됩니다.|
|[CMFCColorDialog::SetCurrentColor](#setcurrentcolor)|현재 선택한 색을 설정합니다.|
|[CMFCColorDialog::SetNewColor](#setnewcolor)|색 RGB 값을 지정된 하려면 해당 가장 설정합니다.|
|[CMFCColorDialog::SetPageOne](#setpageone)|첫 번째 속성 페이지에 대 한 RGB 값을 선택합니다.|
|[CMFCColorDialog::SetPageTwo](#setpagetwo)|두 번째 속성 페이지에 대 한 RGB 값을 선택합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|이름|설명|
|----------|-----------------|
|`m_bIsMyPalette`|색 선택 대화 상자 자체 색상표를 사용 하는 경우 TRUE 또는 FALSE 대화 상자에 지정 된 색상표를 사용 하는 경우는 `CMFCColorDialog` 생성자입니다.|
|`m_bPickerMode`|사용자는 선택 대화 상자에서 색을 선택 하는 동안 TRUE 그렇지 않으면 FALSE입니다.|
|`m_btnColorSelect`|사용자가 선택한 색 단추입니다.|
|`m_CurrentColor`|현재 선택한 색입니다.|
|`m_hcurPicker`|색을 선택 하는 데 사용 되는 커서입니다.|
|`m_NewColor`|잠재 선택한 색을 영구적으로 선택 하거나 원래 색으로 되돌릴 수 있습니다.|
|`m_pColourSheetOne`|색 선택 속성 시트의 첫 번째 속성 페이지에 대 한 포인터입니다.|
|`m_pColourSheetTwo`|색 선택 속성 시트의 속성 페이지에 대 한 포인터입니다.|
|`m_pPalette`|현재 논리 색상표입니다.|
|`m_pPropSheet`|색 선택 대화 상자에 대 한 속성 시트에 대 한 포인터입니다.|
|`m_wndColors`|색 선택 컨트롤 개체입니다.|
|`m_wndStaticPlaceHolder`|색 선택기 속성 시트에 대 한 자리 표시자 정적 컨트롤입니다.|

## <a name="remarks"></a>설명

색 선택 대화 상자는 두 개의 페이지를 사용 하 여 속성 시트로 표시 됩니다. 첫 번째 페이지에서 시스템 색상표;에서 표준 색 선택 두 번째 페이지에서 사용자 지정 색을 선택합니다.

생성할 수 있습니다는 `CMFCColorDialog` 스택의 개체를 호출 `DoModal`, 초기 색에 대 한 매개 변수로 전달 합니다 `CMFCColorDialog` 생성자. 색 선택 대화 상자는 다음 몇 가지 만듭니다 [CMFCColorPickerCtrl 클래스](../../mfc/reference/cmfccolorpickerctrl-class.md) 각 색상표를 처리 하는 개체입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)

## <a name="example"></a>예제

다음 예제에서는 색 대화 상자에서 다양 한 메서드를 사용 하 여 구성 하는 방법에 설명 합니다 `CMFCColorDialog` 클래스입니다. 이 예제에서는 현재 및 대화 상자의 새 색을 설정 하는 방법 및 색 대화의 두 속성 페이지에서 선택한 색의 빨강, 녹색 및 파랑 구성 요소를 설정 하는 방법을 보여 줍니다. 이 예제는의 일부를 [새 컨트롤 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_NewControls#3](../../mfc/reference/codesnippet/cpp/cmfccolordialog-class_1.cpp)]

## <a name="requirements"></a>요구 사항

**헤더:** afxcolordialog.h

##  <a name="cmfccolordialog"></a>  CMFCColorDialog::CMFCColorDialog

`CMFCColorDialog` 개체를 생성합니다.

```
CMFCColorDialog(
    COLORREF clrInit=0,
    DWORD dwFlags=0,
    CWnd* pParentWnd=NULL,
    HPALETTE hPal=NULL);
```

### <a name="parameters"></a>매개 변수

*clrInit*<br/>
[in] 기본 색 선택 합니다. 없는 값을 지정 하는 경우 기본값은 RGB(0,0,0) (검정).

*dwFlags*<br/>
[in] 예약되어 있습니다.

*pParentWnd*<br/>
[in] 대화 상자의 부모 또는 소유자 창에 대 한 포인터입니다.

*hPal*<br/>
[in] 색 색상표 핸들입니다.

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getcolor"></a>  CMFCColorDialog::GetColor

색 대화 상자에서 사용자가 선택한 색을 검색 합니다.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>반환 값

A [COLORREF](/windows/desktop/gdi/colorref) 색 대화 상자에서 선택한 색의 RGB 정보를 포함 하는 값입니다.

### <a name="remarks"></a>설명

이 함수를 호출한 후 호출 된 `DoModal` 메서드.

##  <a name="getpalette"></a>  CMFCColorDialog::GetPalette

현재 색 대화 상자에서 사용할 수 있는 색상표를 검색 합니다.

```
CPalette* GetPalette() const;
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `CPalette` 에 지정 된 개체는 `CMFCColorDialog` 생성자입니다.

### <a name="remarks"></a>설명

색상표는 사용자가 선택할 수 있는 색을 지정 합니다.

##  <a name="rebuildpalette"></a>  CMFCColorDialog::RebuildPalette

색상표는 시스템 색상표에서 파생 됩니다.

```
void RebuildPalette();
```

##  <a name="setcurrentcolor"></a>  CMFCColorDialog::SetCurrentColor

대화 상자의 현재 색을 설정합니다.

```
void SetCurrentColor(COLORREF rgb);
```

### <a name="parameters"></a>매개 변수

*rgb*<br/>
[in] RGB 색상 값

### <a name="remarks"></a>설명

##  <a name="setnewcolor"></a>  CMFCColorDialog::SetNewColor

현재 색 가장 유사한 현재 색상표의 색을 설정 합니다.

```
void SetNewColor(COLORREF rgb);
```

### <a name="parameters"></a>매개 변수

*rgb*<br/>
[in] A [COLORREF](/windows/desktop/gdi/colorref) RGB 색을 지정 하는 합니다.

### <a name="remarks"></a>설명

##  <a name="setpageone"></a>  CMFCColorDialog::SetPageOne

색 대화의 첫 번째 속성 페이지에서 선택한 색의 빨강, 녹색 및 파랑 구성 요소를 명시적으로 지정 합니다.

```
void SetPageOne(
    BYTE R,
    BYTE G,
    BYTE B);
```

### <a name="parameters"></a>매개 변수

*R*<br/>
[in] RGB 값의 빨강 구성 요소를 지정합니다.

*G*<br/>
[in] RGB 값의 녹색 구성 요소를 지정합니다.

*B*<br/>
[in] RGB 값의 파랑 구성 요소를 지정합니다.

### <a name="remarks"></a>설명

##  <a name="setpagetwo"></a>  CMFCColorDialog::SetPageTwo

색 대화의 두 번째 속성 페이지에서 선택한 색의 빨강, 녹색 및 파랑 구성 요소를 명시적으로 지정 합니다.

```
void SetPageTwo(
    BYTE R,
    BYTE G,
    BYTE B);
```

### <a name="parameters"></a>매개 변수

*R*<br/>
[in] RGB 값의 빨강 구성 요소를 지정합니다.

*G*<br/>
[in] RGB 값의 녹색 구성 요소를 지정합니다.

*B*<br/>
[in] RGB 값의 파랑 구성 요소를 지정합니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorPickerCtrl 클래스](../../mfc/reference/cmfccolorpickerctrl-class.md)
