---
title: COleDispatchDriver 클래스
ms.date: 11/04/2016
f1_keywords:
- COleDispatchDriver
- AFXDISP/COleDispatchDriver
- AFXDISP/COleDispatchDriver::COleDispatchDriver
- AFXDISP/COleDispatchDriver::AttachDispatch
- AFXDISP/COleDispatchDriver::CreateDispatch
- AFXDISP/COleDispatchDriver::DetachDispatch
- AFXDISP/COleDispatchDriver::GetProperty
- AFXDISP/COleDispatchDriver::InvokeHelper
- AFXDISP/COleDispatchDriver::ReleaseDispatch
- AFXDISP/COleDispatchDriver::SetProperty
- AFXDISP/COleDispatchDriver::m_bAutoRelease
- AFXDISP/COleDispatchDriver::m_lpDispatch
helpviewer_keywords:
- COleDispatchDriver [MFC], COleDispatchDriver
- COleDispatchDriver [MFC], AttachDispatch
- COleDispatchDriver [MFC], CreateDispatch
- COleDispatchDriver [MFC], DetachDispatch
- COleDispatchDriver [MFC], GetProperty
- COleDispatchDriver [MFC], InvokeHelper
- COleDispatchDriver [MFC], ReleaseDispatch
- COleDispatchDriver [MFC], SetProperty
- COleDispatchDriver [MFC], m_bAutoRelease
- COleDispatchDriver [MFC], m_lpDispatch
ms.assetid: 3ed98daf-cdc7-4374-8a0c-cf695a8d3657
ms.openlocfilehash: c0c1fd14105bae3b5413f92b547339ccabf3bb91
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64341609"
---
# <a name="coledispatchdriver-class"></a>COleDispatchDriver 클래스

OLE 자동화의 클라이언트 쪽을 구현합니다.

## <a name="syntax"></a>구문

```
class COleDispatchDriver
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[COleDispatchDriver::COleDispatchDriver](#coledispatchdriver)|`COleDispatchDriver` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[COleDispatchDriver::AttachDispatch](#attachdispatch)|연결 프로그램 `IDispatch` 연결할을 `COleDispatchDriver` 개체입니다.|
|[COleDispatchDriver::CreateDispatch](#createdispatch)|만듭니다는 `IDispatch` 연결에 연결 하 고는 `COleDispatchDriver` 개체입니다.|
|[COleDispatchDriver::DetachDispatch](#detachdispatch)|분리는 `IDispatch` 해제 하지 않고 연결 합니다.|
|[COleDispatchDriver::GetProperty](#getproperty)|자동화 속성을 가져옵니다.|
|[COleDispatchDriver::InvokeHelper](#invokehelper)|자동화 메서드를 호출 하기 위한 도우미입니다.|
|[COleDispatchDriver::ReleaseDispatch](#releasedispatch)|릴리스는 `IDispatch` 연결 합니다.|
|[COleDispatchDriver::SetProperty](#setproperty)|자동화 속성을 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[COleDispatchDriver::operator =](#operator_eq)|원본 값을 복사 합니다 `COleDispatchDriver` 개체입니다.|
|[COleDispatchDriver::operator LPDISPATCH](#operator_lpdispatch)|기본 액세스 `IDispatch` 포인터입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[COleDispatchDriver::m_bAutoRelease](#m_bautorelease)|해제할지 여부를 지정 합니다 `IDispatch` 동안 `ReleaseDispatch` 또는 개체 소멸 합니다.|
|[COleDispatchDriver::m_lpDispatch](#m_lpdispatch)|에 대 한 포인터를 나타냅니다 합니다 `IDispatch` 인터페이스는이 연결할 `COleDispatchDriver`합니다.|

## <a name="remarks"></a>설명

`COleDispatchDriver` 기본 클래스는 없습니다.

OLE 디스패치 인터페이스 개체의 메서드 및 속성에 대 한 액세스를 제공합니다. 멤버 함수 `COleDispatchDriver` 연결, 분리, 생성 및 디스패치 연결 형식의 릴리스 `IDispatch`합니다. 다른 멤버 함수 호출을 간소화 하기 위해 가변 인수 목록을 사용할 `IDispatch::Invoke`합니다.

이 클래스를 직접 사용할 수 있지만 주로 클래스 추가 마법사에서 만든 클래스에 의해서만 사용 됩니다. 새로 만들 때 C++ 클래스는 형식 라이브러리를 가져와서 새 클래스에서 파생 됩니다 `COleDispatchDriver`합니다.

사용 하 여 대 한 자세한 내용은 `COleDispatchDriver`, 다음 문서를 참조 하세요.

- [자동화 클라이언트](../../mfc/automation-clients.md)

- [자동화 서버](../../mfc/automation-servers.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`COleDispatchDriver`

## <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

##  <a name="attachdispatch"></a>  COleDispatchDriver::AttachDispatch

`AttachDispatch` 멤버 함수를 호출하여 `IDispatch` 개체에 대한 `COleDispatchDriver` 포인터를 연결합니다. 자세한 내용은 [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)을 참조하십시오.

```
void AttachDispatch(
    LPDISPATCH lpDispatch,
    BOOL bAutoRelease = TRUE);
```

### <a name="parameters"></a>매개 변수

*lpDispatch*<br/>
`IDispatch` 개체에 연결될 OLE `COleDispatchDriver` 개체에 대한 포인터입니다.

*bAutoRelease*<br/>
이 개체가 범위를 벗어날 때 디스패치를 해제할지 여부를 지정합니다.

### <a name="remarks"></a>설명

이 함수는 `IDispatch` 개체에 이미 연결된 모든 `COleDispatchDriver` 포인터를 해제합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#3](../../mfc/codesnippet/cpp/coledispatchdriver-class_1.cpp)]

##  <a name="coledispatchdriver"></a>  COleDispatchDriver::COleDispatchDriver

`COleDispatchDriver` 개체를 생성합니다.

```
COleDispatchDriver();
COleDispatchDriver(LPDISPATCH lpDispatch, BOOL bAutoRelease = TRUE);
COleDispatchDriver(const COleDispatchDriver& dispatchSrc);
```

### <a name="parameters"></a>매개 변수

*lpDispatch*<br/>
`IDispatch` 개체에 연결될 OLE `COleDispatchDriver` 개체에 대한 포인터입니다.

*bAutoRelease*<br/>
이 개체가 범위를 벗어날 때 디스패치를 해제할지 여부를 지정합니다.

*dispatchSrc*<br/>
기존 참조 `COleDispatchDriver` 개체입니다.

### <a name="remarks"></a>설명

폼 `COleDispatchDriver`( `LPDISPATCH lpDispatch`를 **BOOL**`bAutoRelease` = **TRUE**) 연결 된 [IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) 인터페이스입니다.

폼 `COleDispatchDriver`( **const**`COleDispatchDriver`& `dispatchSrc`) 기존 복사 `COleDispatchDriver` 개체 및 참조 횟수를 증가 시킵니다.

폼 `COleDispatchDriver`()를 만듭니다를 `COleDispatchDriver` 개체 있지만 연결 하지는 `IDispatch` 인터페이스입니다. 사용 하기 전에 `COleDispatchDriver`연결 해야 인수 없이 ()는 `IDispatch` 중 하나를 사용 하 여 [coledispatchdriver:: Createdispatch](#createdispatch) 하거나 [COleDispatchDriver::AttachDispatch](#attachdispatch)합니다. 자세한 내용은 [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)을 참조하십시오.

### <a name="example"></a>예제

  [COleDispatchDriver::CreateDispatch](#createdispatch)에 대한 예제를 참조하세요.

##  <a name="createdispatch"></a>  COleDispatchDriver::CreateDispatch

[IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) 인터페이스 개체를 만들고 `COleDispatchDriver` 개체에 연결합니다.

```
BOOL CreateDispatch(
    REFCLSID clsid,
    COleException* pError = NULL);

BOOL CreateDispatch(
    LPCTSTR lpszProgID,
    COleException* pError = NULL);
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
만들려는 `IDispatch` 연결 개체의 클래스 ID입니다.

*pError*<br/>
만들기에서 발생하는 상태 코드를 포함할, OLE 예외 개체에 대한 포인터입니다.

*lpszProgID*<br/>
디스패치 개체를 만들려는 자동화 개체의 프로그래밍 ID(예: "Excel.Document.5")에 대한 포인터입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아닌 값이고, 실패하면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#4](../../mfc/codesnippet/cpp/coledispatchdriver-class_2.cpp)]

##  <a name="detachdispatch"></a>  COleDispatchDriver::DetachDispatch

현재 분리 `IDispatch` 이 개체에서 연결 합니다.

```
LPDISPATCH DetachDispatch();
```

### <a name="return-value"></a>반환 값

이전에 연결 된 OLE에 대 한 포인터 `IDispatch` 개체입니다.

### <a name="remarks"></a>설명

`IDispatch` 해제 되지 않습니다.

LPDISPATCH 유형에 대 한 자세한 내용은 참조 하세요. [IDispatch 인터페이스 구현](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#5](../../mfc/codesnippet/cpp/coledispatchdriver-class_3.cpp)]

##  <a name="getproperty"></a>  COleDispatchDriver::GetProperty

지정 된 개체 속성을 가져옵니다 *dwDispID*합니다.

```
void GetProperty(
    DISPID dwDispID,
    VARTYPE vtProp,
    void* pvProp) const;
```

### <a name="parameters"></a>매개 변수

*dwDispID*<br/>
검색할 속성을 식별 합니다.

*vtProp*<br/>
검색할 속성을 지정 합니다. 가능한 값에 대해서는 [COleDispatchDriver::InvokeHelper](#invokehelper)의 설명 섹션을 참조하세요.

*pvProp*<br/>
속성 값을 받을 변수의 주소입니다. 지정 된 형식과 일치 해야 합니다 *vtProp*합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#6](../../mfc/codesnippet/cpp/coledispatchdriver-class_4.cpp)]

##  <a name="invokehelper"></a>  COleDispatchDriver::InvokeHelper

개체 메서드 또는 속성으로 지정 된 호출 *dwDispID*, 지정 된 컨텍스트에서 *wFlags*합니다.

```
void AFX_CDECL InvokeHelper(
    DISPID dwDispID,
    WORD wFlags,
    VARTYPE vtRet,
    void* pvRet,
    const BYTE* pbParamInfo, ...);
```

### <a name="parameters"></a>매개 변수

*dwDispID*<br/>
호출할 메서드 또는 속성을 식별합니다.

*wFlags*<br/>
에 대 한 호출의 컨텍스트를 설명 하는 플래그 `IDispatch::Invoke`합니다. . 가능한 값 목록을 참조 하세요. 합니다 *wFlags* 에 매개 변수 [idispatch:: Invoke](/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke) Windows SDK의 합니다.

*vtRet*<br/>
반환 값 형식을 지정합니다. 가능한 값은 설명 섹션을 참조하세요.

*pvRet*<br/>
속성 값이나 반환 값을 받을 변수의 주소입니다. 지정 된 형식과 일치 해야 합니다 *vtRet*합니다.

*pbParamInfo*<br/>
다음 매개 변수의 형식을 지정 하는 바이트의 null로 끝나는 문자열에 대 한 포인터 *pbParamInfo*합니다.

*...*<br/>
에 지정 된 형식의 매개 변수 목록을 *pbParamInfo*합니다.

### <a name="remarks"></a>설명

합니다 *pbParamInfo* 매개 변수를 메서드 또는 속성에 전달 된 매개 변수의 형식을 지정 합니다. 인수의 변수 목록은 구문 선언에서 **...** 로 표시됩니다.

가능한 값은 *vtRet* 인수 VARENUM 열거에서 가져옵니다. 다음과 같은 값을 사용할 수 있습니다.

|기호|반환 형식|
|------------|-----------------|
|VT_EMPTY|**void**|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|**CY**|
|VT_DATE|**DATE**|
|VT_BSTR|BSTR|
|VT_DISPATCH|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|**BOOL**|
|VT_VARIANT|**VARIANT**|
|VT_UNKNOWN|LPUNKNOWN|

합니다 *pbParamInfo* 인수는 공백으로 구분 된 목록을 **VTS_** 상수입니다. 공백(쉼표가 아님)으로 구분된 이러한 값 중 하나 이상이 함수의 매개 변수 목록을 지정합니다. 가능한 값은 [EVENT_CUSTOM](event-maps.md#event_custom) 매크로를 통해 나열됩니다.

이 함수 VARIANTARG 값을 매개 변수를 문자열로 변환한 다음 호출을 [idispatch:: Invoke](/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke) 메서드. `Invoke` 호출에 실패하면 이 함수가 예외를 throw합니다. SCODE (상태 코드)에서 반환 하는 경우 `IDispatch::Invoke` DISP_E_EXCEPTION을를이 함수는 [COleException](../../mfc/reference/coleexception-class.md) throw이 고, 그렇지 않으면 개체를 [COleDispatchException](../../mfc/reference/coledispatchexception-class.md).

자세한 내용은 [VARIANTARG](/windows/desktop/api/oaidl/ns-oaidl-tagvariant)를 [IDispatch 인터페이스 구현](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)를 [idispatch:: Invoke](/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke), 및 [COM 오류 코드 구조](/windows/desktop/com/structure-of-com-error-codes) Windows SDK에에서 있습니다.

### <a name="example"></a>예제

  [COleDispatchDriver::CreateDispatch](#createdispatch)에 대한 예제를 참조하세요.

##  <a name="m_bautorelease"></a>  COleDispatchDriver::m_bAutoRelease

True 이면 COM 액세스 한 개체가 [m_lpDispatch](#m_lpdispatch) 자동으로 릴리스될 때 [ReleaseDispatch](#releasedispatch) 가 호출 되거나이 `COleDispatchDriver` 개체는 소멸 됩니다.

```
BOOL m_bAutoRelease;
```

### <a name="remarks"></a>설명

기본적으로 `m_bAutoRelease` 생성자에서 TRUE로 설정 됩니다.

COM 개체 해제에 대 한 자세한 내용은 참조 하세요. [구현 참조 카운팅](/windows/desktop/com/implementing-reference-counting) 하 고 [iunknown:: Release](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) Windows SDK의 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#9](../../mfc/codesnippet/cpp/coledispatchdriver-class_5.cpp)]

##  <a name="m_lpdispatch"></a>  COleDispatchDriver::m_lpDispatch

에 대 한 포인터를 `IDispatch` 인터페이스는이 연결할 `COleDispatchDriver`합니다.

```
LPDISPATCH m_lpDispatch;
```

### <a name="remarks"></a>설명

`m_lpDispatch` 데이터 멤버는 LPDISPATCH 형식의 공용 변수입니다.

자세한 내용은 [IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) Windows SDK에 있습니다.

### <a name="example"></a>예제

  예를 참조 하세요 [COleDispatchDriver::AttachDispatch](#attachdispatch)합니다.

##  <a name="operator_eq"></a>  COleDispatchDriver::operator =

원본 값을 복사 합니다 `COleDispatchDriver` 개체입니다.

```
const COleDispatchDriver& operator=(const COleDispatchDriver& dispatchSrc);
```

### <a name="parameters"></a>매개 변수

*dispatchSrc*<br/>
기존에 대 한 포인터 `COleDispatchDriver` 개체입니다.

##  <a name="operator_lpdispatch"></a>  COleDispatchDriver::operator LPDISPATCH

기본 액세스 `IDispatch` 의 포인터는 `COleDispatchDriver` 개체입니다.

```
operator LPDISPATCH();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#8](../../mfc/codesnippet/cpp/coledispatchdriver-class_6.cpp)]

##  <a name="releasedispatch"></a>  COleDispatchDriver::ReleaseDispatch

릴리스는 `IDispatch` 연결 합니다. 자세한 내용은 참조 하세요. [IDispatch 인터페이스 구현](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)

```
void ReleaseDispatch();
```

### <a name="remarks"></a>설명

이 함수를 호출 하는이 연결에 대 한 자동 릴리스를 설정한 경우 `IDispatch::Release` 인터페이스를 해제 하기 전에 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [COleDispatchDriver::AttachDispatch](#attachdispatch)합니다.

##  <a name="setproperty"></a>  COleDispatchDriver::SetProperty

지정 된 OLE 개체 속성을 설정 *dwDispID*합니다.

```
void AFX_CDECL SetProperty(
    DISPID dwDispID,
    VARTYPE vtProp, ...);
```

### <a name="parameters"></a>매개 변수

*dwDispID*<br/>
설정할 속성을 확인합니다.

*vtProp*<br/>
설정할 속성의 유형을 지정합니다. 가능한 값에 대해서는 [COleDispatchDriver::InvokeHelper](#invokehelper)의 설명 섹션을 참조하세요.

*...*<br/>
지정 된 형식의 단일 매개 변수 *vtProp*합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#7](../../mfc/codesnippet/cpp/coledispatchdriver-class_7.cpp)]

## <a name="see-also"></a>참고자료

[CALCDRIV MFC 샘플](../../overview/visual-cpp-samples.md)<br/>
[ACDUAL MFC 샘플](../../overview/visual-cpp-samples.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)
