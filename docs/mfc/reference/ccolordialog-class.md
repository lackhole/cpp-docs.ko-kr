---
title: CColorDialog 클래스
ms.date: 11/04/2016
f1_keywords:
- CColorDialog
- AFXDLGS/CColorDialog
- AFXDLGS/CColorDialog::CColorDialog
- AFXDLGS/CColorDialog::DoModal
- AFXDLGS/CColorDialog::GetColor
- AFXDLGS/CColorDialog::GetSavedCustomColors
- AFXDLGS/CColorDialog::SetCurrentColor
- AFXDLGS/CColorDialog::OnColorOK
- AFXDLGS/CColorDialog::m_cc
helpviewer_keywords:
- CColorDialog [MFC], CColorDialog
- CColorDialog [MFC], DoModal
- CColorDialog [MFC], GetColor
- CColorDialog [MFC], GetSavedCustomColors
- CColorDialog [MFC], SetCurrentColor
- CColorDialog [MFC], OnColorOK
- CColorDialog [MFC], m_cc
ms.assetid: d013dc25-9290-4b5d-a97e-95ad7208e13b
ms.openlocfilehash: bc9bc76b328359d4c8ec7796de7dfaa7d3a9cf2c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207727"
---
# <a name="ccolordialog-class"></a>CColorDialog 클래스

색 선택 대화 상자를 응용 프로그램에 통합할 수 있습니다.

## <a name="syntax"></a>구문

```
class CColorDialog : public CCommonDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CColorDialog::CColorDialog](#ccolordialog)|`CColorDialog` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CColorDialog::DoModal](#domodal)|색 대화 상자를 표시 및 선택할 수 있습니다.|
|[CColorDialog::GetColor](#getcolor)|반환 된 `COLORREF` 선택한 색의 값이 포함 된 구조입니다.|
|[CColorDialog::GetSavedCustomColors](#getsavedcustomcolors)|사용자가 만든 사용자 지정 색을 검색 합니다.|
|[CColorDialog::SetCurrentColor](#setcurrentcolor)|지정된 된 색에 현재 색 선택 영역을 강제로 수행합니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CColorDialog::OnColorOK](#oncolorok)|색 대화 상자에 입력의 유효성을 검사 하려면 재정의 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CColorDialog::m_cc](#m_cc)|대화 상자의 설정을 사용자 지정 하는 데 사용 되는 구조입니다.|

## <a name="remarks"></a>설명

`CColorDialog` 개체 표시 시스템에 대해 정의 된 색 목록 사용 하 여 대화 상자입니다. 사용자 선택 하거나 보고 됩니다 다시 응용 프로그램에 대화 상자를 종료 하는 경우 목록에서 특정 색을 만들 수 있습니다.

생성 하는 `CColorDialog` 개체, 제공 된 생성자를 사용 하거나 새 클래스를 파생 시키고 사용자 고유의 사용자 지정 생성자를 사용 합니다.

대화 상자 생성 되 면이 설정 하거나 모든 값을 수정할 수 있습니다 합니다 [m_cc](#m_cc) 대화 상자의 컨트롤의 값을 초기화 하는 구조입니다. 합니다 *m_cc* 형식의 구조체가 [사용자가 CHOOSECOLOR](/windows/desktop/api/commdlg/ns-commdlg-tagchoosecolora)합니다.

대화 상자의 컨트롤을 초기화 한 후 호출 하 여 `DoModal` 대화 상자를 표시 하 고 사용자가 색을 선택 하도록 허용 하려면 멤버 함수입니다. `DoModal` 사용자의 선택 하거나 대화 상자의 확인 (IDOK) 하거나 취소 (IDCANCEL) 단추를 반환합니다.

하는 경우 `DoModal` IDOK 반환 중 하나를 사용할 수 있습니다 `CColorDialog`의 사용자가 입력 한 정보를 검색 하는 멤버 함수입니다.

Windows를 사용할 수 있습니다 [CommDlgExtendedError](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) 함수 대화 상자를 초기화 하는 동안 오류가 발생 했는지 여부를 확인 하 고 오류에 자세히 알아보기.

`CColorDialog` COMMDLG 의존합니다. Windows 버전 3.1 이상 함께 제공 되는 DLL 파일입니다.

대화 상자를 사용자 지정 하려면 클래스를 파생 `CColorDialog`사용자 지정 대화 상자 템플릿을 제공 하 고 확장 된 컨트롤에서 알림 메시지를 처리 하는 메시지 맵을 추가 합니다. 처리 되지 않은 메시지는 기본 클래스에 전달 되어야 합니다.

후크 함수를 사용자 지정 필요 하지 않습니다.

> [!NOTE]
>  일부 설치에서의 `CColorDialog` 개체에 다른 프레임 워크를 사용한 경우에 회색 배경으로 표시 되지 것입니다 `CDialog` 개체 회색으로 표시 합니다.

사용 하 여 대 한 자세한 내용은 `CColorDialog`를 참조 하세요 [일반 대화 상자 클래스](../../mfc/common-dialog-classes.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CColorDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxdlgs.h

##  <a name="ccolordialog"></a>  CColorDialog::CColorDialog

`CColorDialog` 개체를 생성합니다.

```
CColorDialog(
    COLORREF clrInit = 0,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*clrInit*<br/>
기본 색 선택 합니다. 없는 값을 지정 하는 경우 기본값은 RGB(0,0,0) (검정).

*dwFlags*<br/>
집합 함수 및 대화 상자의 모양을 사용자 지정 하는 플래그입니다. 자세한 내용은 참조는 [사용자가 CHOOSECOLOR](/windows/desktop/api/commdlg/ns-commdlg-tagchoosecolora) Windows SDK의 구조입니다.

*pParentWnd*<br/>
대화 상자의 부모 또는 소유자 창에 대 한 포인터입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#49](../../mfc/codesnippet/cpp/ccolordialog-class_1.cpp)]

##  <a name="domodal"></a>  CColorDialog::DoModal

Windows 일반 색 대화 상자를 표시 하 고 사용자가 색을 선택 하도록 허용 하려면이 함수를 호출 합니다.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>반환 값

IDOK 또는 idcancel이 반환 됩니다. IDCANCEL이 반환 되는 Windows를 호출 [CommDlgExtendedError](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) 오류가 발생 했는지 여부를 결정 하는 함수입니다.

IDOK 및 IDCANCEL는 사용자 확인 또는 취소 단추를 선택 하는지 여부를 나타내는 상수입니다.

### <a name="remarks"></a>설명

멤버를 설정 하 여 다양 한 색 대화 상자 옵션을 초기화 하려는 경우는 [m_cc](#m_cc) 구조를 호출 하기 전에이 작업을 수행 해야 `DoModal` 대화 상자 개체에서 생성 된 후 있지만.

호출 후 `DoModal`, 설정 또는 사용자가 정보 입력 대화 상자에 검색할 함수 다른 멤버를 호출할 수 있습니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CColorDialog::CColorDialog](#ccolordialog)합니다.

##  <a name="getcolor"></a>  CColorDialog::GetColor

이 함수를 호출한 후 호출 `DoModal` 사용자가 선택한 색에 대 한 정보를 검색할 수 있습니다.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>반환 값

A [COLORREF](/windows/desktop/gdi/colorref) 색 대화 상자에서 선택한 색의 RGB 정보를 포함 하는 값입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#50](../../mfc/codesnippet/cpp/ccolordialog-class_2.cpp)]

##  <a name="getsavedcustomcolors"></a>  CColorDialog::GetSavedCustomColors

`CColorDialog` 개체는 사용자가 색을 선택 하는 것 외에도 최대 16 개의 사용자 지정 색을 허용 합니다.

```
static COLORREF* PASCAL GetSavedCustomColors();
```

### <a name="return-value"></a>반환 값

사용자가 만든 사용자 지정 색을 저장 하는 16 RGB 색 값의 배열에 대 한 포인터입니다.

### <a name="remarks"></a>설명

`GetSavedCustomColors` 멤버 함수는 이러한 색에 대 한 액세스를 제공 합니다. 이러한 색 후 검색할 수 있습니다 [DoModal](#domodal) IDOK를 반환 합니다.

각 반환된 된 배열에 16 RGB 값 (흰색) RGB(255,255,255) 초기화 됩니다. 사용자가 선택한 색을 사용자 지정 응용 프로그램 내에서 대화 상자 호출 사이만 저장 됩니다. 응용 프로그램의 호출 사이의 이러한 색을 저장 하려는 경우 저장 해야 다른 방식으로 같은 초기화에서 (합니다. INI) 파일입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#51](../../mfc/codesnippet/cpp/ccolordialog-class_3.cpp)]

##  <a name="m_cc"></a>  CColorDialog::m_cc

형식의 구조체 [사용자가 CHOOSECOLOR](/windows/desktop/api/commdlg/ns-commdlg-tagchoosecolora), 멤버가 특성 및 대화 상자의 값을 저장 합니다.

```
CHOOSECOLOR m_cc;
```

### <a name="remarks"></a>설명

생성 한 후는 `CColorDialog` 개체를 사용할 수 있습니다 *m_cc* 호출 하기 전에 대화 상자의 다양 한 측면을 설정 하는 [DoModal](#domodal) 멤버 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#53](../../mfc/codesnippet/cpp/ccolordialog-class_4.cpp)]

##  <a name="oncolorok"></a>  CColorDialog::OnColorOK

색 대화 상자에 입력의 유효성을 검사 하려면 재정의 합니다.

```
virtual BOOL OnColorOK();
```

### <a name="return-value"></a>반환 값

대화 상자를 닫을 수 해야; 경우 0이 아닌 값 입력 된 색을 적용할 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

색 대화 상자에서 사용자가 선택 된 색의 사용자 지정 유효성 검사를 제공 하려는 경우에이 함수를 재정의 합니다.

사용자는 다음 두 가지 방법 중 하나에서 색을 선택할 수 있습니다.:

- 색상표에서 색을 클릭합니다. 선택한 색의 RGB 값은 다음 적절 한 RGB 편집 상자에 반영 됩니다.

- 입력 값의 RGB에서 편집 상자

재정의 `OnColorOK` 어떤 응용 프로그램 관련 이유로 공용 색 대화 상자에 입력 하는 색을 거부할 수 있습니다.

일반적으로 프레임 워크가 색의 기본 유효성 검사를 제공 하 고 잘못 된 색을 입력 한 경우 메시지 상자를 표시 하기 때문에이 함수를 사용할 필요가 없습니다.

호출할 수 있습니다 [SetCurrentColor](#setcurrentcolor) 내에서 `OnColorOK` 색 선택 하도록 합니다. 한 번 `OnColorOK` 발생 했음을 (즉, 사용자가 **확인** 색 변경 내용을 적용할), 호출할 수 있습니다 [GetColor](#getcolor) 새 색의 RGB 값을 가져오려고 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#52](../../mfc/codesnippet/cpp/ccolordialog-class_5.cpp)]

##  <a name="setcurrentcolor"></a>  CColorDialog::SetCurrentColor

이 함수를 호출한 후 호출 `DoModal` 에 지정 된 색 값으로 현재 색 선택을 적용할 *clr*합니다.

```
void SetCurrentColor(COLORREF clr);
```

### <a name="parameters"></a>매개 변수

*clr*<br/>
RGB 색 값입니다.

### <a name="remarks"></a>설명

이 함수는 메시지 처리기 내에서 호출 또는 `OnColorOK`합니다. 대화 상자에서는의 값을 기반으로 하는 사용자가 선택한을 자동으로 업데이트 합니다 *clr* 매개 변수입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CColorDialog::OnColorOK](#oncolorok)합니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 MDI](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 DRAWCLI](../../overview/visual-cpp-samples.md)<br/>
[CCommonDialog 클래스](../../mfc/reference/ccommondialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
