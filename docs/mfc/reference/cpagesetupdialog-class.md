---
title: CPageSetupDialog 클래스
ms.date: 11/04/2016
f1_keywords:
- CPageSetupDialog
- AFXDLGS/CPageSetupDialog
- AFXDLGS/CPageSetupDialog::CPageSetupDialog
- AFXDLGS/CPageSetupDialog::CreatePrinterDC
- AFXDLGS/CPageSetupDialog::DoModal
- AFXDLGS/CPageSetupDialog::GetDeviceName
- AFXDLGS/CPageSetupDialog::GetDevMode
- AFXDLGS/CPageSetupDialog::GetDriverName
- AFXDLGS/CPageSetupDialog::GetMargins
- AFXDLGS/CPageSetupDialog::GetPaperSize
- AFXDLGS/CPageSetupDialog::GetPortName
- AFXDLGS/CPageSetupDialog::OnDrawPage
- AFXDLGS/CPageSetupDialog::PreDrawPage
- AFXDLGS/CPageSetupDialog::m_psd
helpviewer_keywords:
- CPageSetupDialog [MFC], CPageSetupDialog
- CPageSetupDialog [MFC], CreatePrinterDC
- CPageSetupDialog [MFC], DoModal
- CPageSetupDialog [MFC], GetDeviceName
- CPageSetupDialog [MFC], GetDevMode
- CPageSetupDialog [MFC], GetDriverName
- CPageSetupDialog [MFC], GetMargins
- CPageSetupDialog [MFC], GetPaperSize
- CPageSetupDialog [MFC], GetPortName
- CPageSetupDialog [MFC], OnDrawPage
- CPageSetupDialog [MFC], PreDrawPage
- CPageSetupDialog [MFC], m_psd
ms.assetid: 049c0ac8-f254-4854-9414-7a8271d1447a
ms.openlocfilehash: 01a320fbcd9760bab484f3c75553613852ca9aed
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58778093"
---
# <a name="cpagesetupdialog-class"></a>CPageSetupDialog 클래스

인쇄 여백 설정과 수정이 추가로 지원되는 Windows 공용 OLE 페이지 설정 대화 상자에서 제공하는, 서비스를 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CPageSetupDialog : public CCommonDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog)|`CPageSetupDialog` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CPageSetupDialog::CreatePrinterDC](#createprinterdc)|인쇄에 대 한 장치 컨텍스트를 만듭니다.|
|[CPageSetupDialog::DoModal](#domodal)|대화 상자를 표시 하 고 사용자 확인을 선택할 수 있습니다.|
|[CPageSetupDialog::GetDeviceName](#getdevicename)|프린터의 장치 이름을 반환합니다.|
|[CPageSetupDialog::GetDevMode](#getdevmode)|프린터의 현재 DEVMODE를 반환합니다.|
|[CPageSetupDialog::GetDriverName](#getdrivername)|프린터에서 사용 하는 드라이버를 반환 합니다.|
|[CPageSetupDialog::GetMargins](#getmargins)|프린터의 현재 여백 설정을 반환합니다.|
|[CPageSetupDialog::GetPaperSize](#getpapersize)|프린터의 용지 크기를 반환합니다.|
|[CPageSetupDialog::GetPortName](#getportname)|출력 포트 이름을 반환합니다.|
|[CPageSetupDialog::OnDrawPage](#ondrawpage)|인쇄 된 페이지의 화면 이미지를 렌더링 하기 위해 프레임 워크에서 호출 됩니다.|
|[CPageSetupDialog::PreDrawPage](#predrawpage)|인쇄 된 페이지의 화면 이미지를 렌더링 하기 전에 프레임 워크에서 호출 됩니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CPageSetupDialog::m_psd](#m_psd)|사용자 지정 하는 데 사용 되는 구조를 `CPageSetupDialog` 개체입니다.|

## <a name="remarks"></a>설명

이 클래스는 인쇄 설정 대화 상자의 위치를 사용 하도록 설계 되었습니다.

사용 하는 `CPageSetupDialog` 개체를 처음 사용 하 여 개체를 만듭니다는 `CPageSetupDialog` 생성자입니다. 대화 상자 생성 되 면이 설정 하거나 모든 값을 수정할 수 있습니다는 `m_psd` 데이터 멤버 대화 상자의 컨트롤의 값을 초기화 합니다. 합니다 [m_psd](#m_psd) PAGESETUPDLG 형식의 구조입니다.

대화 상자 컨트롤을 초기화 한 후 호출 하 여 `DoModal` 대화 상자를 표시 하 고 사용자가 인쇄 옵션을 선택 하도록 허용 하려면 멤버 함수입니다. `DoModal` 사용자 확인 (IDOK) 또는 취소 (IDCANCEL) 단추를 선택 하는지 여부를 반환 합니다.

경우 `DoModal` IDOK 반환 몇 가지를 사용할 수 있습니다 `CPageSetupDialog`의 멤버 함수 또는 액세스를 `m_psd` 데이터 멤버, 사용자가 정보 입력을 검색 합니다.

> [!NOTE]
>  공용 OLE 페이지 설정 대화 상자는 해제 된 후 프레임 워크에서 사용자가 변경한 내용을 저장 되지 않습니다. 응용 프로그램의 문서 또는 응용 프로그램 클래스의 멤버와 같은 영구 위치,이 대화 상자에서 값을 저장 하려면 응용 프로그램 자체는 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPageSetupDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxdlgs.h

##  <a name="cpagesetupdialog"></a>  CPageSetupDialog::CPageSetupDialog

생성 하려면이 함수 호출을 `CPageSetupDialog` 개체입니다.

```
CPageSetupDialog(
    DWORD dwFlags = PSD_MARGINS | PSD_INWININIINTLMEASURE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*dwFlags*<br/>
하나 이상의 플래그를 사용 하면 대화 상자의 설정을 사용자 지정할 수 있습니다. 비트 OR 연산자를 사용 하 여 값을 결합할 수 있습니다. 이러한 값에는 다음과 같은 의미가 있습니다.

- PSD_DEFAULTMINMARGINS는 프린터의 최소값으로 동일 하도록 페이지 여백에 대 한 허용 되는 최소 너비를 설정 합니다. PSD_MARGINS 및 PSD_MINMARGINS 플래그 지정 된 경우이 플래그는 무시 됩니다.

- PSD_INWININIINTLMEASURE 없습니다 구현 합니다.

- PSD_MINMARGINS 하면 시스템에서 지정 된 값이 사용 된 `rtMinMargin` 왼쪽, 위쪽, 오른쪽 및 아래쪽 여백에 대 한 최소 허용 되는 너비와 멤버입니다. 시스템에서 지정 된 최소값 보다 작은 너비 입력 사용자를 방지 합니다. PSD_MINMARGINS를 지정 하지 않은 경우 프린터에서 허용 되는 것 허용 되는 최소 너비를 설정 하는 시스템입니다.

- PSD_MARGINS 여백 컨트롤 영역을 활성화합니다.

- PSD_INTHOUSANDTHSOFINCHES 하면 대화 상자의 단위 1/1000 인치 단위로 측정입니다.

- PSD_INHUNDREDTHSOFMILLIMETERS 하면 대화 상자의 단위 1/100 밀리미터 단위로 측정입니다.

- PSD_DISABLEMARGINS 여백 대화 상자 컨트롤을 비활성화합니다.

- PSD_DISABLEPRINTER는 프린터 단추를 사용 하지 않도록 설정 합니다.

- PSD_NOWARNING 기본 프린터가 없는 경우 표시 되 고 경고 메시지를 방지 합니다.

- PSD_DISABLEORIENTATION은 페이지 방향 대화 상자 컨트롤을 비활성화합니다.

- PSD_RETURNDEFAULT 발생 `CPageSetupDialog` 반환할 [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) 하 고 [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) 대화 상자를 표시 하지 않고 시스템 기본 프린터에 대 한 초기화 되는 구조입니다. 가정 하는 두 `hDevNames` 고 `hDevMode` 함수는 오류를 반환 하는 고, 그렇지 않으면 null입니다. 시스템 기본 프린터는 이전 프린터 드라이버 (이전의 Windows 버전 3.0)에서 지원 되는 경우만 `hDevNames` 를 반환 합니다. `hDevMode` NULL입니다.

- PSD_DISABLEPAPER 문서 선택 컨트롤을 비활성화 합니다.

- PSD_SHOWHELP 하면 대화 상자의 도움말 단추를 표시 합니다. `hwndOwner` 멤버 해야이 플래그를 지정 하는 경우 null 일 수 없습니다.

- PSD_ENABLEPAGESETUPHOOK 후크 함수에 지정 된 수 있도록 `lpfnSetupHook`입니다.

- PSD_ENABLEPAGESETUPTEMPLATE 인해 운영 체제에서 식별 된 템플릿 대화 상자를 사용 하 여 대화 상자를 만들려면 `hInstance` 고 `lpSetupTemplateName`입니다.

- 나타내는 PSD_ENABLEPAGESETUPTEMPLATEHANDLE `hInstance` 미리 로드 된 대화 상자 템플릿에 포함 된 데이터 블록을 식별 합니다. 시스템은 무시 `lpSetupTemplateName` 이 플래그를 지정 합니다.

- PSD_ENABLEPAGEPAINTHOOK 후크 함수에 지정 된 수 있도록 `lpfnPagePaintHook`입니다.

- PSD_DISABLEPAGEPAINTING은 그리기 영역의 대화 상자를 사용 하지 않도록 설정 합니다.

*pParentWnd*<br/>
대화 상자의 부모 또는 소유자에 대 한 포인터입니다.

### <a name="remarks"></a>설명

사용 된 [DoModal](../../mfc/reference/cdialog-class.md#domodal) 대화 상자를 표시 하는 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#94](../../mfc/codesnippet/cpp/cpagesetupdialog-class_1.cpp)]

##  <a name="createprinterdc"></a>  CPageSetupDialog::CreatePrinterDC

프린터 장치 컨텍스트를 만듭니다.는 [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) 하 고 [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) 구조입니다.

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>반환 값

새로 만든된 프린터 장치 컨텍스트 (DC)에 대 한 핸들입니다.

##  <a name="domodal"></a>  CPageSetupDialog::DoModal

Windows 공용 OLE 페이지 설정 대화 상자를 표시 하 고 사용자가 인쇄 여백, 크기 및 방향을 문서 및 대상 프린터와 같은 다양 한 인쇄 설정 옵션을 선택 하도록 허용 하려면이 함수를 호출 합니다.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>반환 값

IDOK 또는 idcancel이 반환 됩니다. IDCANCEL이 반환 되는 Windows를 호출 [CommDlgExtendedError](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) 오류가 발생 했는지 여부를 결정 하는 함수입니다.

IDOK 및 IDCANCEL는 사용자 확인 또는 취소 단추를 선택 하는지 여부를 나타내는 상수입니다.

### <a name="remarks"></a>설명

또한 사용자는 네트워크 위치 및 선택한 프린터에 특정 속성과 같은 프린터 설치 옵션을 액세스할 수 있습니다.

멤버를 설정 하 여 다양 한 페이지 설정 대화 상자 옵션을 초기화 하려는 경우는 `m_psd` 구조를 호출 하기 전에 이렇게 해야 `DoModal`, 대화 상자 개체에서 생성 된 후 및 합니다. 호출 후 `DoModal`, 다른 멤버를 설정 또는 사용자가 정보 입력 대화 상자에 검색할 함수를 호출 합니다.

사용자가 입력 한 현재 설정을 전파 하려는 경우 호출할 [CWinApp::SelectPrinter](../../mfc/reference/cwinapp-class.md#selectprinter)합니다. 이 함수는의 정보는 `CPageSetupDialog` 개체를 초기화 하 고 적절 한 특성을 사용 하 여 새 프린터 DC를 선택 합니다.

[!code-cpp[NVC_MFCDocView#95](../../mfc/codesnippet/cpp/cpagesetupdialog-class_2.cpp)]

### <a name="example"></a>예제

  예를 참조 하세요 [CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog)합니다.

##  <a name="getdevicename"></a>  CPageSetupDialog::GetDeviceName

후이 함수를 호출 `DoModal` 현재 선택한 프린터의 이름을 검색 합니다.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>반환 값

사용 된 장치 이름을 `CPageSetupDialog` 개체입니다.

##  <a name="getdevmode"></a>  CPageSetupDialog::GetDevMode

이 함수를 호출한 후 호출 `DoModal` 의 프린터 장치 컨텍스트에 대 한 정보를 검색 하는 `CPageSetupDialog` 개체입니다.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>반환 값

합니다 [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) 장치 초기화 및 인쇄 드라이버의 환경에 대 한 정보를 포함 하는 데이터 구조입니다. 이 구조는 Windows 사용 하 여 가져온 메모리가 잠금을 해제 해야 합니다 [GlobalUnlock](/windows/desktop/api/winbase/nf-winbase-globalunlock) Windows SDK에 설명 된 함수입니다.

##  <a name="getdrivername"></a>  CPageSetupDialog::GetDriverName

호출한 후이 함수를 호출 [DoModal](../../mfc/reference/cprintdialog-class.md#domodal) 시스템 정의 프린터 장치 드라이버의 이름을 검색 합니다.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>반환 값

`CString` 드라이버 시스템 정의 이름을 지정 합니다.

### <a name="remarks"></a>설명

에 대 한 포인터를 사용 합니다 `CString` 에서 반환 된 개체 `GetDriverName` 값으로 `lpszDriverName` 호출에서 [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).

##  <a name="getmargins"></a>  CPageSetupDialog::GetMargins

이 함수를 호출한 후 호출 `DoModal` 프린터 장치 드라이버의 여백을 검색할 합니다.

```
void GetMargins(
    LPRECT lpRectMargins,
    LPRECT lpRectMinMargins) const;
```

### <a name="parameters"></a>매개 변수

*lpRectMargins*<br/>
에 대 한 포인터를 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 구조 나 [CRect](../../atl-mfc-shared/reference/crect-class.md) 현재 선택한 프린터에서 인쇄 여백을 (1/1000 인치 또는 1/100 mm)에서 설명 하는 개체입니다. 이 사각형에 관심이 없는 경우이 매개 변수에 대해 NULL을 전달 합니다.

*lpRectMinMargins*<br/>
에 대 한 포인터를 `RECT` 구조 또는 `CRect` 현재 선택된 된 프린터에 대 한 최소 인쇄 여백 (1/1000 인치 또는 1/100 mm)에서 설명 하는 개체입니다. 이 사각형에 관심이 없는 경우이 매개 변수에 대해 NULL을 전달 합니다.

##  <a name="getpapersize"></a>  CPageSetupDialog::GetPaperSize

인쇄 하기 위해 선택한 용지 크기를 검색 하려면이 함수를 호출 합니다.

```
CSize GetPaperSize() const;
```

### <a name="return-value"></a>반환 값

A [CSize](../../atl-mfc-shared/reference/csize-class.md) (1/1000 인치 또는 1/100 mm)에서 인쇄 하기 위해 선택한 용지 크기를 포함 하는 개체입니다.

##  <a name="getportname"></a>  CPageSetupDialog::GetPortName

이 함수를 호출한 후 호출 `DoModal` 현재 선택 된 프린터 포트의 이름을 검색 하려면.

```
CString GetPortName() const;
```

### <a name="return-value"></a>반환 값

현재 선택 된 프린터 포트의 이름입니다.

##  <a name="m_psd"></a>  CPageSetupDialog::m_psd

PAGESETUPDLG, 대화 상자 개체의 특성을 저장 하는 멤버가 형식의 구조체입니다.

```
PAGESETUPDLG m_psd;
```

### <a name="remarks"></a>설명

생성 한 후는 `CPageSetupDialog` 개체를 사용할 수 있습니다 `m_psd` 호출 하기 전에 대화 상자의 다양 한 측면을 설정 하는 `DoModal` 멤버 함수입니다.

수정 하는 경우는 `m_psd` 데이터 멤버는 기본 동작을 재정의 직접.

에 대 한 자세한 합니다 [PAGESETUPDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpsda) 구조체를 Windows SDK를 참조 하세요.

예를 참조 하세요 [CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog)합니다.

##  <a name="ondrawpage"></a>  CPageSetupDialog::OnDrawPage

인쇄 된 페이지의 화면 이미지를 그리기 위해 프레임 워크에서 호출 됩니다.

```
virtual UINT OnDrawPage(
    CDC* pDC,
    UINT nMessage,
    LPRECT lpRect);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
프린터 장치 컨텍스트 포인터입니다.

*nMessage*<br/>
그리고 현재 페이지의 영역을 나타내는 메시지를 지정 합니다. 다음 중 하나일 수 있습니다.

- WM_PSD_FULLPAGERECT 전체 페이지 영역입니다.

- WM_PSD_MINMARGINRECT 현재 최소 여백입니다.

- 현재 WM_PSD_MARGINRECT 여백입니다.

- 페이지의 WM_PSD_GREEKTEXTRECT 내용입니다.

- 우표 표현에 대 한 예약 WM_PSD_ENVSTAMPRECT 영역입니다.

- 반송 주소 표현에 대 한 WM_PSD_YAFULLPAGERECT 영역입니다. 이 영역은 샘플 페이지 영역의 가장자리에 확장 됩니다.

*lpRect*<br/>
에 대 한 포인터를 [CRect](../../atl-mfc-shared/reference/crect-class.md) 하거나 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 그리기 영역의 좌표를 포함 하는 개체입니다.

### <a name="return-value"></a>반환 값

처리 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 이미지는 다음 공용 OLE 페이지 설정 대화 상자의 일부로 표시 됩니다. 기본 구현은 텍스트 페이지의 이미지를 그립니다.

사용자 지정 이미지 또는 전체 이미지의 특정 영역으로 그릴 하려면이 함수를 재정의 합니다. 사용 하 여이 수행할 수 있습니다는 **전환** 사용 하 여 문을 **사례** 값을 확인 하는 문을 *n 메시지*합니다. 예를 들어 페이지 이미지의 내용 렌더링을 사용자 지정 하려면 다음 예제 코드를 사용할 수 있습니다.

[!code-cpp[NVC_MFCDocView#96](../../mfc/codesnippet/cpp/cpagesetupdialog-class_3.cpp)]

모든 사례를 처리할 필요가 없습니다 *n 메시지*합니다. 요소 이미지, 이미지 또는 전체 영역의 여러 구성 요소 중 하나를 처리 하도록 선택할 수 있습니다.

##  <a name="predrawpage"></a>  CPageSetupDialog::PreDrawPage

인쇄 된 페이지의 화면 이미지를 그리기 전에 프레임 워크에서 호출 됩니다.

```
virtual UINT PreDrawPage(
    WORD wPaper,
    WORD wFlags,
    LPPAGESETUPDLG pPSD);
```

### <a name="parameters"></a>매개 변수

*wPaper*<br/>
용지 크기를 나타내는 값을 지정 합니다. 이 값 중 하나일 수 있습니다 합니다 **DMPAPER_** 의 설명에 나열 된 값을 [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) 구조입니다.

*wFlags*<br/>
용지 또는 봉투의 방향을 나타냅니다 및 프린터 도트 또는 HPPCL (Hewlett Packard 프린터 컨트롤 Language) 장치를 인지 합니다. 이 매개 변수는 다음 값 중 하나를 가질 수 있습니다.

- (도트 매트릭스) 가로 모드로 0x001 용지

- (HPPCL) 가로 모드로 0x003 용지

- (도트 매트릭스) 세로 모드로 0x005 용지

- (HPPCL) 세로 모드로 0x007 용지

- 0x00b 가로 모드 (HPPCL) 봉투 (envelope)

- 0x00d 세로 모드 (도트 매트릭스) 봉투 (envelope)

- 0x019 가로 모드 (도트 매트릭스) 봉투 (envelope)

- 0x01f 세로 모드 (도트 매트릭스) 봉투 (envelope)

*pPSD*<br/>
`PAGESETUPDLG` 구조체에 대한 포인터입니다. 에 대 한 자세한 [PAGESETUPDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpsda), Windows SDK를 참조 하세요.

### <a name="return-value"></a>반환 값

처리 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이미지의 그리기를 사용자 지정 하려면이 함수를 재정의 합니다. 이 함수를 재정의 하 고 TRUE를 반환 하는 경우에 전체 이미지를 그릴 해야 합니다. 이 함수를 재정의 하 고 FALSE를 반환 하는 경우 전체 기본 이미지 프레임 워크에서 그려집니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 워드 패드](../../overview/visual-cpp-samples.md)<br/>
[CCommonDialog 클래스](../../mfc/reference/ccommondialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
