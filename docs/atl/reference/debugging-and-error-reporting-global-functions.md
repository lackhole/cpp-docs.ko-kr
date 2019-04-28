---
title: 디버깅 및 오류 보고 전역 함수
ms.date: 11/04/2016
f1_keywords:
- atlcomcli/ATL::AtlHresultFromLastError
- atlcom/ATL::AtlReportError
- atldef/ATL::AtlThrow
helpviewer_keywords:
- functions [ATL], error reporting
ms.assetid: 11339c02-98cd-428d-b3b9-7deeb155a6a3
ms.openlocfilehash: f7483b7473383958089b0c88d0b3c2645ddc2a4f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62276668"
---
# <a name="debugging-and-error-reporting-global-functions"></a>디버깅 및 오류 보고 전역 함수

이러한 함수는 유용한 디버깅 및 추적 기능을 제공합니다.

|||
|-|-|
|[AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror)|반환 된 `GetLastError` 형식의 HRESULT 오류 코드입니다.|
|[AtlHresultFromWin32](debugging-and-error-reporting-global-functions.md#atlhresultfromwin32)|Win32 오류 코드 HRESULT로 변환합니다.|
|[AtlReportError](debugging-and-error-reporting-global-functions.md#atlreporterror)|설정 `IErrorInfo` 클라이언트에 오류 세부 정보를 제공 합니다.|
|[AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)|`CAtlException`를 throw합니다.|
|[AtlThrowLastWin32](debugging-and-error-reporting-global-functions.md#atlthrowlastwin32)|Windows 함수 `GetLastError`의 결과에 따라 오류를 표시하려면 이 함수를 호출합니다.|

##  <a name="atlhresultfromlasterror"></a>  AtlHresultFromLastError

호출 스레드의 마지막 오류 코드 값을 HRESULT 형식으로 반환합니다.

```
HRESULT AtlHresultFromLastError();
```

### <a name="remarks"></a>설명

`AtlHresultFromLastError` 호출 `GetLastError` 마지막 오류를 가져오려면 HRESULT_FROM_WIN32 매크로 사용 하는 HRESULT를 변환한 후 오류를 반환 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlcomcli.h

##  <a name="atlhresultfromwin32"></a>  AtlHresultFromWin32

Win32 오류 코드 HRESULT로 변환합니다.

```
AtlHresultFromWin32(DWORD error);
```

### <a name="parameters"></a>매개 변수

*error*<br/>
변환 오류 값입니다.

### <a name="remarks"></a>설명

Win32 오류 코드 HRESULT HRESULT_FROM_WIN32 매크로 사용 하 여 변환 합니다.

> [!NOTE]
>  사용 하는 대신 `HRESULT_FROM_WIN32(GetLastError())`에서 함수를 사용 하 여 [AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror)합니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlcomcli.h

##  <a name="atlreporterror"></a>  AtlReportError

설정 된 `IErrorInfo` 개체의 클라이언트에 오류 정보를 제공 하는 인터페이스입니다.

```
HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCOLESTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCOLESTR lpszDesc,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCSTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCSTR lpszDesc,
    DWORD dwHelpID,
    LPCSTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    UINT nID,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    UINT nID,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
[in] 오류를 보고 하는 개체의 CLSID입니다.

*lpszDesc*<br/>
[in] 오류를 설명 하는 문자열입니다. 유니코드 버전 지정 *lpszDesc* 입니다 LPCOLESTR 입력; ANSI 버전 LPCSTR 형식을 지정 합니다.

*iid*<br/>
[in] 오류는 운영 체제에 의해 정의 된 경우 오류 또는 GUID_NULL를 정의 하는 인터페이스의 IID입니다.

*hRes*<br/>
[in] 원하는 HRESULT 호출자에 게 반환 합니다.

*nID*<br/>
[in] 오류 설명 문자열을 저장 된 리소스 식별자입니다. 이 값 사이 있어야 0x0200 및 0xFFFF 까지입니다. 디버그 빌드에서 **ASSERT** 경우에 발생 합니다 *nID* 는 유효한 문자열을 인덱싱하지 않습니다. 릴리스 빌드에서 오류 설명 문자열을 "알 수 없는 오류입니다."로 설정 됩니다.

*dwHelpID*<br/>
[in] 오류에 대 한 도움말 컨텍스트 식별자입니다.

*lpszHelpFile*<br/>
[in] 경로 오류를 설명 하는 도움말 파일의 이름입니다.

*hInst*<br/>
[in] 리소스에 대 한 핸들입니다. 이 매개 변수는 기본적으로 `__AtlBaseModuleModule::GetResourceInstance`, 여기서 `__AtlBaseModuleModule` 의 인스턴스인 전역 [CAtlBaseModule](../../atl/reference/catlbasemodule-class.md) 클래스에서 파생 된 또는 합니다.

### <a name="return-value"></a>반환 값

경우는 *hRes* 매개 변수는 0이 아닌의 값을 반환 *hRes*합니다. 하는 경우 *hRes* 이 0 이면의 처음 4 개 버전 `AtlReportError` DISP_E_EXCEPTION을 반환 합니다. 매크로의 결과 반환 하는 마지막 두 버전 **MAKE_HRESULT (1, FACILITY_ITF** `nID` **)** 합니다.

### <a name="remarks"></a>설명

문자열 *lpszDesc* 오류의 텍스트 설명으로 사용 됩니다. 받으면 클라이언트는 *hRes* 에서 반환 `AtlReportError`, 액세스할 수는 `IErrorInfo` 오류에 대 한 세부 정보에 대 한 구조입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#52](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_1.cpp)]

> [!CAUTION]
>  사용 하지 마세요 `AtlReportError` 에서 C++ 처리기를 catch 합니다. 이러한 함수의 재정의 중 일부 사용 하 여 ATL 문자열 변환 매크로 내부적으로 사용 된 `_alloca` 내부적으로 작동 합니다. 사용 하 여 `AtlReportError` 에 C++ catch 처리기에서 예외를 일으킬 수 있습니다 C++ catch 처리기입니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="atlthrow"></a>  AtlThrow

HRESULT 상태 코드를 기반으로 오류를 표시 하려면이 함수를 호출 합니다.

```
__declspec(noreturn) inline void AtlThrow(HRESULT hr);
```

### <a name="parameters"></a>매개 변수

*hr*<br/>
표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 함수는 오류 조건이 발생할 경우 ATL 및 MFC 코드에서 사용 됩니다. 사용자 고유의 코드에서 호출할 수도 있습니다. 이 함수를 기본 구현에 따라 달라 집니다 기호 _ATL_NO_EXCEPTIONS의 정의 된 형식의 프로젝트, MFC 또는 ATL.

모든 경우에이 함수는 HRESULT 디버거를 추적합니다.

Visual Studio 2015 업데이트 3 이상 버전에서는이 함수는 잘못 된 SAL 경고가 표시 되지 않도록 하는 __declspec (noreturn 특성 사용된).

이 함수가 throw _ATL_NO_EXCEPTIONS MFC 프로젝트에서를 정의 하지 않은 경우는 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException](../../mfc/reference/coleexception-class.md) HRESULT의 값을 기반으로 합니다.

함수가 throw _ATL_NO_EXCEPTIONS ATL 프로젝트에 정의 되어 있지 않으면, 한 [CAtlException](../../atl/reference/catlexception-class.md)합니다.

_ATL_NO_EXCEPTIONS 정의 된 경우 함수는 예외를 throw 하는 대신 어설션 실패가 발생 합니다.

ATL 프로젝트에 대 한 오류 발생 시 ATL에서 사용할이 함수의 자체 구현을 제공할 수 됩니다. 이렇게 하려면 동일한 시그니처를 사용 하 여 사용자 고유의 함수를 정의할 `AtlThrow` 및 #define `AtlThrow` 함수의 이름 이어야 합니다. (즉, 수행 atlbase.h atlexcept.h 포함 하므로 ATL 헤더를 포함 하기 전에 해야 함을) atlexcept.h 포함 하기 전에 수행 해야 합니다. 함수 특성 `__declspec(noreturn)` 에 잘못 된 SAL 경고가 표시 되지 않도록 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#95](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_2.h)]

## <a name="requirements"></a>요구 사항

**헤더:** atldef.h

##  <a name="atlthrowlastwin32"></a>  AtlThrowLastWin32

Windows 함수 `GetLastError`의 결과에 따라 오류를 표시하려면 이 함수를 호출합니다.

```
inline void AtlThrowLastWin32();
```

### <a name="remarks"></a>설명

이 함수는 결과 추적 `GetLastError` 디버거에 합니다.

이 함수가 throw _ATL_NO_EXCEPTIONS MFC 프로젝트에서를 정의 하지 않은 경우는 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException](../../mfc/reference/coleexception-class.md) 반환한 값을 기반으로 `GetLastError`입니다.

함수가 throw _ATL_NO_EXCEPTIONS ATL 프로젝트에 정의 되어 있지 않으면, 한 [CAtlException](../../atl/reference/catlexception-class.md)합니다.

_ATL_NO_EXCEPTIONS 정의 된 경우 함수는 예외를 throw 하는 대신 어설션 실패가 발생 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldef.h

## <a name="see-also"></a>참고자료

[함수](../../atl/reference/atl-functions.md)<br/>
[디버깅 및 오류 보고 매크로](../../atl/reference/debugging-and-error-reporting-macros.md)
