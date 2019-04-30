---
title: CPropExchange 클래스
ms.date: 11/04/2016
f1_keywords:
- CPropExchange
- AFXCTL/CPropExchange
- AFXCTL/CPropExchange::ExchangeBlobProp
- AFXCTL/CPropExchange::ExchangeFontProp
- AFXCTL/CPropExchange::ExchangePersistentProp
- AFXCTL/CPropExchange::ExchangeProp
- AFXCTL/CPropExchange::ExchangeVersion
- AFXCTL/CPropExchange::GetVersion
- AFXCTL/CPropExchange::IsAsynchronous
- AFXCTL/CPropExchange::IsLoading
helpviewer_keywords:
- CPropExchange [MFC], ExchangeBlobProp
- CPropExchange [MFC], ExchangeFontProp
- CPropExchange [MFC], ExchangePersistentProp
- CPropExchange [MFC], ExchangeProp
- CPropExchange [MFC], ExchangeVersion
- CPropExchange [MFC], GetVersion
- CPropExchange [MFC], IsAsynchronous
- CPropExchange [MFC], IsLoading
ms.assetid: ed872180-e770-4942-892a-92139d501fab
ms.openlocfilehash: 4210399e32c2bb39008afa75b787c19e3338a7d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372428"
---
# <a name="cpropexchange-class"></a>CPropExchange 클래스

OLE 컨트롤의 지속성 구현을 지원합니다.

## <a name="syntax"></a>구문

```
class AFX_NOVTABLE CPropExchange
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CPropExchange::ExchangeBlobProp](#exchangeblobprop)|이진 대형 개체 (BLOB) 속성을 교환합니다.|
|[CPropExchange::ExchangeFontProp](#exchangefontprop)|글꼴 속성을 교환합니다.|
|[CPropExchange::ExchangePersistentProp](#exchangepersistentprop)|컨트롤 사이의 파일 속성을 교환합니다.|
|[CPropExchange::ExchangeProp](#exchangeprop)|모든 기본 제공 형식의 속성을 교환합니다.|
|[CPropExchange::ExchangeVersion](#exchangeversion)|OLE 컨트롤의 버전 번호를 교환합니다.|
|[CPropExchange::GetVersion](#getversion)|OLE 컨트롤의 버전 번호를 검색합니다.|
|[CPropExchange::IsAsynchronous](#isasynchronous)|속성 교환 비동기적으로 완료 되는 경우를 결정 합니다.|
|[CPropExchange::IsLoading](#isloading)|속성 되 고 있는지 여부를 나타내는 컨트롤에 로드 하거나이를 저장 합니다.|

## <a name="remarks"></a>설명

`CPropExchange` 기본 클래스는 없습니다.

컨텍스트 및 속성 exchange의 방향을 설정합니다.

지 속성은 일반적으로 컨트롤 자체와 미디어 간에 해당 속성을 나타내는 컨트롤의 상태 정보를 교환 합니다.

파생 된 개체를 생성 하는 프레임 워크 `CPropExchange` OLE 컨트롤의 속성에서 로드 되는 알림을 받았을 때 또는 저장소에 영구 저장된 합니다.

이 대 한 포인터를 전달 하는 프레임 워크 `CPropExchange` 컨트롤의 개체 `DoPropExchange` 함수입니다. 컨트롤, 컨트롤의 시작 파일을 만들려면 마법사를 사용 하는 경우 `DoPropExchange` 함수 호출 `COleControl::DoPropExchange`합니다. 기본 클래스 버전 교환 컨트롤의 스톡 속성 컨트롤에 추가한 파생된 클래스의 버전 exchange 속성을 수정할 수 있습니다.

`CPropExchange` 컨트롤의 속성을 serialize 하거나 부하 또는 컨트롤 생성 시 컨트롤의 속성을 초기화 데 사용할 수 있습니다. 합니다 `ExchangeProp` 하 고 `ExchangeFontProp` 의 멤버 함수 `CPropExchange` 속성을 저장 하 고 다양 한 미디어에서 로드 합니다.

사용 하 여 대 한 자세한 내용은 `CPropExchange`, 문서를 참고 [MFC ActiveX 컨트롤: 속성 페이지](../../mfc/mfc-activex-controls-property-pages.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CPropExchange`

## <a name="requirements"></a>요구 사항

**헤더:** afxctl.h

##  <a name="exchangeblobprop"></a>  CPropExchange::ExchangeBlobProp

Binary large object (BLOB) 데이터를 저장 하는 속성을 serialize 합니다.

```
virtual BOOL ExchangeBlobProp(
    LPCTSTR pszPropName,
    HGLOBAL* phBlob,
    HGLOBAL hBlobDefault = NULL) = 0;
```

### <a name="parameters"></a>매개 변수

*pszPropName*<br/>
교환 되는 속성의 이름입니다.

*phBlob*<br/>
변수의 속성을 저장할 위치를 가리키는 포인터입니다 (변수가 일반적으로 클래스의 멤버).

*hBlobDefault*<br/>
속성에 대 한 기본 값입니다.

### <a name="return-value"></a>반환 값

Exchange에 성공 하면 0이 아닌 값 실패 한 경우 0입니다.

### <a name="remarks"></a>설명

속성의 값에서 읽거나 쓸 적절 한 참조 변수 처럼 *phBlob*합니다. 하는 경우 *hBlobDefault* 지정, 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 serialization 어떤 이유로 실패 하는 경우 사용 됩니다.

함수 `CArchivePropExchange::ExchangeBlobProp`, `CResetPropExchange::ExchangeBlobProp`, 및 `CPropsetPropExchange::ExchangeBlobProp` 이 순수 가상 함수를 재정의 합니다.

##  <a name="exchangefontprop"></a>  CPropExchange::ExchangeFontProp

저장 매체와 컨트롤 간의 글꼴 속성을 교환합니다.

```
virtual BOOL ExchangeFontProp(
    LPCTSTR pszPropName,
    CFontHolder& font,
    const FONTDESC* pFontDesc,
    LPFONTDISP pFontDispAmbient) = 0;
```

### <a name="parameters"></a>매개 변수

*pszPropName*<br/>
교환 되는 속성의 이름입니다.

*font*<br/>
에 대 한 참조를 [CFontHolder](../../mfc/reference/cfontholder-class.md) 글꼴 속성을 포함 하는 개체입니다.

*pFontDesc*<br/>
에 대 한 포인터를 [FONTDESC](/windows/desktop/api/olectl/ns-olectl-tagfontdesc) font 속성의 기본 상태로 초기화에 대 한 값이 포함 된 구조 때 *pFontDispAmbient* NULL입니다.

*pFontDispAmbient*<br/>
에 대 한 포인터를 `IFontDisp` font 속성의 기본 상태로 초기화에 사용 되는 글꼴의 인터페이스입니다.

### <a name="return-value"></a>반환 값

Exchange에 성공 하면 0이 아닌 값 실패 한 경우 0입니다.

### <a name="remarks"></a>설명

Font 속성 매체에서 컨트롤을 로드 하 고, 글꼴 특성에서 미디어 검색 됩니다와 `CFontHolder` 개체에서 참조 *글꼴* 으로 초기화 됩니다. Font 속성에 저장 되는 경우 글꼴 개체의 특징을 미디어에 기록 됩니다.

함수 `CArchivePropExchange::ExchangeFontProp`, `CResetPropExchange::ExchangeFontProp`, 및 `CPropsetPropExchange::ExchangeFontProp` 이 순수 가상 함수를 재정의 합니다.

##  <a name="exchangepersistentprop"></a>  CPropExchange::ExchangePersistentProp

컨트롤 사이의 파일 속성을 교환합니다.

```
virtual BOOL ExchangePersistentProp(
    LPCTSTR pszPropName,
    LPUNKNOWN* ppUnk,
    REFIID iid,
    LPUNKNOWN pUnkDefault) = 0;
```

### <a name="parameters"></a>매개 변수

*pszPropName*<br/>
교환 되는 속성의 이름입니다.

*ppUnk*<br/>
속성에 대 한 포인터를 포함 하는 변수에 대 한 포인터 `IUnknown` 인터페이스 (이 변수는 클래스의 멤버가 일반적으로).

*iid*<br/>
컨트롤을 사용 하는 속성에 대 한 인터페이스의 인터페이스 ID입니다.

*pUnkDefault*<br/>
속성에 대 한 기본 값입니다.

### <a name="return-value"></a>반환 값

Exchange에 성공 하면 0이 아닌 값 실패 한 경우 0입니다.

### <a name="remarks"></a>설명

속성 파일에서 컨트롤을 로드 하 고, 속성 생성 되어 파일에서 초기화 됩니다. 속성에 저장 되는 경우 해당 값은 파일에 기록 됩니다.

함수 `CArchivePropExchange::ExchangePersistentProp`, `CResetPropExchange::ExchangePersistentProp`, 및 `CPropsetPropExchange::ExchangePersistentProp` 이 순수 가상 함수를 재정의 합니다.

##  <a name="exchangeprop"></a>  CPropExchange::ExchangeProp

저장 매체 사이의 컨트롤 속성을 교환합니다.

```
virtual BOOL ExchangeProp(
    LPCTSTR pszPropName,
    VARTYPE vtProp,
    void* pvProp,
    const void* pvDefault = NULL) = 0 ;
```

### <a name="parameters"></a>매개 변수

*pszPropName*<br/>
교환 되는 속성의 이름입니다.

*vtProp*<br/>
교환 되는 속성의 유형을 지정 하는 기호입니다. 가능한 값은 다음과 같습니다.

|기호|속성 형식|
|------------|-------------------|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_BOOL|**BOOL**|
|VT_BSTR|`CString`|
|VT_CY|**CY**|
|VT_R4|**float**|
|VT_R8|**double**|

*pvProp*<br/>
속성의 값에 대 한 포인터입니다.

*pvDefault*<br/>
속성의 기본값에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

Exchange에 성공 하면 0이 아닌 값 실패 한 경우 0입니다.

### <a name="remarks"></a>설명

속성 매체에서 컨트롤을 로드 하 고, 속성 값을 미디어에서 검색 되며 가리키는 개체에 저장 *pvProp*합니다. 속성 매체에 저장 하려는 경우는 개체의 값을 가리키는 *pvProp* 미디어에 기록 됩니다.

함수 `CArchivePropExchange::ExchangeProp`, `CResetPropExchange::ExchangeProp`, 및 `CPropsetPropExchange::ExchangeProp` 이 순수 가상 함수를 재정의 합니다.

##  <a name="exchangeversion"></a>  CPropExchange::ExchangeVersion

버전 번호의 지 속성을 처리 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual BOOL ExchangeVersion(
    DWORD& dwVersionLoaded,
    DWORD dwVersionDefault,
    BOOL bConvert);
```

### <a name="parameters"></a>매개 변수

*dwVersionLoaded*<br/>
로드 되는 영구 데이터의 버전 번호를 저장 하는 변수에 대 한 참조입니다.

*dwVersionDefault*<br/>
컨트롤의 현재 버전 번호입니다.

*bConvert*<br/>
현재 버전에 영구 데이터를 변환 또는 로드 된 버전 유지 여부를 나타냅니다.

### <a name="return-value"></a>반환 값

함수가 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

##  <a name="getversion"></a>  CPropExchange::GetVersion

컨트롤의 버전 번호를 검색 하려면이 함수를 호출 합니다.

```
DWORD GetVersion();
```

### <a name="return-value"></a>반환 값

컨트롤의 버전 번호입니다.

##  <a name="isasynchronous"></a>  CPropExchange::IsAsynchronous

속성 교환 비동기적으로 완료 되는 경우를 결정 합니다.

```
BOOL IsAsynchronous();
```

### <a name="return-value"></a>반환 값

속성이 있으면 TRUE를 반환 교환 비동기적으로 그렇지 않으면 FALSE입니다.

##  <a name="isloading"></a>  CPropExchange::IsLoading

속성 되 고 있는지 여부를 결정 하는이 함수를 호출 컨트롤에 로드 하거나이를 저장 합니다.

```
BOOL IsLoading();
```

### <a name="return-value"></a>반환 값

속성; 로드 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COleControl::DoPropExchange](../../mfc/reference/colecontrol-class.md#dopropexchange)
