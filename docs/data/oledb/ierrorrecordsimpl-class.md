---
title: IErrorRecordsImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- ATL::IErrorRecordsImpl
- ATL.IErrorRecordsImpl
- IErrorRecordsImpl
- GetErrorDescriptionString
- IErrorRecordsImpl.GetErrorDescriptionString
- IErrorRecordsImpl::GetErrorDescriptionString
- GetErrorGUID
- IErrorRecordsImpl.GetErrorGUID
- IErrorRecordsImpl::GetErrorGUID
- GetErrorHelpContext
- IErrorRecordsImpl::GetErrorHelpContext
- IErrorRecordsImpl.GetErrorHelpContext
- IErrorRecordsImpl::GetErrorHelpFile
- GetErrorHelpFile
- IErrorRecordsImpl.GetErrorHelpFile
- IErrorRecordsImpl.GetErrorSource
- GetErrorSource
- IErrorRecordsImpl::GetErrorSource
- IErrorRecordsImpl.AddErrorRecord
- AddErrorRecord
- IErrorRecordsImpl::AddErrorRecord
- ATL::IErrorRecordsImpl::GetBasicErrorInfo
- IErrorRecordsImpl::GetBasicErrorInfo
- GetBasicErrorInfo
- ATL.IErrorRecordsImpl.GetBasicErrorInfo
- IErrorRecordsImpl.GetBasicErrorInfo
- ATL::IErrorRecordsImpl::GetCustomErrorObject
- IErrorRecordsImpl::GetCustomErrorObject
- ATL.IErrorRecordsImpl.GetCustomErrorObject
- IErrorRecordsImpl.GetCustomErrorObject
- GetCustomErrorObject
- GetErrorInfo
- IErrorRecordsImpl.GetErrorInfo
- IErrorRecordsImpl::GetErrorInfo
- IErrorRecordsImpl::GetErrorParameters
- ATL.IErrorRecordsImpl.GetErrorParameters
- IErrorRecordsImpl.GetErrorParameters
- GetErrorParameters
- ATL::IErrorRecordsImpl::GetErrorParameters
- IErrorRecordsImpl::GetRecordCount
- ATL::IErrorRecordsImpl::GetRecordCount
- IErrorRecordsImpl.GetRecordCount
- ATL.IErrorRecordsImpl.GetRecordCount
- IErrorRecordsImpl::m_rgErrors
- IErrorRecordsImpl.m_rgErrors
- ATL.IErrorRecordsImpl.m_rgErrors
- m_rgErrors
- ATL::IErrorRecordsImpl::m_rgErrors
helpviewer_keywords:
- IErrorRecordsImpl class
- GetErrorDescriptionString method
- GetErrorGUID method
- GetErrorHelpContext method
- GetErrorHelpFile method
- GetErrorSource method
- AddErrorRecord method
- GetBasicErrorInfo method
- GetCustomErrorObject method
- GetErrorInfo method
- GetErrorParameters method
- GetRecordCount method
- m_rgErrors
ms.assetid: dea8e938-c5d8-45ab-86de-eb8fbf534ffb
ms.openlocfilehash: b1ab6b0984cbf84690d69a3ffe7eb3931bf59563
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59029475"
---
# <a name="ierrorrecordsimpl-class"></a>IErrorRecordsImpl 클래스

OLE DB 구현 [IErrorRecords](/previous-versions/windows/desktop/ms718112(v=vs.85)) 레코드를 추가 하 고 데이터 멤버에서 레코드를 검색 하는 인터페이스를 ([m_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)) 형식의 **CAtlArray <** `RecordClass`**>**.

## <a name="syntax"></a>구문

```cpp
template <class T, class RecordClass = ATLERRORINFO>
class IErrorRecordsImpl : public IErrorRecords
```

### <a name="parameters"></a>매개 변수

*T*<br/>
파생 된 클래스 `IErrorRecordsImpl`합니다.

*RecordClass*<br/>
OLE DB 오류 개체를 나타내는 클래스입니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldb.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[GetErrorDescriptionString](#geterrordescriptionstring)|오류 레코드에서 오류 설명 문자열을 가져옵니다.|
|[GetErrorGUID](#geterrorguid)|오류 레코드에서 오류를 GUID를 가져옵니다.|
|[GetErrorHelpContext](#geterrorhelpcontext)|오류 레코드에서 도움말 컨텍스트 ID를 가져옵니다.|
|[GetErrorHelpFile](#geterrorhelpfile)|오류 레코드에서 도움말 파일의 전체 경로 이름을 가져옵니다.|
|[GetErrorSource](#geterrorsource)|오류 레코드에서 오류 소스 코드를 가져옵니다.|

### <a name="interface-methods"></a>인터페이스 메서드

|||
|-|-|
|[AddErrorRecord](#adderrorrecord)|OLE DB 오류 개체에 레코드를 추가합니다.|
|[GetBasicErrorInfo](#getbasicerrorinfo)|반환 코드 및 공급자 특정 오류 번호와 같은 오류에 대 한 기본 정보를 반환 합니다.|
|[GetCustomErrorObject](#getcustomerrorobject)|인터페이스를 사용자 지정 오류 개체에 대 한 포인터를 반환합니다.|
|[GetErrorInfo](#geterrorinfo)|반환 된 [IErrorInfo](/previous-versions/windows/desktop/ms718112(v=vs.85)) 지정된 된 레코드에 대 한 인터페이스 포인터입니다.|
|[GetErrorParameters](#geterrorparameters)|오류 매개 변수를 반환합니다.|
|[GetRecordCount](#getrecordcount)|OLE DB 레코드 개체의 레코드 수를 반환 합니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|[m_rgErrors](#rgerrors)|오류 레코드의 배열입니다.|

## <a name="geterrordescriptionstring"></a> IErrorRecordsImpl::GetErrorDescriptionString

오류 레코드에서 오류 설명 문자열을 가져옵니다.

### <a name="syntax"></a>구문

```cpp
LPOLESTR GetErrorDescriptionString(ERRORINFO& rCurError);
```

#### <a name="parameters"></a>매개 변수

*rCurError*<br/>
`ERRORINFO` 레코드는 `IErrorInfo` 인터페이스입니다.

### <a name="return-value"></a>반환 값

오류를 설명 하는 문자열에 대 한 포인터입니다.

## <a name="geterrorguid"></a> IErrorRecordsImpl::GetErrorGUID

오류 레코드에서 오류를 GUID를 가져옵니다.

### <a name="syntax"></a>구문

```cpp
REFGUID GetErrorGUID(ERRORINFO& rCurError);
```

#### <a name="parameters"></a>매개 변수

*rCurError*<br/>
`ERRORINFO` 레코드는 `IErrorInfo` 인터페이스입니다.

### <a name="return-value"></a>반환 값

오류에 대 한 GUID에 대 한 참조입니다.

## <a name="geterrorhelpcontext"></a> IErrorRecordsImpl::GetErrorHelpContext

오류 레코드에서 도움말 컨텍스트 ID를 가져옵니다.

### <a name="syntax"></a>구문

```cpp
DWORD GetErrorHelpContext(ERRORINFO& rCurError);
```

#### <a name="parameters"></a>매개 변수

*rCurError*<br/>
`ERRORINFO` 레코드는 `IErrorInfo` 인터페이스입니다.

### <a name="return-value"></a>반환 값

오류에 대 한 도움말 컨텍스트 ID입니다.

## <a name="geterrorhelpfile"></a> IErrorRecordsImpl::GetErrorHelpFile

오류 레코드에서 도움말 파일의 경로 이름을 가져옵니다.

### <a name="syntax"></a>구문

```cpp
LPOLESTR GetErrorHelpFile(ERRORINFO& rCurError);
```

#### <a name="parameters"></a>매개 변수

*rCurError*<br/>
`ERRORINFO` 레코드는 `IErrorInfo` 인터페이스입니다.

### <a name="return-value"></a>반환 값

오류에 대 한 도움말 파일의 경로 이름을 포함 하는 문자열에 대 한 포인터입니다.

## <a name="geterrorsource"></a> IErrorRecordsImpl::GetErrorSource

오류 레코드에서 오류를 발생 시킨 소스 코드를 가져옵니다.

### <a name="syntax"></a>구문

```cpp
LPOLESTR GetErrorSource(ERRORINFO& rCurError);
```

#### <a name="parameters"></a>매개 변수

*rCurError*<br/>
`ERRORINFO` 레코드는 `IErrorInfo` 인터페이스입니다.

### <a name="return-value"></a>반환 값

오류에 대 한 소스 코드를 포함 하는 문자열에 대 한 포인터입니다.

## <a name="adderrorrecord"></a> IErrorRecordsImpl::AddErrorRecord

OLE DB 오류 개체에 레코드를 추가합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(AddErrorRecord )(ERRORINFO *pErrorInfo,
   DWORD dwLookupID,
   DISPPARAMS *pdispparams,
   IUnknown *punkCustomError,
   DWORD dwDynamicErrorID);
```

#### <a name="parameters"></a>매개 변수

참조 [IErrorRecords::AddErrorRecord](/previous-versions/windows/desktop/ms725362(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="getbasicerrorinfo"></a> IErrorRecordsImpl::GetBasicErrorInfo

반환 코드 및 공급자 특정 오류 번호와 같은 오류에 대 한 기본 정보를 반환 합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(GetBasicErrorInfo )(ULONG ulRecordNum,
   ERRORINFO *pErrorInfo);
```

#### <a name="parameters"></a>매개 변수

참조 [IErrorRecords::GetBasicErrorInfo](/previous-versions/windows/desktop/ms723907(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="getcustomerrorobject"></a> IErrorRecordsImpl::GetCustomErrorObject

인터페이스를 사용자 지정 오류 개체에 대 한 포인터를 반환합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(GetCustomErrorObject )(ULONG ulRecordNum,
   REFIID riid,
   IUnknown **ppObject);
```

#### <a name="parameters"></a>매개 변수

참조 [IErrorRecords::GetCustomErrorObject](/previous-versions/windows/desktop/ms725417(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="geterrorinfo"></a> IErrorRecordsImpl::GetErrorInfo

반환 된 [IErrorInfo](/previous-versions/windows/desktop/ms718112(v=vs.85)) 지정된 된 레코드에 대 한 인터페이스 포인터입니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(GetErrorInfo )(ULONG ulRecordNum,
   LCID lcid,
   IErrorInfo **ppErrorInfo);
```

#### <a name="parameters"></a>매개 변수

참조 [IErrorRecords::GetErrorInfo](/previous-versions/windows/desktop/ms711230(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="geterrorparameters"></a> IErrorRecordsImpl::GetErrorParameters

오류 매개 변수를 반환합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(GetErrorParameters )(ULONG ulRecordNum,
   DISPPARAMS *pdispparams);
```

#### <a name="parameters"></a>매개 변수

참조 [IErrorRecords::GetErrorParameters](/previous-versions/windows/desktop/ms715793(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="getrecordcount"></a> IErrorRecordsImpl::GetRecordCount

OLE DB 레코드 개체의 레코드 수를 반환 합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(GetRecordCount )(ULONG *pcRecords);
```

#### <a name="parameters"></a>매개 변수

참조 [IErrorRecords::GetRecordCount](/previous-versions/windows/desktop/ms722724(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="rgerrors"></a> IErrorRecordsImpl::m_rgErrors

오류 레코드의 배열입니다.

### <a name="syntax"></a>구문

```cpp
CAtlArray< RecordClass > m_rgErrors;
```

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)