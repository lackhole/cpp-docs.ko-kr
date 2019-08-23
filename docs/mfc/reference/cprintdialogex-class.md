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
ms.openlocfilehash: ebef892e174525c0b907818c02b7d34b1b41f850
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916892"
---
# <a name="cprintdialogex-class"></a>CPrintDialogEx 클래스

Windows 인쇄 속성 시트에서 제공 하는 서비스를 캡슐화 합니다.

## <a name="syntax"></a>구문

```
class CPrintDialogEx : public CCommonDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|Description|
|----------|-----------------|
|[CPrintDialogEx::CPrintDialogEx](#cprintdialogex)|`CPrintDialogEx` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CPrintDialogEx::CreatePrinterDC](#createprinterdc)|인쇄 대화 상자를 표시 하지 않고 프린터 장치 컨텍스트를 만듭니다.|
|[CPrintDialogEx::DoModal](#domodal)|사용자가 선택할 수 있도록 대화 상자를 표시 합니다.|
|[CPrintDialogEx::GetCopies](#getcopies)|요청 된 복사본 수를 검색 합니다.|
|[CPrintDialogEx::GetDefaults](#getdefaults)|대화 상자를 표시 하지 않고 장치 기본값을 검색 합니다.|
|[CPrintDialogEx::GetDeviceName](#getdevicename)|현재 선택 된 프린터 장치의 이름을 검색 합니다.|
|[CPrintDialogEx::GetDevMode](#getdevmode)|구조체를 `DEVMODE` 검색 합니다.|
|[CPrintDialogEx::GetDriverName](#getdrivername)|시스템 정의 프린터 장치 드라이버의 이름을 검색 합니다.|
|[CPrintDialogEx::GetPortName](#getportname)|현재 선택 된 프린터 포트의 이름을 검색 합니다.|
|[CPrintDialogEx::GetPrinterDC](#getprinterdc)|프린터 장치 컨텍스트에 대 한 핸들을 검색 합니다.|
|[CPrintDialogEx::PrintAll](#printall)|문서의 모든 페이지를 인쇄할지 여부를 결정 합니다.|
|[CPrintDialogEx::PrintCollate](#printcollate)|정렬 된 복사본이 요청 되는지 여부를 결정 합니다.|
|[CPrintDialogEx::PrintCurrentPage](#printcurrentpage)|문서의 현재 페이지를 인쇄할지 여부를 결정 합니다.|
|[CPrintDialogEx::PrintRange](#printrange)|지정 된 페이지 범위만 인쇄할지 여부를 결정 합니다.|
|[CPrintDialogEx::PrintSelection](#printselection)|현재 선택 된 항목만 인쇄할지 여부를 결정 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CPrintDialogEx::m_pdex](#m_pdex)|`CPrintDialogEx` 개체를 사용자 지정 하는 데 사용 되는 구조체입니다.|

## <a name="remarks"></a>설명

프레임 워크를 사용 하 여 응용 프로그램에 대 한 인쇄 프로세스의 여러 측면을 처리할 수 있습니다. 프레임 워크를 사용 하 여 인쇄 작업을 처리 하는 방법에 대 한 자세한 내용은 [인쇄](../../mfc/printing.md)문서를 참조 하세요.

응용 프로그램에서 프레임 워크의 개입 없이 인쇄를 처리 하려는 경우 제공 된 생성자를 사용 `CPrintDialogEx` 하 여 "있는 그대로" 클래스를 사용 하거나,에서 `CPrintDialogEx` 사용자의 대화 상자 클래스를 파생 시키고 필요에 맞게 생성자를 작성할 수 있습니다. 두 경우 모두 이러한 대화 상자는 클래스 `CCommonDialog`에서 파생 되므로 표준 MFC 대화 상자 처럼 동작 합니다.

`CPrintDialogEx` 개체를 사용 하려면 먼저 `CPrintDialogEx` 생성자를 사용 하 여 개체를 만듭니다. 대화 상자를 생성 한 후에는 [m_pdex](#m_pdex) 구조체의 값을 설정 하거나 수정 하 여 대화 상자의 컨트롤 값을 초기화할 수 있습니다. 구조 `m_pdex` 는 [PRINTDLGEX](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa)형식입니다. 이 구조에 대 한 자세한 내용은 Windows SDK를 참조 하세요.

`m_pdex` `GlobalFree` 및 멤버`hDevNames` 에 대해 고유한 핸들을 제공 하지 않는 경우 대화 상자를 사용 하 여 작업을 완료 하면 이러한 핸들에 대해 Windows 함수를 `hDevMode` 호출 해야 합니다.

대화 상자 컨트롤을 초기화 한 후 `DoModal` 멤버 함수를 호출 하 여 대화 상자를 표시 하 고 사용자가 인쇄 옵션을 선택할 수 있습니다. 가 `DoModal` 반환 되 면 사용자가 확인, 적용 또는 취소 단추를 선택 했는지 여부를 확인할 수 있습니다.

사용자가 확인을 누르면의 멤버 함수를 `CPrintDialogEx`사용 하 여 사용자가 입력 한 정보를 검색할 수 있습니다.

`CPrintDialogEx::GetDefaults` 멤버 함수는 대화 상자를 표시 하지 않고 현재 프린터 기본값을 검색 하는 데 유용 합니다. 이 메서드는 사용자 조작이 필요 하지 않습니다.

Windows `CommDlgExtendedError` 함수를 사용 하 여 대화 상자를 초기화 하는 동안 오류가 발생 했는지 확인 하 고 오류에 대해 자세히 알아볼 수 있습니다. 이 함수에 대 한 자세한 내용은 Windows SDK를 참조 하세요.

사용 `CPrintDialogEx`에 대 한 자세한 내용은 [일반 대화 상자 클래스](../../mfc/common-dialog-classes.md)를 참조 하세요.

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`IObjectWithSite`

`IPrintDialogCallback`

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPrintDialogEx`

## <a name="requirements"></a>요구 사항

**헤더:** afxdlgs

##  <a name="cprintdialogex"></a>  CPrintDialogEx::CPrintDialogEx

Windows 인쇄 속성 시트를 생성 합니다.

```
CPrintDialogEx(
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS       | PD_HIDEPRINTTOFILE | PD_NOSELECTION | PD_NOCURRENTPAGE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*dwFlags*<br/>
비트 OR 연산자를 사용 하 여 대화 상자의 설정을 사용자 지정 하는 데 사용할 수 있는 하나 이상의 플래그입니다. 예를 들어 PD_ALLPAGES 플래그는 문서의 모든 페이지에 기본 인쇄 범위를 설정 합니다. 이러한 플래그에 대 한 자세한 내용은 Windows SDK의 [PRINTDLGEX](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa) 구조를 참조 하세요.

*pParentWnd*<br/>
대화 상자의 부모 또는 소유자 창에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 개체만 생성 합니다. `DoModal` 멤버 함수를 사용 하 여 대화 상자를 표시 합니다.

##  <a name="createprinterdc"></a>  CPrintDialogEx::CreatePrinterDC

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) 및 [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) 구조에서 프린터 DC (장치 컨텍스트)를 만듭니다.

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>반환 값

새로 만든 프린터 장치 컨텍스트에 대 한 핸들입니다.

### <a name="remarks"></a>설명

반환 된 DC는 `hDC` [m_pdex](#m_pdex)의 구성원에도 저장 됩니다.

이 DC는 현재 프린터 DC로 간주 되며 이전에 가져온 다른 프린터 Dc를 삭제 해야 합니다. 이 함수를 호출 하 고, 결과 DC를 사용 하 여 인쇄 대화 상자를 표시 하지 않을 수 있습니다.

##  <a name="domodal"></a>  CPrintDialogEx::DoModal

이 함수를 호출 하 여 Windows 인쇄 속성 시트를 표시 하 고 사용자가 복사본 수, 페이지 범위, 복사본의 정렬 여부와 같은 다양 한 인쇄 옵션을 선택할 수 있습니다.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>반환 값

INT_PTR 반환 값은 실제로 HRESULT입니다. Windows SDK에서 [PrintDlgEx](/previous-versions/windows/desktop/legacy/ms646942\(v=vs.85\)) 의 반환 값 섹션을 참조 하십시오.

### <a name="remarks"></a>설명

`m_pdex` 구조체의 멤버를 설정 하 여 다양 한 인쇄 대화 상자 옵션을 초기화 하려면를 호출 `DoModal`하기 전에이 작업을 수행 해야 합니다. 단, 대화 상자 개체가 생성 된 후에는이 작업을 수행 해야 합니다.

를 호출한 `DoModal`후에는 다른 멤버 함수를 호출 하 여 사용자가 대화 상자에 입력 한 설정 또는 정보를 검색할 수 있습니다.

를 호출할 `DoModal`때 PD_RETURNDC 플래그를 사용 하면 프린터 DC가 [m_pdex](#m_pdex)의 `hDC` 구성원에 반환 됩니다. 호출자`CPrintDialogEx`가 [DeleteDC](/windows/desktop/api/wingdi/nf-wingdi-deletedc) 를 호출 하 여이 DC를 해제 해야 합니다.

##  <a name="getcopies"></a>  CPrintDialogEx::GetCopies

요청 된 복사본 수를 `DoModal` 검색 하기 위해를 호출한 후이 함수를 호출 합니다.

```
int GetCopies() const;
```

### <a name="return-value"></a>반환 값

요청 된 복사본의 수입니다.

##  <a name="getdefaults"></a>  CPrintDialogEx::GetDefaults

대화 상자를 표시 하지 않고 기본 프린터의 장치 기본값을 검색 하려면이 함수를 호출 합니다.

```
BOOL GetDefaults();
```

### <a name="return-value"></a>반환 값

성공 하면 TRUE이 고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) 및 [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) 구조에서 프린터 DC (장치 컨텍스트)를 만듭니다.

`GetDefaults`인쇄 속성 시트를 표시 하지 않습니다. 대신, `hDevNames` [m_pdex](#m_pdex) 의 및 `hDevMode` 멤버가 시스템 기본 프린터에 대해 초기화 된 [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) 및 [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) 구조체를 처리 하도록 설정 합니다. `GetDefaults` 및 `hDevNames` 는모두NULL이거나실패합니다`hDevMode` .

PD_RETURNDC 플래그가 설정 된 경우이 함수 `hDevNames` 는 및 `hDevMode` (및 `m_pdex.hDevMode`에 `m_pdex.hDevNames` 있음)를 호출자에 게 반환 하지만에서 `m_pdex.hDC`프린터 DC도 반환 합니다. 호출자가 `CPrintDialogEx` 개체를 마치면 핸들에서 프린터 DC를 삭제 하 고 Windows [globalfree](/windows/desktop/api/winbase/nf-winbase-globalfree) 함수를 호출 해야 합니다.

##  <a name="getdevicename"></a>  CPrintDialogEx::GetDeviceName

[DoModal](#domodal) 을 호출 하 여 현재 선택 된 프린터의 이름을 검색 하거나 [getdefaults](#getdefaults) 를 호출 하 여 기본 프린터의 이름을 검색 한 후이 함수를 호출 합니다.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>반환 값

현재 선택 된 프린터의 이름입니다.

### <a name="remarks"></a>설명

`GetDeviceName`에서 반환 하는 `CString`개체에 대 한 포인터를 [CDC:: CreateDC](../../mfc/reference/cdc-class.md#createdc)에 대한 호출에서 `lpszDeviceName`값으로 사용 합니다.

##  <a name="getdevmode"></a>  CPrintDialogEx::GetDevMode

[DoModal](#domodal) 또는 [getdefaults](#getdefaults) 를 호출한 후이 함수를 호출 하 여 인쇄 장치에 대 한 정보를 검색 합니다.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>반환 값

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) 데이터 구조로, 장치 초기화 및 인쇄 드라이버 환경에 대 한 정보가 포함 되어 있습니다. Windows SDK에서 설명 하는 Windows [globalunlock](/windows/desktop/api/winbase/nf-winbase-globalunlock) 함수를 사용 하 여이 구조에서 사용 하는 메모리의 잠금을 해제 해야 합니다.

##  <a name="getdrivername"></a>  CPrintDialogEx::GetDriverName

[DoModal](#domodal) 또는 [getdefaults](#getdefaults) 를 호출한 후이 함수를 호출 하 여 시스템 정의 프린터 장치 드라이버의 이름을 검색 합니다.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>반환 값

시스템 `CString` 정의 드라이버 이름을 지정 하는입니다.

### <a name="remarks"></a>설명

`GetDriverName`에서 반환 하는 `CString` 개체에 대한 포인터를 [CDC:: CreateDC](../../mfc/reference/cdc-class.md#createdc)에 대한 호출의 *lpszDriverName* 값으로 사용 합니다.

##  <a name="getportname"></a>  CPrintDialogEx::GetPortName

[DoModal](#domodal) 또는 [getdefaults](#getdefaults) 를 호출한 후이 함수를 호출 하 여 현재 선택 된 프린터 포트의 이름을 검색 합니다.

```
CString GetPortName() const;
```

### <a name="return-value"></a>반환 값

현재 선택 된 프린터 포트의 이름입니다.

##  <a name="getprinterdc"></a>  CPrintDialogEx::GetPrinterDC

프린터 장치 컨텍스트에 대 한 핸들을 반환 합니다.

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>반환 값

프린터 장치 컨텍스트에 대 한 핸들입니다.

### <a name="remarks"></a>설명

장치 컨텍스트를 사용 하는 경우 장치 컨텍스트를 삭제 하려면 Windows [DeleteDC](/windows/desktop/api/wingdi/nf-wingdi-deletedc) 함수를 호출 해야 합니다.

##  <a name="m_pdex"></a>  CPrintDialogEx::m_pdex

해당 멤버가 dialog 개체의 특성을 저장 하는 PRINTDLGEX 구조체입니다.

```
PRINTDLGEX m_pdex;
```

### <a name="remarks"></a>설명

`CPrintDialogEx` 개체를 생성 한 후에는 [DoModal](#domodal) 멤버 함수를 호출 하기 전에를 사용 `m_pdex` 하 여 대화 상자의 다양 한 측면을 설정할 수 있습니다. `m_pdex` 구조에 대 한 자세한 내용은 Windows SDK에서 [PRINTDLGEX](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa) 을 참조 하세요.

`m_pdex` 데이터 멤버를 직접 수정 하는 경우 모든 기본 동작을 재정의 합니다.

##  <a name="printall"></a>  CPrintDialogEx::PrintAll

를 호출한 `DoModal` 후이 함수를 호출 하 여 문서의 모든 페이지를 인쇄할지 여부를 결정 합니다.

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>반환 값

문서의 모든 페이지를 인쇄 하려면 TRUE이 고, 그렇지 않으면 FALSE입니다.

##  <a name="printcollate"></a>  CPrintDialogEx::PrintCollate

를 호출한 `DoModal` 후이 함수를 호출 하 여 프린터에서 문서의 모든 인쇄 된 복사본을 정렬 해야 하는지 여부를 확인 합니다.

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>반환 값

사용자가 대화 상자에서 collate 확인란을 선택 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="printcurrentpage"></a>  CPrintDialogEx::PrintCurrentPage

을 호출 `DoModal` 하 고 문서에서 현재 페이지를 인쇄할지 여부를 결정 하려면이 함수를 호출 합니다.

```
BOOL PrintCurrentPage() const;
```

### <a name="return-value"></a>반환 값

인쇄 대화 상자에서 **현재 인쇄 페이지** 를 선택한 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="printrange"></a>  CPrintDialogEx::PrintRange

문서에서 페이지 범위만 인쇄할지 `DoModal` 여부를 확인 하려면를 호출한 후이 함수를 호출 합니다.

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>반환 값

문서의 페이지 범위만 인쇄 해야 하면 TRUE이 고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

지정 된 페이지 범위는 [m_pdex](#m_pdex) 에서 확인할 수 있습니다 ( `nPageRanges`Windows SDK `nMaxPageRanges`의 [PRINTDLGEX](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa) 구조에서, 및 `lpPageRanges` 참조).

##  <a name="printselection"></a>  CPrintDialogEx::PrintSelection

를 호출한 `DoModal` 후이 함수를 호출 하 여 현재 선택 된 항목만 인쇄할지 여부를 확인 합니다.

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>반환 값

선택한 항목만 인쇄 하려면 TRUE이 고, 그렇지 않으면 FALSE입니다.

## <a name="see-also"></a>참고자료

[CCommonDialog 클래스](../../mfc/reference/ccommondialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CPrintInfo 구조체](../../mfc/reference/cprintinfo-structure.md)
