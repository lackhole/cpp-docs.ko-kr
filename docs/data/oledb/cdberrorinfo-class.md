---
title: CDBErrorInfo 클래스
ms.date: 11/04/2016
f1_keywords:
- CDBErrorInfo
- ATL::CDBErrorInfo
- ATL.CDBErrorInfo
- ATL.CDBErrorInfo.GetAllErrorInfo
- CDBErrorInfo::GetAllErrorInfo
- ATL::CDBErrorInfo::GetAllErrorInfo
- GetAllErrorInfo
- CDBErrorInfo.GetAllErrorInfo
- CDBErrorInfo::GetBasicErrorInfo
- ATL.CDBErrorInfo.GetBasicErrorInfo
- CDBErrorInfo.GetBasicErrorInfo
- ATL::CDBErrorInfo::GetBasicErrorInfo
- GetBasicErrorInfo
- CDBErrorInfo::GetCustomErrorObject
- ATL.CDBErrorInfo.GetCustomErrorObject
- CDBErrorInfo.GetCustomErrorObject
- ATL::CDBErrorInfo::GetCustomErrorObject
- GetCustomErrorObject
- GetErrorInfo
- ATL.CDBErrorInfo.GetErrorInfo
- CDBErrorInfo.GetErrorInfo
- ATL::CDBErrorInfo::GetErrorInfo
- CDBErrorInfo::GetErrorInfo
- ATL.CDBErrorInfo.GetErrorParameters
- CDBErrorInfo::GetErrorParameters
- ATL::CDBErrorInfo::GetErrorParameters
- CDBErrorInfo.GetErrorParameters
- GetErrorParameters
- CDBErrorInfo.GetErrorRecords
- ATL.CDBErrorInfo.GetErrorRecords
- ATL::CDBErrorInfo::GetErrorRecords
- GetErrorRecords
- CDBErrorInfo::GetErrorRecords
helpviewer_keywords:
- CDBErrorInfo class
- GetAllErrorInfo method
- GetBasicErrorInfo method
- GetCustomErrorObject method
- GetErrorInfo method
- GetErrorParameters method
- GetErrorRecords method
ms.assetid: 9a5c18a2-ee3e-40f5-ab4c-581288d7f737
ms.openlocfilehash: bc13137a4222ba51cf3745f9706353d48068a072
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59021542"
---
# <a name="cdberrorinfo-class"></a>CDBErrorInfo 클래스

OLE DB를 사용 하 여 OLE DB 오류 처리에 대 한 지원 제공 [IErrorRecords](/previous-versions/windows/desktop/ms718112(v=vs.85)) 인터페이스입니다.

## <a name="syntax"></a>구문

```cpp
class CDBErrorInfo
```

## <a name="requirements"></a>요구 사항

**헤더:** atldbcli.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[GetAllErrorInfo](#getallerrorinfo)|오류 레코드에 포함 된 모든 오류 정보를 반환 합니다.|
|[GetBasicErrorInfo](#getbasicerrorinfo)|호출 [IErrorRecords::GetBasicErrorInfo](/previous-versions/windows/desktop/ms723907(v=vs.85)) 지정된 된 오류에 대 한 기본 정보를 반환 합니다.|
|[GetCustomErrorObject](#getcustomerrorobject)|호출 [IErrorRecords::GetCustomErrorObject](/previous-versions/windows/desktop/ms725417(v=vs.85)) 를 사용자 지정 오류 개체 인터페이스 포인터를 반환 합니다.|
|[GetErrorInfo](#geterrorinfo)|호출 [IErrorRecords::GetErrorInfo](/previous-versions/windows/desktop/ms711230(v=vs.85)) 반환할는 `IErrorInfo` 지정된 된 레코드에 대 한 인터페이스 포인터입니다.|
|[GetErrorParameters](#geterrorparameters)|호출 [IErrorRecords::GetErrorParameters](/previous-versions/windows/desktop/ms715793(v=vs.85)) 오류 매개 변수를 반환 합니다.|
|[GetErrorRecords](#geterrorrecords)|지정된 된 개체에 대 한 오류 레코드를 가져옵니다.|

## <a name="remarks"></a>설명

이 인터페이스는 사용자에 게 하나 이상의 오류 레코드를 반환합니다. 호출 [cdberrorinfo:: Geterrorrecords](../../data/oledb/cdberrorinfo-geterrorrecords.md) 첫 번째 오류 레코드 수를 가져옵니다. 다음 중 한 액세스와 같은 함수를 호출 [cdberrorinfo:: Getallerrorinfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md), 각 레코드에 대 한 오류 정보를 검색 합니다.

## <a name="getallerrorinfo"></a> CDBErrorInfo::GetAllErrorInfo

모든 유형의 오류 레코드에 포함 된 오류 정보를 반환 합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT GetAllErrorInfo(ULONG ulRecordNum,
   LCID lcid,  BSTR* pbstrDescription,
   BSTR* pbstrSource = NULL,
   GUID* pguid = NULL,
   DWORD* pdwHelpContext = NULL,
   BSTR* pbstrHelpFile = NULL) const throw();
```

#### <a name="parameters"></a>매개 변수

*ulRecordNum*<br/>
[in] 오류 정보를 반환 하는 레코드의 0부터 시작 하는 번호입니다.

*lcid*<br/>
[in] 반환할 오류 정보에 대 한 로캘 ID입니다.

*pbstrDescription*<br/>
[out] 오류 또는 로캘을 지원 하지 않는 경우 NULL의 텍스트 설명에 대 한 포인터입니다. 설명 부분을 참조하세요.

*pbstrSource*<br/>
[out] 오류를 발생 시킨 구성 요소의 이름을 포함 하는 문자열에 대 한 포인터입니다.

*pguid*<br/>
[out] 오류를 정의한 인터페이스의 GUID에 대 한 포인터입니다.

*pdwHelpContext*<br/>
[out] 오류에 대 한 도움말 컨텍스트 ID에 대 한 포인터입니다.

*pbstrHelpFile*<br/>
[out] 오류를 설명 하는 도움말 파일의 경로를 포함 하는 문자열에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공 하면 S_OK입니다. 참조 [IErrorRecords::GetErrorInfo](/previous-versions/windows/desktop/ms711230(v=vs.85)) 에 *OLE DB Programmer's Reference* 다른 반환 값입니다.

### <a name="remarks"></a>설명

출력 값 *pbstrDescription* 내부적으로 호출 하 여 가져온 `IErrorInfo::GetDescription`, 로캘을 지원 되지 않는 경우 또는 다음 조건이 모두 true 이면 null 값을 설정 하는:

1. 변수의 *lcid* 미국 아닙니다 영어 및

1. 변수의 *lcid* 는 GetUserDefaultLCID 반환한 값과는 같지 않은 합니다.

## <a name="getbasicerrorinfo"></a> CDBErrorInfo::GetBasicErrorInfo

호출 [IErrorRecords::GetBasicErrorInfo](/previous-versions/windows/desktop/ms723907(v=vs.85)) 반환 코드 및 공급자 특정 오류 번호와 같은 오류에 대 한 기본 정보를 반환 합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT GetBasicErrorInfo(ULONG ulRecordNum,
   ERRORINFO* pErrorInfo) const throw();
```

#### <a name="parameters"></a>매개 변수

참조 [IErrorRecords::GetBasicErrorInfo](/previous-versions/windows/desktop/ms723907(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

## <a name="getcustomerrorobject"></a> CDBErrorInfo::GetCustomErrorObject

호출 [IErrorRecords::GetCustomErrorObject](/previous-versions/windows/desktop/ms725417(v=vs.85)) 를 사용자 지정 오류 개체 인터페이스 포인터를 반환 합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT GetCustomErrorObject(ULONG ulRecordNum,
   REFIID riid,IUnknown** ppObject) const throw();
```

#### <a name="parameters"></a>매개 변수

참조 [IErrorRecords::GetCustomErrorObject](/previous-versions/windows/desktop/ms725417(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

## <a name="geterrorinfo"></a> CDBErrorInfo::GetErrorInfo

호출 [IErrorRecords::GetErrorInfo](/previous-versions/windows/desktop/ms711230(v=vs.85)) 반환 하는 [IErrorInfo](/previous-versions/windows/desktop/ms718112(v=vs.85)) 지정된 된 레코드에 대 한 인터페이스 포인터입니다.

### <a name="syntax"></a>구문

```cpp
HRESULT GetErrorInfo(ULONG ulRecordNum,
   LCID lcid,IErrorInfo** ppErrorInfo) const throw();
```

#### <a name="parameters"></a>매개 변수

참조 [IErrorRecords::GetErrorInfo](/previous-versions/windows/desktop/ms711230(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

## <a name="geterrorparameters"></a> CDBErrorInfo::GetErrorParameters

호출 [IErrorRecords::GetErrorParameters](/previous-versions/windows/desktop/ms715793(v=vs.85)) 오류 매개 변수를 반환 합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT GetErrorParameters(ULONG ulRecordNum,
   DISPPARAMS* pdispparams) const throw();
```

#### <a name="parameters"></a>매개 변수

참조 [IErrorRecords::GetErrorParameters](/previous-versions/windows/desktop/ms715793(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

## <a name="geterrorrecords"></a> CDBErrorInfo::GetErrorRecords

지정된 된 개체에 대 한 오류 레코드를 가져옵니다.

### <a name="syntax"></a>구문

```cpp
HRESULT GetErrorRecords(IUnknown* pUnk,
   const IID& iid,
   ULONG* pcRecords) throw();

HRESULT GetErrorRecords(ULONG* pcRecords) throw();
```

#### <a name="parameters"></a>매개 변수

*pUnk*<br/>
[in] 인터페이스 오류 레코드를 가져올 개체입니다.

*iid*<br/>
[in] 오류와 관련 된 인터페이스의 IID입니다.

*pcRecords*<br/>
[out] 오류 레코드 수 (1부터 시작)에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

오류 정보를 얻을 수 있는 인터페이스를 확인 하려는 경우에 함수의 첫 번째 형태를 사용 합니다. 그렇지 않으면 두 번째 형태를 사용 합니다.

## <a name="see-also"></a>참고자료

[DBViewer](../../overview/visual-cpp-samples.md)<br/>
[OLE DB 소비자 템플릿(C++)](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)