---
title: CPrintDialogEx 클래스
ms.date: 11/04/2016
f1_keywords:
- CPrintDialogEx
- AFXDLGS/CPrintDialogEx
- AFXDLGS/CPrintDialogEx::CPrintDialogEx
- AFXDLGS/CPrintDialogEx::CreatePrinterDC
- AFXDLGS/CPrintDialogEx::DoModal
- AFXDLGS/CPrintDialogEx::GetCopies
- AFXDLGS/CPrintDialogEx::GetDefaults
- AFXDLGS/CPrintDialogEx::GetDeviceName
- AFXDLGS/CPrintDialogEx::GetDevMode
- AFXDLGS/CPrintDialogEx::GetDriverName
- AFXDLGS/CPrintDialogEx::GetPortName
- AFXDLGS/CPrintDialogEx::GetPrinterDC
- AFXDLGS/CPrintDialogEx::PrintAll
- AFXDLGS/CPrintDialogEx::PrintCollate
- AFXDLGS/CPrintDialogEx::PrintCurrentPage
- AFXDLGS/CPrintDialogEx::PrintRange
- AFXDLGS/CPrintDialogEx::PrintSelection
- AFXDLGS/CPrintDialogEx::m_pdex
helpviewer_keywords:
- CPrintDialogEx [MFC], CPrintDialogEx
- CPrintDialogEx [MFC], CreatePrinterDC
- CPrintDialogEx [MFC], DoModal
- CPrintDialogEx [MFC], GetCopies
- CPrintDialogEx [MFC], GetDefaults
- CPrintDialogEx [MFC], GetDeviceName
- CPrintDialogEx [MFC], GetDevMode
- CPrintDialogEx [MFC], GetDriverName
- CPrintDialogEx [MFC], GetPortName
- CPrintDialogEx [MFC], GetPrinterDC
- CPrintDialogEx [MFC], PrintAll
- CPrintDialogEx [MFC], PrintCollate
- CPrintDialogEx [MFC], PrintCurrentPage
- CPrintDialogEx [MFC], PrintRange
- CPrintDialogEx [MFC], PrintSelection
- CPrintDialogEx [MFC], m_pdex
ms.assetid: 1d506703-ee1c-44cc-b4ce-4e778fec26b8
ms.openlocfilehash: 3959eb01e5c0a36410129925e7c3f53898e99196
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66504792"
---
# <a name="cprintdialogex-class"></a>CPrintDialogEx 클래스

Windows 인쇄 속성 시트에서 제공 하는 서비스를 캡슐화 합니다.

## <a name="syntax"></a>구문

```
class CPrintDialogEx : public CCommonDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CPrintDialogEx::CPrintDialogEx](#cprintdialogex)|`CPrintDialogEx` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CPrintDialogEx::CreatePrinterDC](#createprinterdc)|인쇄 대화 상자를 표시 하지 않고 프린터 장치 컨텍스트를 만듭니다.|
|[CPrintDialogEx::DoModal](#domodal)|대화 상자를 표시 및 선택할 수 있습니다.|
|[CPrintDialogEx::GetCopies](#getcopies)|요청 된 복사본의 수를 검색 합니다.|
|[CPrintDialogEx::GetDefaults](#getdefaults)|대화 상자를 표시 하지 않고 장치 기본값을 검색 합니다.|
|[CPrintDialogEx::GetDeviceName](#getdevicename)|현재 선택 된 프린터 장치 이름을 검색합니다.|
|[CPrintDialogEx::GetDevMode](#getdevmode)|검색 된 `DEVMODE` 구조입니다.|
|[CPrintDialogEx::GetDriverName](#getdrivername)|시스템 정의 프린터 장치 드라이버의 이름을 검색합니다.|
|[CPrintDialogEx::GetPortName](#getportname)|현재 선택 된 프린터 포트의 이름을 검색합니다.|
|[CPrintDialogEx::GetPrinterDC](#getprinterdc)|프린터 장치 컨텍스트에 대 한 핸들을 검색합니다.|
|[CPrintDialogEx::PrintAll](#printall)|문서의 모든 페이지를 인쇄할 것인지를 결정 합니다.|
|[CPrintDialogEx::PrintCollate](#printcollate)|복사본을 요청 하는 데이터 정렬 여부를 확인 합니다.|
|[CPrintDialogEx::PrintCurrentPage](#printcurrentpage)|문서의 현재 페이지를 인쇄할 것인지를 결정 합니다.|
|[CPrintDialogEx::PrintRange](#printrange)|지정된 된 범위의 페이지를 인쇄할지 여부를 결정 합니다.|
|[CPrintDialogEx::PrintSelection](#printselection)|현재 선택한 항목을 인쇄할지 여부를 결정 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CPrintDialogEx::m_pdex](#m_pdex)|사용자 지정 하는 데 사용 되는 구조를 `CPrintDialogEx` 개체입니다.|

## <a name="remarks"></a>설명

응용 프로그램에 대 한 인쇄 프로세스의 다양 한 측면을 처리 하기 위해 프레임 워크에서 사용할 수 있습니다. 프레임 워크를 사용 하 여 인쇄 작업을 처리 하는 방법에 대 한 자세한 내용은 문서 참조 [인쇄](../../mfc/printing.md)합니다.

프레임 워크의 개입 없이도 인쇄를 처리 하도록 응용 프로그램을 원하는 경우 사용할 수 있습니다는 `CPrintDialogEx` "있는 그대로" 제공 하는 생성자를 사용 하 여 클래스 또는 고유한 대화 상자 클래스에서 파생 될 수 있습니다 `CPrintDialogEx` 요구에 맞게 생성자를 작성 합니다. 두 경우 모두 이러한 대화 상자는 처럼 표준 MFC 대화 상자 클래스에서 파생 되므로 `CCommonDialog`합니다.

사용 하는 `CPrintDialogEx` 개체를 처음 사용 하 여 개체를 만듭니다는 `CPrintDialogEx` 생성자입니다. 대화 상자 생성 되 면이 설정 하거나 모든 값을 수정할 수 있습니다 합니다 [m_pdex](#m_pdex) 대화 상자의 컨트롤의 값을 초기화 하는 구조입니다. 합니다 `m_pdex` 형식의 구조체가 [PRINTDLGEX](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa)합니다. 이 구조에 대 한 자세한 내용은 Windows SDK를 참조 하세요.

고유한 핸들을 제공 하지 않는 경우 `m_pdex` 에 대 한 합니다 `hDevMode` 및 `hDevNames` 멤버를 Windows 함수를 호출 해야 `GlobalFree` 대화 상자를 사용 하 여 완료 되 면 이러한 핸들에 대 한 합니다.

대화 상자 컨트롤을 초기화 한 후 호출 하 여 `DoModal` 대화 상자를 표시 하 고 사용자가 인쇄 옵션을 선택 하도록 허용 하려면 멤버 함수입니다. 때 `DoModal` 반환 되 면 사용자 확인, 적용 또는 취소 단추를 선택 하는지 여부를 확인할 수 있습니다.

사용자 확인을 누를 경우 사용할 수 있습니다 `CPrintDialogEx`의 사용자가 입력 한 정보를 검색 하는 멤버 함수입니다.

`CPrintDialogEx::GetDefaults` 멤버 함수는 대화 상자를 표시 하지 않고 현재 프린터 기본값을 검색 하는 데 유용 합니다. 이 메서드는 사용자 개입이 필요합니다.

Windows를 사용할 수 있습니다 `CommDlgExtendedError` 함수 대화 상자를 초기화 하는 동안 오류가 발생 했는지 여부를 확인 하 고 오류에 자세히 알아보기. 이 함수에 대 한 자세한 내용은 Windows SDK를 참조 하세요.

사용 하 여 대 한 자세한 내용은 `CPrintDialogEx`를 참조 하세요 [일반 대화 상자 클래스](../../mfc/common-dialog-classes.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`IObjectWithSite`

`IPrintDialogCallback`

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPrintDialogEx`

## <a name="requirements"></a>요구 사항

**헤더:** afxdlgs.h

##  <a name="cprintdialogex"></a>  CPrintDialogEx::CPrintDialogEx

Windows 인쇄 속성 시트를 생성합니다.

```
CPrintDialogEx(
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS       | PD_HIDEPRINTTOFILE | PD_NOSELECTION | PD_NOCURRENTPAGE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*dwFlags*<br/>
비트 OR 연산자를 사용 하 여 결합 대화 상자에서 설정을 사용자 지정 하 여 하나 이상의 플래그입니다. 예를 들어 PD_ALLPAGES 플래그 문서의 모든 페이지의 기본 인쇄 범위를 설정합니다. 참조 된 [PRINTDLGEX](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa) 이러한 플래그에 대 한 자세한 내용은 Windows SDK에는 구조입니다.

*pParentWnd*<br/>
대화 상자의 부모 또는 소유자 창에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 멤버 함수는만 개체를 생성 합니다. 사용 된 `DoModal` 멤버 함수는 대화 상자를 표시 합니다.

##  <a name="createprinterdc"></a>  CPrintDialogEx::CreatePrinterDC

프린터 장치 컨텍스트 (DC)를 만듭니다.는 [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) 하 고 [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) 구조입니다.

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>반환 값

새로 만든된 프린터 장치 컨텍스트에 대 한 핸들입니다.

### <a name="remarks"></a>설명

반환 된 DC에도 저장 됩니다는 `hDC` 소속 [m_pdex](#m_pdex)합니다.

이 DC 현재 프린터 DC로 간주 됩니다 하 고 Dc 삭제 해야 하는 프린터를 이전에 가져온 모든 다른 키를 누릅니다. 이 함수를 호출 하 고 적이 인쇄 대화 상자를 표시 하지 않고 결과 DC를 사용 합니다.

##  <a name="domodal"></a>  CPrintDialogEx::DoModal

Windows 인쇄 속성 시트를 표시 하 고 사용자가 페이지 범위를 복사본의 수와 같은 다양 한 인쇄 옵션을 선택 하도록 허용 하려면이 함수를 호출 복사본 대조해 야 해야 하는지 여부 및 합니다.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>반환 값

INT_PTR 값이 실제로 HRESULT를 반환 합니다. 반환 값 섹션을 참조 하세요 [PrintDlgEx](/previous-versions/windows/desktop/legacy/ms646942\(v=vs.85\)) Windows SDK에 있습니다.

### <a name="remarks"></a>설명

멤버를 설정 하 여 다양 한 인쇄 대화 상자 옵션을 초기화 하려는 경우는 `m_pdex` 구조를 호출 하기 전에이 작업을 수행 해야 `DoModal`, 대화 상자 개체에서 생성 된 후 있지만.

호출 후 `DoModal`, 설정 또는 사용자가 정보 입력 대화 상자에 검색할 함수 다른 멤버를 호출할 수 있습니다.

호출할 때 PD_RETURNDC 플래그를 사용 하는 경우 `DoModal`, 프린터 DC에서 반환될지를 `hDC` 소속 [m_pdex](#m_pdex)합니다. 이 DC에 대 한 호출을 사용 하 여 해제 해야 합니다 [DeleteDC](/windows/desktop/api/wingdi/nf-wingdi-deletedc) 호출자가 `CPrintDialogEx`입니다.

##  <a name="getcopies"></a>  CPrintDialogEx::GetCopies

호출한 후이 함수를 호출 `DoModal` 요청 복사본 수를 검색할 수 있습니다.

```
int GetCopies() const;
```

### <a name="return-value"></a>반환 값

요청 하는 복사본 수입니다.

##  <a name="getdefaults"></a>  CPrintDialogEx::GetDefaults

대화 상자를 표시 하지 않고 장치에 대 한 기본값인 기본 프린터를 검색 하려면이 함수를 호출 합니다.

```
BOOL GetDefaults();
```

### <a name="return-value"></a>반환 값

TRUE 이면 성공적이 고, 그렇지 않으면 FALSE.

### <a name="remarks"></a>설명

프린터 장치 컨텍스트 (DC)를 만듭니다.는 [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) 하 고 [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) 구조입니다.

`GetDefaults` 인쇄 속성 시트를 표시 하지 않습니다. 설정 대신 합니다 `hDevNames` 및 `hDevMode` 멤버인 [m_pdex](#m_pdex) 에 대 한 핸들을는 [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) 및 [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) 구조에 대 한 초기화 되는 시스템 기본 프린터입니다. 둘 다 `hDevNames` 하 고 `hDevMode` 는 NULL 이어야 또는 `GetDefaults` 실패 합니다.

PD_RETURNDC 플래그가 설정 된 경우이 함수는 반환 하지 않습니다만 `hDevNames` 하 고 `hDevMode` (에 있는 `m_pdex.hDevNames` 및 `m_pdex.hDevMode`) 호출자에 게에서 프린터 DC도 반환 됩니다 `m_pdex.hDC`합니다. DC 프린터를 삭제 하는 Windows를 호출 하는 호출자의 책임이 [GlobalFree](/windows/desktop/api/winbase/nf-winbase-globalfree) 완료 했으면 핸들에 대해 함수를 `CPrintDialogEx` 개체입니다.

##  <a name="getdevicename"></a>  CPrintDialogEx::GetDeviceName

호출한 후이 함수를 호출 [DoModal](#domodal) 호출한 후 또는 현재 선택 된 프린터의 이름을 검색할 [GetDefaults](#getdefaults) 기본 프린터의 이름을 검색 합니다.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>반환 값

현재 선택한 프린터의 이름입니다.

### <a name="remarks"></a>설명

에 대 한 포인터를 사용 합니다 `CString` 에서 반환 된 개체 `GetDeviceName` 값으로 `lpszDeviceName` 호출에서 [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).

##  <a name="getdevmode"></a>  CPrintDialogEx::GetDevMode

이 함수를 호출한 후 호출 [DoModal](#domodal) 또는 [GetDefaults](#getdefaults) 인쇄 장치에 대 한 정보를 검색 합니다.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>반환 값

합니다 [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) 장치 초기화 및 인쇄 드라이버의 환경에 대 한 정보를 포함 하는 데이터 구조입니다. 이 구조는 Windows 사용 하 여 가져온 메모리가 잠금을 해제 해야 합니다 [GlobalUnlock](/windows/desktop/api/winbase/nf-winbase-globalunlock) Windows SDK에 설명 된 함수입니다.

##  <a name="getdrivername"></a>  CPrintDialogEx::GetDriverName

호출한 후이 함수를 호출 [DoModal](#domodal) 또는 [GetDefaults](#getdefaults) 시스템 정의 프린터 장치 드라이버의 이름을 검색 합니다.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>반환 값

`CString` 드라이버 시스템 정의 이름을 지정 합니다.

### <a name="remarks"></a>설명

에 대 한 포인터를 사용 합니다 `CString` 에서 반환 된 개체 `GetDriverName` 값으로 *lpszDriverName* 호출에서 [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)합니다.

##  <a name="getportname"></a>  CPrintDialogEx::GetPortName

호출한 후이 함수를 호출 [DoModal](#domodal) 또는 [GetDefaults](#getdefaults) 현재 선택 된 프린터 포트의 이름을 검색 합니다.

```
CString GetPortName() const;
```

### <a name="return-value"></a>반환 값

현재 선택 된 프린터 포트의 이름입니다.

##  <a name="getprinterdc"></a>  CPrintDialogEx::GetPrinterDC

프린터 장치 컨텍스트 핸들을 반환합니다.

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>반환 값

프린터 장치 컨텍스트 핸들입니다.

### <a name="remarks"></a>설명

Windows를 호출 해야 합니다 [DeleteDC](/windows/desktop/api/wingdi/nf-wingdi-deletedc) 함수 완료 되 면 장치 컨텍스트를 삭제 하려면 사용 합니다.

##  <a name="m_pdex"></a>  CPrintDialogEx::m_pdex

대화 상자 개체의 특성을 저장 하는 멤버가 PRINTDLGEX 구조체입니다.

```
PRINTDLGEX m_pdex;
```

### <a name="remarks"></a>설명

생성 한 후는 `CPrintDialogEx` 개체를 사용할 수 있습니다 `m_pdex` 호출 하기 전에 대화 상자의 다양 한 측면을 설정 하는 [DoModal](#domodal) 멤버 함수입니다. 대 한 자세한 내용은 합니다 `m_pdex` 구조체를 참조 하세요 [PRINTDLGEX](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa) Windows SDK에 있습니다.

수정 하는 경우는 `m_pdex` 데이터 멤버는 기본 동작을 재정의 직접.

##  <a name="printall"></a>  CPrintDialogEx::PrintAll

이 함수를 호출한 후 호출 `DoModal` 문서에서 모든 페이지를 인쇄할 것인지 여부를 결정 합니다.

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>반환 값

문서의 모든 페이지가; 인쇄 하려는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="printcollate"></a>  CPrintDialogEx::PrintCollate

이 함수를 호출한 후 호출 `DoModal` 프린터 문서의 모든 인쇄 된 복사본이 collate 해야 하는지 여부를 확인 하려면.

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>반환 값

사용자가 대화 상자의 collate 확인란을 선택 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="printcurrentpage"></a>  CPrintDialogEx::PrintCurrentPage

이 함수를 호출한 후 호출 `DoModal` 문서의 현재 페이지를 인쇄할 것인지 여부를 결정 합니다.

```
BOOL PrintCurrentPage() const;
```

### <a name="return-value"></a>반환 값

TRUE 이면 **현재 페이지 인쇄** 인쇄 대화 상자에서 선택한 이면, 그렇지 않으면 FALSE입니다.

##  <a name="printrange"></a>  CPrintDialogEx::PrintRange

이 함수를 호출한 후 호출 `DoModal` 문서의 페이지의 하위 범위만 인쇄할지 여부를 확인 하려면.

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>반환 값

문서에서 페이지 범위 인쇄;만 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

지정한 페이지 범위를 확인할 수 있습니다 [m_pdex](#m_pdex) (참조 `nPageRanges`를 `nMaxPageRanges`, 및 `lpPageRanges` 에 [PRINTDLGEX](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa) Windows SDK의 구조).

##  <a name="printselection"></a>  CPrintDialogEx::PrintSelection

이 함수를 호출한 후 호출 `DoModal` 현재 선택한 항목만 인쇄 여부를 결정 합니다.

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>반환 값

선택한 항목을 인쇄할;만 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

## <a name="see-also"></a>참고자료

[CCommonDialog 클래스](../../mfc/reference/ccommondialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CPrintInfo 구조체](../../mfc/reference/cprintinfo-structure.md)
