---
title: 레지스트리 및 TypeLib 전역 함수
ms.date: 03/27/2019
f1_keywords:
- atlbase/ATL::AtlGetPerUserRegistration
- afxpriv/ATL::AfxRegCreateKey
- afxpriv/ATL::AfxRegDeleteKey
- atlbase/ATL::AtlRegisterTypeLib
- afxpriv/ATL::AfxRegOpenKey
- afxpriv/ATL::AfxRegOpenKeyEx
- afxdisp/ATL::AfxUnregisterPreviewHandler
- atlbase/ATL::AtlSetPerUserRegistration
- atlbase/ATL::AtlUnRegisterTypeLib
- atlbase/ATL::AtlLoadTypeLib
- atlbase/ATL::AtlUpdateRegistryFromResourceD
- atlbase/ATL::RegistryDataExchange
helpviewer_keywords:
- RegistryDataExchange function, global functions
ms.assetid: d58b8a4e-975c-4417-8b34-d3c847f679b3
ms.openlocfilehash: c5fdaceb47b6cd09dd9d66f26af1337a8dc6bbae
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58566015"
---
# <a name="registry-and-typelib-global-functions"></a>레지스트리 및 TypeLib 전역 함수

이러한 함수를 사용 하면 로드 하 고 형식 라이브러리를 등록에 대 한 지원.

> [!IMPORTANT]
>  다음 표에 나열 된 함수를 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

|||
|-|-|
|[AfxRegCreateKey](#afxregcreatekey)|지정된 된 레지스트리 키를 만듭니다.|
|[AfxRegDeleteKey](#afxregdeletekey)|지정된 된 레지스트리 키를 삭제합니다.|
|[AfxRegisterPreviewHandler](#afxregisterpreviewhandler)|미리 보기 처리기를 등록 하는 도우미입니다.|
|[AfxUnregisterPreviewHandler](#afxunregisterpreviewhandler)| 미리 보기 처리기의 등록을 취소 하는 도우미입니다. |
|[AtlRegisterTypeLib](#atlregistertypelib)|이 함수는 형식 라이브러리를 등록하기 위해 호출됩니다.|
|[AtlUnRegisterTypeLib](#atlunregistertypelib)|이 함수가 호출 되어 형식 라이브러리의 등록을 취소 합니다.|
|[AfxRegOpenKey](#afxregopenkey)|지정 된 레지스트리 키를 엽니다.|
|[AfxRegOpenKeyEx](#afxregopenkeyex)|지정 된 레지스트리 키를 엽니다.|
|[AtlLoadTypeLib](#atlloadtypelib)|이 함수는 형식 라이브러리를 로드하기 위해 호출됩니다.|
|[AtlUpdateRegistryFromResourceD](#atlupdateregistryfromresourced)|이 함수는 제공된 리소스에서 레지스트리를 업데이트하기 위해 호출됩니다.|
|[RegistryDataExchange](#registrydataexchange)|이 함수는 시스템 레지스트리에서 읽거나 쓰기 위해 호출됩니다. 에 의해 호출 된 [레지스트리 데이터 교환 매크로](../../atl/reference/registry-data-exchange-macros.md)합니다.|

이러한 함수는 프로그램 사용 정보를 저장 하 여 레지스트리에서 노드를 제어 합니다.

|||
|-|-|
|[AtlGetPerUserRegistration](#atlgetperuserregistration)|응용 프로그램에 대 한 레지스트리 액세스 리디렉션합니다 있는지 여부를 검색 합니다 **HKEY_CURRENT_USER** ( **HKCU**) 노드.|
|[AtlSetPerUserRegistration](#atlsetperuserregistration)|응용 프로그램에 대 한 레지스트리 액세스 리디렉션합니다 있는지 여부를 설정 합니다 **HKEY_CURRENT_USER** ( **HKCU**) 노드.|

### <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="atlgetperuserregistration"></a> AtlGetPerUserRegistration

이 함수를 사용 하 여 응용 프로그램에 대 한 레지스트리 액세스 리디렉션합니다 여부를 결정 하는 **HKEY_CURRENT_USER** (**HKCU**) 노드.

### <a name="syntax"></a>구문

```
ATLINLINE ATLAPI AtlGetPerUserRegistration(bool* pEnabled);
```

### <a name="parameters"></a>매개 변수

*pEnabled*<br/>
[out] TRUE 이면 레지스트리 정보를 이동 합니다 **HKCU** 노드 False로 기본 노드에 레지스트리 정보를 기록 하는 응용 프로그램을 나타냅니다. 기본 노드인 **HKEY_CLASSES_ROOT** (**HKCR**).

### <a name="return-value"></a>반환 값

S_OK는 메서드가 성공적 이면, 그렇지 않으면 HRESULT 오류 코드는 오류가 발생 한 경우.

### <a name="remarks"></a>설명

레지스트리 리디렉션 기본적으로 사용 되지 않습니다. 이 옵션을 사용 하는 경우 레지스트리 액세스도 리디렉션되는지 **HKEY_CURRENT_USER\Software\Classes**합니다.

리디렉션 전역 아닙니다. 이 레지스트리 리디렉션은 MFC 및 ATL 프레임 영향을 받습니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="afxregcreatekey"></a> AfxRegCreateKey

지정된 된 레지스트리 키를 만듭니다.

### <a name="syntax"></a>구문

```
LONG AFXAPI AfxRegCreateKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>매개 변수

*hKey*<br/>
열고 레지스트리 키에 대 한 핸들입니다.

*lpSubKey*<br/>
이 함수를 열거나 만듭니다는 키의 이름입니다.

*phkResult*<br/>
열린 만들거나 키에 대 한 핸들을 수신 하는 변수에 대 한 포인터입니다.

*pTM*<br/>
`CAtlTransactionManager` 개체에 대한 포인터입니다.

### <a name="return-value"></a>반환 값

함수가 성공할 경우 반환 값은 ERROR_SUCCESS입니다. 함수가 실패 한 경우 반환 값은 winerror에 정의 된 0이 아닌 오류 코드입니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxpriv.h

## <a name="afxregdeletekey"></a> AfxRegDeleteKey

지정된 된 레지스트리 키를 삭제합니다.

### <a name="syntax"></a>구문

```
LONG AFXAPI AfxRegDeleteKey(HKEY hKey, LPCTSTR lpSubKey, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>매개 변수

*hKey*<br/>
열고 레지스트리 키에 대 한 핸들입니다.

*lpSubKey*<br/>
삭제할 키의 이름입니다.

*pTM*<br/>
`CAtlTransactionManager` 개체에 대한 포인터입니다.

### <a name="return-value"></a>반환 값

함수가 성공할 경우 반환 값은 ERROR_SUCCESS입니다. 함수가 실패 한 경우 반환 값은 winerror에 정의 된 0이 아닌 오류 코드입니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxpriv.h

## <a name="afxregisterpreviewhandler"></a>

미리 보기 처리기를 등록 하는 도우미입니다.

### <a name="syntax"></a>구문

```
BOOL AFXAPI AfxRegisterPreviewHandler(LPCTSTR lpszCLSID, LPCTSTR lpszShortTypeName, LPCTSTR lpszFilterExt);
```

### <a name="parameters"></a>매개 변수

*lpszCLSID*<br/>
처리기의 CLSID를 지정합니다.

*lpszShortTypeName*<br/>
처리기의 ProgID를 지정합니다.

*lpszFilterExt*<br/>
이 처리기를 사용 하 여 등록 된 파일 확장명을 지정 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

##  <a name="atlregistertypelib"></a>  AtlRegisterTypeLib

이 함수는 형식 라이브러리를 등록하기 위해 호출됩니다.

```
ATLAPI AtlRegisterTypeLib(HINSTANCE hInstTypeLib, LPCOLESTR lpszIndex);
```

### <a name="parameters"></a>매개 변수

*hInstTypeLib*<br/>
모듈 인스턴스에 대 한 핸들입니다.

*lpszIndex*<br/>
형식에서 문자열 "\\\N", 여기서 N은 정수 인덱스 형식 라이브러리 리소스입니다. 인덱스가 필요 없는 경우 NULL 일 수 있습니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

이 도우미 함수를 사용 하 여 [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver) 하 고 [CAtlComModule::RegisterTypeLib](../../atl/reference/catlcommodule-class.md#registertypelib)합니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="afxregopenkey"></a> AfxRegOpenKey

지정 된 레지스트리 키를 엽니다.

### <a name="syntax"></a>구문

```
LONG AFXAPI AfxRegOpenKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>매개 변수

*hKey*<br/>
열고 레지스트리 키에 대 한 핸들입니다.

*lpSubKey*<br/>
이 함수를 열거나 만듭니다는 키의 이름입니다.

*phkResult*<br/>
만든된 키에 대 한 핸들을 수신 하는 변수에 대 한 포인터입니다.

*pTM*<br/>
`CAtlTransactionManager` 개체에 대한 포인터입니다.

### <a name="return-value"></a>반환 값

함수가 성공할 경우 반환 값은 ERROR_SUCCESS입니다. 함수가 실패 한 경우 반환 값은 winerror에 정의 된 0이 아닌 오류 코드입니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxpriv.h

## <a name="afxregopenkeyex"></a>  AfxRegOpenKeyEx

지정 된 레지스트리 키를 엽니다.

### <a name="syntax"></a>구문

```
LONG AFXAPI AfxRegOpenKeyEx(HKEY hKey, LPCTSTR lpSubKey, DWORD ulOptions, REGSAM samDesired, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>매개 변수

*hKey*<br/>
열고 레지스트리 키에 대 한 핸들입니다.

*lpSubKey*<br/>
이 함수를 열거나 만듭니다는 키의 이름입니다.

*ulOptions*<br/>
이 매개 변수는 예약 되며 0 이어야 합니다.

*samDesired*<br/>
키에 원하는 액세스 권한을 지정 하는 마스크입니다.

*phkResult*<br/>
열린된 키에 대 한 핸들을 수신 하는 변수에 대 한 포인터입니다.

*pTM*<br/>
`CAtlTransactionManager` 개체에 대한 포인터입니다.

### <a name="return-value"></a>반환 값

함수가 성공할 경우 반환 값은 ERROR_SUCCESS입니다. 함수가 실패 한 경우 반환 값은 winerror에 정의 된 0이 아닌 오류 코드입니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxpriv.h

## <a name="afxunregisterpreviewhandler"></a> AfxUnregisterPreviewHandler

미리 보기 처리기의 등록을 취소 하는 도우미입니다.

### <a name="syntax"></a>구문

```
BOOL AFXAPI AfxUnRegisterPreviewHandler(LPCTSTR lpszCLSID);
```

### <a name="parameters"></a>매개 변수

*lpszCLSID*<br/>
등록 취소할 처리기의 CLSID를 지정 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="atlsetperuserregistration"></a> AtlSetPerUserRegistration

응용 프로그램에 대 한 레지스트리 액세스 리디렉션합니다 있는지 여부를 설정 합니다 **HKEY_CURRENT_USER** (**HKCU**) 노드.

### <a name="syntax"></a>구문

```
ATLINLINE ATLAPI AtlSetPerUserRegistration(bool bEnable);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
[in] TRUE 이면 레지스트리 정보를 이동 합니다 **HKCU** 노드 False로 기본 노드에 레지스트리 정보를 기록 하는 응용 프로그램을 나타냅니다. 기본 노드인 **HKEY_CLASSES_ROOT** (**HKCR**).

### <a name="return-value"></a>반환 값

S_OK는 메서드가 성공적 이면, 그렇지 않으면 HRESULT 오류 코드는 오류가 발생 한 경우.

### <a name="remarks"></a>설명

레지스트리 리디렉션 기본적으로 사용 되지 않습니다. 이 옵션을 사용 하는 경우 레지스트리 액세스도 리디렉션되는지 **HKEY_CURRENT_USER\Software\Classes**합니다.

리디렉션 전역 아닙니다. 이 레지스트리 리디렉션은 MFC 및 ATL 프레임 영향을 받습니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

##  <a name="atlunregistertypelib"></a>  AtlUnRegisterTypeLib

이 함수는 형식 라이브러리를 등록 취소하기 위해 호출됩니다.

### <a name="syntax"></a>구문

```
ATLAPI AtlUnRegisterTypeLib(
    HINSTANCE hInstTypeLib,
    LPCOLESTR lpszIndex);
```

### <a name="parameters"></a>매개 변수

*hInstTypeLib*<br/>
모듈 인스턴스에 대 한 핸들입니다.

*lpszIndex*<br/>
형식에서 문자열 "\\\N", 여기서 N은 정수 인덱스 형식 라이브러리 리소스입니다. 인덱스가 필요 없는 경우 NULL 일 수 있습니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

이 도우미 함수를 사용 하 여 [CAtlComModule::UnRegisterTypeLib](../../atl/reference/catlcommodule-class.md#unregistertypelib) 하 고 [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver)합니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

##  <a name="atlloadtypelib"></a>  AtlLoadTypeLib

이 함수는 형식 라이브러리를 로드하기 위해 호출됩니다.

### <a name="syntax"></a>구문

```
ATLINLINE ATLAPI AtlLoadTypeLib(
    HINSTANCE hInstTypeLib,
    LPCOLESTR lpszIndex,
    BSTR* pbstrPath,
    ITypeLib** ppTypeLib);
```

### <a name="parameters"></a>매개 변수

*hInstTypeLib*<br/>
형식 라이브러리와 연결 된 모듈에 대 한 핸들입니다.

*lpszIndex*<br/>
형식에서 문자열 "\\\N", 여기서 N은 정수 인덱스 형식 라이브러리 리소스입니다. 인덱스가 필요 없는 경우 NULL 일 수 있습니다.

*pbstrPath*<br/>
반환이 성공적 이면 형식 라이브러리와 연결 된 모듈의 전체 경로 포함 합니다.

*ppTypeLib*<br/>
반환이 성공적 이면 로드 된 형식 라이브러리에 대 한 포인터에 대 한 포인터를 포함합니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

이 도우미 함수를 사용 하 여 [AtlRegisterTypeLib](#atlregistertypelib) 하 고 [AtlUnRegisterTypeLib](#atlunregistertypelib)합니다.

##  <a name="atlupdateregistryfromresourced"></a>  AtlUpdateRegistryFromResourceD

이 함수는 Visual Studio 2013에서 사용이 중단되었으며, Visual Studio 2015에서 제거되었습니다.

```
<removed>
```

##  <a name="registrydataexchange"></a>  RegistryDataExchange

이 함수는 시스템 레지스트리에서 읽거나 쓰기 위해 호출됩니다.

### <a name="syntax"></a>구문

```
HRESULT RegistryDataExchange(
    T* pT,
    enum RDXOperations rdxOp,
    void* pItem = NULL);
```

### <a name="parameters"></a>매개 변수

*pT*<br/>
현재 개체에 대 한 포인터입니다.

*rdxOp*<br/>
작업을 나타내는 열거형 값을 함수를 수행 해야 합니다. 허용 되는 값에 대 한 설명 섹션의 표를 참조 합니다.

*pItem*<br/>
데이터를 읽거나 레지스트리를 작성 하는 것에 대 한 포인터입니다. 데이터를 레지스트리에서 삭제할 키를 나타낼 수도 있습니다. 기본값은 NULL입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

매크로 [BEGIN_RDX_MAP](registry-data-exchange-macros.md#begin_rdx_map) 하 고 [END_RDX_MAP](registry-data-exchange-macros.md#end_rdx_map) 호출 하는 함수를 확장 하 고 `RegistryDataExchange`입니다.

함수 작업을 수행할지 여부를 나타내는 열거 가능한 값은 아래에 나와 있습니다.

|열거형 값|작업|
|----------------|---------------|
|eReadFromReg|레지스트리에서 데이터를 읽습니다.|
|eWriteToReg|레지스트리 데이터를 씁니다.|
|eDeleteFromReg|레지스트리에서 키를 삭제 합니다.|

### <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="see-also"></a>참고자료

[함수](atl-functions.md)<br/>
[레지스트리 데이터 교환 매크로](registry-data-exchange-macros.md)
