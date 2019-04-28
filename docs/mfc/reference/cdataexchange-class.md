---
title: CDataExchange 클래스
ms.date: 11/04/2016
f1_keywords:
- CDataExchange
- AFXWIN/CDataExchange
- AFXWIN/CDataExchange::CDataExchange
- AFXWIN/CDataExchange::Fail
- AFXWIN/CDataExchange::PrepareCtrl
- AFXWIN/CDataExchange::PrepareEditCtrl
- AFXWIN/CDataExchange::PrepareOleCtrl
- AFXWIN/CDataExchange::m_bSaveAndValidate
- AFXWIN/CDataExchange::m_pDlgWnd
helpviewer_keywords:
- CDataExchange [MFC], CDataExchange
- CDataExchange [MFC], Fail
- CDataExchange [MFC], PrepareCtrl
- CDataExchange [MFC], PrepareEditCtrl
- CDataExchange [MFC], PrepareOleCtrl
- CDataExchange [MFC], m_bSaveAndValidate
- CDataExchange [MFC], m_pDlgWnd
ms.assetid: 84ed6113-325d-493e-a75d-223f03a992b8
ms.openlocfilehash: 0e7a9d429acb1acd72942e5f10ac0815232ddc69
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62253571"
---
# <a name="cdataexchange-class"></a>CDataExchange 클래스

Microsoft Foundation 클래스에서 사용되는 DDX(대화 상자 데이터 교환) 및 DDV(대화 상자 데이터 유효성 검사) 루틴을 지원합니다.

## <a name="syntax"></a>구문

```
class CDataExchange
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CDataExchange::CDataExchange](#cdataexchange)|`CDataExchange` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CDataExchange::Fail](#fail)|유효성 검사가 실패할 때 호출 됩니다. 이전 컨트롤로 포커스를 다시 설정 하 고 예외를 throw 합니다.|
|[CDataExchange::PrepareCtrl](#preparectrl)|데이터 교환 또는 유효성 검사에 대 한 지정된 된 컨트롤을 준비합니다. Nonedit 컨트롤에 사용 됩니다.|
|[CDataExchange::PrepareEditCtrl](#prepareeditctrl)|데이터 교환 또는 유효성 검사에 대 한 지정 된 편집 컨트롤을 준비합니다.|
|[CDataExchange::PrepareOleCtrl](#prepareolectrl)|데이터 교환 또는 유효성 검사에 대 한 지정된 된 OLE 컨트롤을 준비합니다. Nonedit 컨트롤에 사용 됩니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CDataExchange::m_bSaveAndValidate](#m_bsaveandvalidate)|DDX 및 DDV의 방향에 대 한 플래그입니다.|
|[CDataExchange::m_pDlgWnd](#m_pdlgwnd)|데이터를 교환할 대화 상자 또는 창에 수행이 됩니다.|

## <a name="remarks"></a>설명

`CDataExchange` 기본 클래스는 없습니다.

사용자 지정 데이터 형식 또는 컨트롤에 대 한 데이터 교환 루틴을 작성 하는 경우이 클래스를 사용 하거나 사용자 고유의 데이터 유효성 검사 루틴을 작성 하는 경우. 사용자 고유의 DDX 및 DDV 루틴을 작성에 대 한 자세한 내용은 참조 하세요. [기술 참고 26](../../mfc/tn026-ddx-and-ddv-routines.md)합니다. DDX 및 DDV 개요를 참조 하세요 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md) 하 고 [대화 상자](../../mfc/dialog-boxes.md)합니다.

`CDataExchange` DDX 및 DDV 되려면 배치 하는 데 필요한 컨텍스트 정보를 제공 하는 개체입니다. 플래그 *m_bSaveAndValidate* DDX는 데이터 멤버에서 대화 상자 컨트롤의 초기 값을 채우는 데 사용 되는 경우는 FALSE입니다. 플래그 *m_bSaveAndValidate* DDX는 데이터 멤버 및 DDV 데이터 값의 유효성 검사에 사용 되는 경우 대화 상자 컨트롤의 현재 값을 설정 하는 데 사용 되는 TRUE입니다. DDV 유효성 검사에 실패할 경우 DDV 프로시저에 입력된 오류를 설명 하는 메시지 상자가 표시 됩니다. DDV 프로시저 호출 다음 `Fail` 에 잘못 된 컨트롤에 포커스를 다시 설정 하 고 유효성 검사 프로세스를 중지 하려면 예외를 throw 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CDataExchange`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="cdataexchange"></a>  CDataExchange::CDataExchange

생성 하려면이 멤버 함수 호출을 `CDataExchange` 개체입니다.

```
CDataExchange(
    CWnd* pDlgWnd,
    BOOL bSaveAndValidate);
```

### <a name="parameters"></a>매개 변수

*pDlgWnd*<br/>
컨트롤이 포함 된 부모 창에 대 한 포인터입니다. 이 일반적으로 [CDialog](../../mfc/reference/cdialog-class.md)-파생 개체입니다.

*bSaveAndValidate*<br/>
True 이면이 개체 데이터의 유효성을 검사 다음 멤버를 컨트롤에서 데이터를 씁니다. FALSE 이면이 개체는 컨트롤에 데이터를 멤버에서 이동 됩니다.

### <a name="remarks"></a>설명

생성 된 `CDataExchange` 개체 프로그램 창에 전달 하는 데이터 교환 개체에 추가 정보를 저장 하기 위해 직접 [CWnd::DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange) 멤버 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#70](../../mfc/codesnippet/cpp/cdataexchange-class_1.cpp)]

##  <a name="fail"></a>  CDataExchange::Fail

프레임 워크는 대화 상자 데이터 유효성 검사 (DDV) 작업이 실패 하면이 멤버 함수를 호출 합니다.

```
void Fail();
```

### <a name="remarks"></a>설명

`Fail` 해당 유효성 검사 실패 (있는 경우 복원 하기 위한 컨트롤) 컨트롤에 포커스 및 선택 영역을 복원 합니다. `Fail` 다음 형식의 예외를 throw [CUserException](../../mfc/reference/cuserexception-class.md) 유효성 검사 프로세스를 중지 합니다. 예외로 인해 표시할 오류를 설명 하는 메시지 상자입니다. DDV 유효성 검사에 실패 한 후 사용자는 잘못 된 컨트롤의 데이터 다시 입력할 수 있습니다.

사용자 지정 DDV 루틴의 구현자를 호출할 수 `Fail` 유효성 검사가 실패할 때 자신의 루틴에서 합니다.

사용자 고유의 DDX 및 DDV 루틴을 작성에 대 한 자세한 내용은 참조 하세요. [기술 참고 26](../../mfc/tn026-ddx-and-ddv-routines.md)합니다. DDX 및 DDV 개요를 참조 하세요 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md) 하 고 [대화 상자 항목](../../mfc/dialog-boxes.md)합니다.

##  <a name="m_bsaveandvalidate"></a>  CDataExchange::m_bSaveAndValidate

이 플래그는 대화 상자 데이터 교환 (DDX) 작업의 방향을 나타냅니다.

```
BOOL m_bSaveAndValidate;
```

### <a name="remarks"></a>설명

플래그는 0이 아닌 경우는 `CDataExchange` 개체는 데 사용자가 컨트롤을 편집 후 대화 상자 컨트롤에서 데이터를 대화 상자 클래스 데이터 멤버를 이동 합니다. 대화 상자 클래스 데이터 멤버에서 대화 상자 컨트롤을 초기화 하는 개체를 사용 하는 경우 플래그는 0입니다.

플래그 중 대화 상자 데이터 유효성 검사 (DDV) 0이 아닌 이기도합니다.

사용자 고유의 DDX 및 DDV 루틴을 작성에 대 한 자세한 내용은 참조 하세요. [기술 참고 26](../../mfc/tn026-ddx-and-ddv-routines.md)합니다. DDX 및 DDV 개요를 참조 하세요 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md) 하 고 [대화 상자 항목](../../mfc/dialog-boxes.md)합니다.

##  <a name="m_pdlgwnd"></a>  CDataExchange::m_pDlgWnd

에 대 한 포인터를 포함 합니다 [CWnd](../../mfc/reference/cwnd-class.md) 개체는 대화에 대 한 DDX (데이터 교환) 또는 유효성 검사 (DDV)을 수행 합니다.

```
CWnd* m_pDlgWnd;
```

### <a name="remarks"></a>설명

이 개체는 일반적으로 [CDialog](../../mfc/reference/cdialog-class.md) 개체입니다. 사용자 지정 DDX 또는 DDV 루틴의 구현자에서 작동 하는 컨트롤이 포함 된 대화 상자 창에 대 한 액세스를 얻으려면이 포인터를 사용할 수 있습니다.

사용자 고유의 DDX 및 DDV 루틴을 작성에 대 한 자세한 내용은 참조 하세요. [기술 참고 26](../../mfc/tn026-ddx-and-ddv-routines.md)합니다. DDX 및 DDV 개요를 참조 하세요 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md) 하 고 [대화 상자 항목](../../mfc/dialog-boxes.md)합니다.

##  <a name="preparectrl"></a>  CDataExchange::PrepareCtrl

프레임 워크 (DDX) 대화 상자 데이터 교환 및 유효성 검사 (DDV)에 지정된 된 컨트롤을 준비 하려면이 멤버 함수를 호출 합니다.

```
HWND PrepareCtrl(int nIDC);
```

### <a name="parameters"></a>매개 변수

*nIDC*<br/>
DDX 또는 DDV 준비 될 컨트롤의 ID입니다.

### <a name="return-value"></a>반환 값

DDX 또는 DDV 준비 중인 컨트롤의 HWND입니다.

### <a name="remarks"></a>설명

사용 하 여 [PrepareEditCtrl](#prepareeditctrl) 대신 편집 컨트롤에 대 한 다른 모든 컨트롤에 대 한이 멤버 함수를 사용 합니다.

준비에서 컨트롤의 HWND를 저장 하는 구성 된 `CDataExchange` 클래스입니다. 프레임 워크는이 핸들을 사용 하 여 DDX 또는 DDV 오류가 발생할 경우 이전에 포커스가 있는 컨트롤에 포커스를 복원 합니다.

사용자 지정 DDX 또는 DDV 루틴의 구현자를 호출 해야 `PrepareCtrl` 는 DDX 통해 데이터를 교환 하거나 DDV 통해 데이터를 유효성을 검사 하는 모든 비 편집 컨트롤에 대 한 합니다.

사용자 고유의 DDX 및 DDV 루틴을 작성에 대 한 자세한 내용은 참조 하세요. [기술 참고 26](../../mfc/tn026-ddx-and-ddv-routines.md)합니다. DDX 및 DDV 개요를 참조 하세요 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md) 하 고 [대화 상자 항목](../../mfc/dialog-boxes.md)합니다.

##  <a name="prepareeditctrl"></a>  CDataExchange::PrepareEditCtrl

프레임 워크 (DDX) 대화 상자 데이터 교환 및 유효성 검사 (DDV)에 지정 된 편집 컨트롤을 준비 하려면이 멤버 함수를 호출 합니다.

```
HWND PrepareEditCtrl(int nIDC);
```

### <a name="parameters"></a>매개 변수

*nIDC*<br/>
DDX에 DDV 준비 편집 컨트롤의 ID입니다.

### <a name="return-value"></a>반환 값

DDX 또는 DDV 준비 중인 편집 컨트롤의 HWND입니다.

### <a name="remarks"></a>설명

사용 하 여 [PrepareCtrl](#preparectrl) 대신 모든 비 편집 컨트롤에 대 한 합니다.

준비 두 가지 이루어져 있습니다. 먼저 `PrepareEditCtrl` 컨트롤의 HWND에 저장 된 `CDataExchange` 클래스. 프레임 워크는이 핸들을 사용 하 여 DDX 또는 DDV 오류가 발생할 경우 이전에 포커스가 있는 컨트롤에 포커스를 복원 합니다. 두 번째 `PrepareEditCtrl` 에 플래그를 설정 합니다 `CDataExchange` 되도록 클래스에 데이터가 교환 되는 또는 유효성을 검사 하는 것은 편집 컨트롤 컨트롤입니다.

사용자 지정 DDX 또는 DDV 루틴의 구현자를 호출 해야 `PrepareEditCtrl` 모든 편집는 DDX 통해 데이터를 교환 하거나 DDV 통해 데이터를 유효성을 검사 하는 컨트롤에 대 한 합니다.

사용자 고유의 DDX 및 DDV 루틴을 작성에 대 한 자세한 내용은 참조 하세요. [기술 참고 26](../../mfc/tn026-ddx-and-ddv-routines.md)합니다. DDX 및 DDV 개요를 참조 하세요 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md) 하 고 [대화 상자 항목](../../mfc/dialog-boxes.md)합니다.

##  <a name="prepareolectrl"></a>  CDataExchange::PrepareOleCtrl

프레임 워크 (DDX) 대화 상자 데이터 교환 및 유효성 검사 (DDV)에 지정된 된 OLE 컨트롤을 준비 하려면이 멤버 함수를 호출 합니다.

```
COleControlSite* PrepareOleCtrl(int nIDC);
```

### <a name="parameters"></a>매개 변수

*nIDC*<br/>
DDX에 DDV 준비 OLE 컨트롤의 ID입니다.

### <a name="return-value"></a>반환 값

OLE 컨트롤 사이트에 대 한 포인터입니다.

### <a name="remarks"></a>설명

사용 하 여 [PrepareEditCtrl](#prepareeditctrl) 대신 편집 컨트롤에 대 한 나 [PrepareCtrl](#preparectrl) 다른 모든 비 OLE 컨트롤에 대 한 합니다.

사용자 지정 DDX 또는 DDV 루틴의 구현자를 호출 해야 `PrepareOleCtrl` 는 DDX 통해 데이터를 교환 하거나 DDV 통해 데이터를 유효성을 검사 하는 모든 OLE 컨트롤에 대 한 합니다.

사용자 고유의 DDX 및 DDV 루틴을 작성에 대 한 자세한 내용은 참조 하세요. [기술 참고 26](../../mfc/tn026-ddx-and-ddv-routines.md)합니다. DDX 및 DDV 개요를 참조 하세요 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md) 하 고 [대화 상자 항목](../../mfc/dialog-boxes.md)합니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 VIEWEX](../../overview/visual-cpp-samples.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CWnd::DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange)<br/>
[CWnd::UpdateData](../../mfc/reference/cwnd-class.md#updatedata)
