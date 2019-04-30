---
title: CMFCFilterChunkValueImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl::Clear
- AFXWIN/CMFCFilterChunkValueImpl::CopyChunk
- AFXWIN/CMFCFilterChunkValueImpl::CopyFrom
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkGUID
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkPID
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkType
- AFXWIN/CMFCFilterChunkValueImpl::GetString
- AFXWIN/CMFCFilterChunkValueImpl::GetValue
- AFXWIN/CMFCFilterChunkValueImpl::GetValueNoAlloc
- AFXWIN/CMFCFilterChunkValueImpl::IsValid
- AFXWIN/CMFCFilterChunkValueImpl::SetBoolValue
- AFXWIN/CMFCFilterChunkValueImpl::SetDwordValue
- AFXWIN/CMFCFilterChunkValueImpl::SetFileTimeValue
- AFXWIN/CMFCFilterChunkValueImpl::SetInt64Value
- AFXWIN/CMFCFilterChunkValueImpl::SetIntValue
- AFXWIN/CMFCFilterChunkValueImpl::SetLongValue
- AFXWIN/CMFCFilterChunkValueImpl::SetSystemTimeValue
- AFXWIN/CMFCFilterChunkValueImpl::SetTextValue
- AFXWIN/CMFCFilterChunkValueImpl::SetChunk
helpviewer_keywords:
- CMFCFilterChunkValueImpl [MFC], CMFCFilterChunkValueImpl
- CMFCFilterChunkValueImpl [MFC], Clear
- CMFCFilterChunkValueImpl [MFC], CopyChunk
- CMFCFilterChunkValueImpl [MFC], CopyFrom
- CMFCFilterChunkValueImpl [MFC], GetChunkGUID
- CMFCFilterChunkValueImpl [MFC], GetChunkPID
- CMFCFilterChunkValueImpl [MFC], GetChunkType
- CMFCFilterChunkValueImpl [MFC], GetString
- CMFCFilterChunkValueImpl [MFC], GetValue
- CMFCFilterChunkValueImpl [MFC], GetValueNoAlloc
- CMFCFilterChunkValueImpl [MFC], IsValid
- CMFCFilterChunkValueImpl [MFC], SetBoolValue
- CMFCFilterChunkValueImpl [MFC], SetDwordValue
- CMFCFilterChunkValueImpl [MFC], SetFileTimeValue
- CMFCFilterChunkValueImpl [MFC], SetInt64Value
- CMFCFilterChunkValueImpl [MFC], SetIntValue
- CMFCFilterChunkValueImpl [MFC], SetLongValue
- CMFCFilterChunkValueImpl [MFC], SetSystemTimeValue
- CMFCFilterChunkValueImpl [MFC], SetTextValue
- CMFCFilterChunkValueImpl [MFC], SetChunk
ms.assetid: 3c833f23-5b88-4d08-9e09-ca6a8aec88bf
ms.openlocfilehash: b883d442342dd9fbbd074d9f8fcab76f81ef9864
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62237560"
---
# <a name="cmfcfilterchunkvalueimpl-class"></a>CMFCFilterChunkValueImpl 클래스

청크 및 속성 값 쌍의 논리를 간소화 하는 클래스입니다.

## <a name="syntax"></a>구문

```
class CMFCFilterChunkValueImpl : public ATL::IFilterChunkValue;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMFCFilterChunkValueImpl::~CMFCFilterChunkValueImpl](#_dtorcmfcfilterchunkvalueimpl)|개체를 destructs입니다.|
|[CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl](#cmfcfilterchunkvalueimpl)|개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCFilterChunkValueImpl::Clear](#clear)|ChunkValue를 지웁니다.|
|[CMFCFilterChunkValueImpl::CopyChunk](#copychunk)|이 청크를 청크의 특징을 설명 하는 구조에 복사 합니다.|
|[CMFCFilterChunkValueImpl::CopyFrom](#copyfrom)|다른 값에서이 청크 값을 초기화합니다.|
|[CMFCFilterChunkValueImpl::GetChunkGUID](#getchunkguid)|GUID 청크를 검색합니다.|
|[CMFCFilterChunkValueImpl::GetChunkPID](#getchunkpid)|청크 PID (속성 ID)를 검색합니다.|
|[CMFCFilterChunkValueImpl::GetChunkType](#getchunktype)|가져옵니다 청크 형식입니다.|
|[CMFCFilterChunkValueImpl::GetString](#getstring)|문자열 값을 검색 합니다.|
|[CMFCFilterChunkValueImpl::GetValue](#getvalue)|할당 된 propvariant으로 값을 검색합니다.|
|[CMFCFilterChunkValueImpl::GetValueNoAlloc](#getvaluenoalloc)|(내부 값)을 할당 되지 않은 반환 값입니다.|
|[CMFCFilterChunkValueImpl::IsValid](#isvalid)|이 속성 값이 유효한 지 여부를 확인 합니다.|
|[CMFCFilterChunkValueImpl::SetBoolValue](#setboolvalue)|오버로드됨. 부울 값을 키로 속성을 설정합니다.|
|[CMFCFilterChunkValueImpl::SetDwordValue](#setdwordvalue)|DWORD 키로 속성을 설정합니다.|
|[CMFCFilterChunkValueImpl::SetFileTimeValue](#setfiletimevalue)|Filetime 키로 속성을 설정합니다.|
|[CMFCFilterChunkValueImpl::SetInt64Value](#setint64value)|Int64로 키 속성을 설정합니다.|
|[CMFCFilterChunkValueImpl::SetIntValue](#setintvalue)|정수를 키로 속성을 설정합니다.|
|[CMFCFilterChunkValueImpl::SetLongValue](#setlongvalue)|LONG 값을 키로 속성을 설정합니다.|
|[CMFCFilterChunkValueImpl::SetSystemTimeValue](#setsystemtimevalue)|속성을 SystemTime 키로 설정합니다.|
|[CMFCFilterChunkValueImpl::SetTextValue](#settextvalue)|유니코드 문자열에 키로 속성을 설정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CMFCFilterChunkValueImpl::SetChunk](#setchunk)|청크의 공용 속성을 설정 하는 도우미 함수입니다.|

## <a name="remarks"></a>설명

를 사용 하려면 단순히 만든 올바른 종류의 CMFCFilterChunkValueImpl 클래스

예제:

CMFCFilterChunkValueImpl 청크;

hr = chunk.SetBoolValue(PKEY_IsAttachment, true);

또는

hr = chunk.SetFileTimeValue(PKEY_ItemDate, ftLastModified);

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ATL::IFilterChunkValue`

[CMFCFilterChunkValueImpl](../../mfc/reference/cmfcfilterchunkvalueimpl-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="clear"></a>  CMFCFilterChunkValueImpl::Clear

ChunkValue를 지웁니다.

```
void Clear();
```

### <a name="remarks"></a>설명

##  <a name="cmfcfilterchunkvalueimpl"></a>  CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl

개체를 생성합니다.

```
CMFCFilterChunkValueImpl();
```

### <a name="remarks"></a>설명

##  <a name="_dtorcmfcfilterchunkvalueimpl"></a>  CMFCFilterChunkValueImpl::~CMFCFilterChunkValueImpl

개체를 destructs입니다.

```
virtual ~CMFCFilterChunkValueImpl();
```

### <a name="remarks"></a>설명

##  <a name="copychunk"></a>  CMFCFilterChunkValueImpl::CopyChunk

이 청크를 청크의 특징을 설명 하는 구조에 복사 합니다.

```
HRESULT CopyChunk(STAT_CHUNK* pStatChunk);
```

### <a name="parameters"></a>매개 변수

*pStatChunk*<br/>
청크의 특성을 설명 하는 대상 값에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고 그렇지 않으면 오류 코드입니다.

### <a name="remarks"></a>설명

##  <a name="copyfrom"></a>  CMFCFilterChunkValueImpl::CopyFrom

다른 값에서이 청크 값을 초기화합니다.

```
void CopyFrom (IFilterChunkValue* pValue);
```

### <a name="parameters"></a>매개 변수

*pValue*<br/>
복사할 소스 값을 지정 합니다.

### <a name="remarks"></a>설명

##  <a name="getchunkguid"></a>  CMFCFilterChunkValueImpl::GetChunkGUID

GUID 청크를 검색합니다.

```
REFGUID GetChunkGUID() const;
```

### <a name="return-value"></a>반환 값

참조 된 청크를 식별 하는 GUID입니다.

### <a name="remarks"></a>설명

##  <a name="getchunkpid"></a>  CMFCFilterChunkValueImpl::GetChunkPID

청크 PID (속성 ID)를 검색합니다.

```
DWORD GetChunkPID() const;
```

### <a name="return-value"></a>반환 값

속성 ID를 포함 하는 DWORD 값

### <a name="remarks"></a>설명

##  <a name="getchunktype"></a>  CMFCFilterChunkValueImpl::GetChunkType

청크 형식을 검색합니다.

```
CHUNKSTATE GetChunkType() const;
```

### <a name="return-value"></a>반환 값

현재 청크는 텍스트 형식 속성 또는 값 형식 속성 인지 여부를 지정 하는 CHUNKSTATE 열거 값입니다.

### <a name="remarks"></a>설명

##  <a name="getstring"></a>  CMFCFilterChunkValueImpl::GetString

문자열 값을 검색 합니다.

```
CString &GetString();
```

### <a name="return-value"></a>반환 값

청크 값을 포함 하는 문자열입니다.

### <a name="remarks"></a>설명

##  <a name="getvalue"></a>  CMFCFilterChunkValueImpl::GetValue

할당 된 propvariant으로 값을 검색합니다.

```
HRESULT GetValue(PROPVARIANT** ppPropVariant);
```

### <a name="parameters"></a>매개 변수

*ppPropVariant*<br/>
함수는 반환 될 때이 매개 변수는 청크 값을 포함 합니다.

### <a name="return-value"></a>반환 값

청크 값을 복사 했습니다 PROPVARIANT 성공적으로 할당 된 경우 S_OK *ppPropVariant*이 고 그렇지 않으면 오류 코드입니다.

### <a name="remarks"></a>설명

##  <a name="getvaluenoalloc"></a>  CMFCFilterChunkValueImpl::GetValueNoAlloc

할당 되지 않은 (내부) 값을 반환합니다.

```
PROPVARIANT GetValueNoAlloc ();
```

### <a name="return-value"></a>반환 값

현재 청크 값을 반환 합니다.

### <a name="remarks"></a>설명

##  <a name="isvalid"></a>  CMFCFilterChunkValueImpl::IsValid

이 속성 값이 유효한 지 여부를 확인 합니다.

```
BOOL IsValid() const;
```

### <a name="return-value"></a>반환 값

현재 청크 값이 잘못 되었습니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="setboolvalue"></a>  CMFCFilterChunkValueImpl::SetBoolValue

오버로드됨. 부울 값을 키로 속성을 설정합니다.

```
HRESULT SetBoolValue(
    REFPROPERTYKEY pkey,
    BOOL bVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);

HRESULT SetBoolValue(
    REFPROPERTYKEY pkey,
    VARIANT_BOOL bVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>매개 변수

*pkey*<br/>
속성 키를 지정합니다.

*bVal*<br/>
설정할 청크 값을 지정 합니다.

*chunkType*<br/>
플래그는이 청크는 텍스트 형식 또는 값 형식 속성에 포함 되는지 여부를 나타냅니다. 플래그 값은 CHUNKSTATE 열거형에서 가져옵니다.

*locale*<br/>
언어 및 하위 텍스트의 청크를 사용 하 여 연결 합니다. 청크 로캘이 문서 인덱서에서 적절 한 단어 문자의 분리 하는 데 사용 됩니다. 청크 텍스트 형식이 아니고 VT_LPWSTR,: VT_LPSTR, 또는 VT_BSTR 데이터 형식과 값 형식의 경우이 필드는 무시 됩니다.

*cwcLenSource*<br/>
현재 청크가 파생 된 원본 텍스트의 문자 길이입니다. 값이 0 이면 소스 텍스트 및 파생된 텍스트의 문자 단위로 대응을 나타냅니다. 0이 아닌 값을 이러한 직접적인 대응이 없습니다 있음을 의미 합니다.

*cwcStartSource*<br/>
파생된 청크에 대 한 소스 텍스트 원본 청크의 시작 오프셋입니다.

*chunkBreakType*<br/>
형식에서 현재 청크가 이전 청크를 구분 하는 중단입니다. CHUNK_BREAKTYPE 열거형의 값은입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고 그렇지 않으면 오류 코드입니다.

### <a name="remarks"></a>설명

##  <a name="setchunk"></a>  CMFCFilterChunkValueImpl::SetChunk

청크의 공용 속성을 설정 하는 도우미 함수입니다.

```
HRESULT SetChunk(
    REFPROPERTYKEY pkey,
    CHUNKSTATE chunkType=CHUNK_VALUE,
    LCID locale=0,
    DWORD cwcLenSource=0,
    DWORD cwcStartSource=0,
    CHUNK_BREAKTYPE chunkBreakType=CHUNK_NO_BREAK);
```

### <a name="parameters"></a>매개 변수

*pkey*<br/>
속성 키를 지정합니다.

*chunkType*<br/>
플래그는이 청크는 텍스트 형식 또는 값 형식 속성에 포함 되는지 여부를 나타냅니다. 플래그 값은 CHUNKSTATE 열거형에서 가져옵니다.

*locale*<br/>
언어 및 하위 텍스트의 청크를 사용 하 여 연결 합니다. 청크 로캘이 문서 인덱서에서 적절 한 단어 문자의 분리 하는 데 사용 됩니다. 청크 텍스트 형식이 아니고 VT_LPWSTR,: VT_LPSTR, 또는 VT_BSTR 데이터 형식과 값 형식의 경우이 필드는 무시 됩니다.

*cwcLenSource*<br/>
현재 청크가 파생 된 원본 텍스트의 문자 길이입니다. 값이 0 이면 소스 텍스트 및 파생된 텍스트의 문자 단위로 대응을 나타냅니다. 0이 아닌 값을 이러한 직접적인 대응이 없습니다 있음을 의미 합니다.

*cwcStartSource*<br/>
파생된 청크에 대 한 소스 텍스트 원본 청크의 시작 오프셋입니다.

*chunkBreakType*<br/>
형식에서 현재 청크가 이전 청크를 구분 하는 중단입니다. CHUNK_BREAKTYPE 열거형의 값은입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고 그렇지 않으면 오류 코드입니다.

### <a name="remarks"></a>설명

##  <a name="setdwordvalue"></a>  CMFCFilterChunkValueImpl::SetDwordValue

DWORD 키로 속성을 설정 합니다.

```
HRESULT SetDwordValue(
    REFPROPERTYKEY pkey,
    DWORD dwVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>매개 변수

*pkey*<br/>
속성 키를 지정합니다.

*dwVal*<br/>
설정할 청크 값을 지정 합니다.

*chunkType*<br/>
플래그는이 청크는 텍스트 형식 또는 값 형식 속성에 포함 되는지 여부를 나타냅니다. 플래그 값은 CHUNKSTATE 열거형에서 가져옵니다.

*locale*<br/>
언어 및 하위 텍스트의 청크를 사용 하 여 연결 합니다. 청크 로캘이 문서 인덱서에서 적절 한 단어 문자의 분리 하는 데 사용 됩니다. 청크 텍스트 형식이 아니고 VT_LPWSTR,: VT_LPSTR, 또는 VT_BSTR 데이터 형식과 값 형식의 경우이 필드는 무시 됩니다.

*cwcLenSource*<br/>
현재 청크가 파생 된 원본 텍스트의 문자 길이입니다. 값이 0 이면 소스 텍스트 및 파생된 텍스트의 문자 단위로 대응을 나타냅니다. 0이 아닌 값을 이러한 직접적인 대응이 없습니다 있음을 의미 합니다.

*cwcStartSource*<br/>
파생된 청크에 대 한 소스 텍스트 원본 청크의 시작 오프셋입니다.

*chunkBreakType*<br/>
형식에서 현재 청크가 이전 청크를 구분 하는 중단입니다. CHUNK_BREAKTYPE 열거형의 값은입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고 그렇지 않으면 오류 코드입니다.

### <a name="remarks"></a>설명

##  <a name="setfiletimevalue"></a>  CMFCFilterChunkValueImpl::SetFileTimeValue

Filetime 키로 속성을 설정 합니다.

```
HRESULT SetFileTimeValue(
    REFPROPERTYKEY pkey,
    FILETIME dtVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>매개 변수

*pkey*<br/>
속성 키를 지정합니다.

*dtVal*<br/>
설정할 청크 값을 지정 합니다.

*chunkType*<br/>
플래그는이 청크는 텍스트 형식 또는 값 형식 속성에 포함 되는지 여부를 나타냅니다. 플래그 값은 CHUNKSTATE 열거형에서 가져옵니다.

*locale*<br/>
언어 및 하위 텍스트의 청크를 사용 하 여 연결 합니다. 청크 로캘이 문서 인덱서에서 적절 한 단어 문자의 분리 하는 데 사용 됩니다. 청크 텍스트 형식이 아니고 VT_LPWSTR,: VT_LPSTR, 또는 VT_BSTR 데이터 형식과 값 형식의 경우이 필드는 무시 됩니다.

*cwcLenSource*<br/>
현재 청크가 파생 된 원본 텍스트의 문자 길이입니다. 값이 0 이면 소스 텍스트 및 파생된 텍스트의 문자 단위로 대응을 나타냅니다. 0이 아닌 값을 이러한 직접적인 대응이 없습니다 있음을 의미 합니다.

*cwcStartSource*<br/>
파생된 청크에 대 한 소스 텍스트 원본 청크의 시작 오프셋입니다.

*chunkBreakType*<br/>
형식에서 현재 청크가 이전 청크를 구분 하는 중단입니다. CHUNK_BREAKTYPE 열거형의 값은입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고 그렇지 않으면 오류 코드입니다.

### <a name="remarks"></a>설명

##  <a name="setint64value"></a>  CMFCFilterChunkValueImpl::SetInt64Value

Int64로 키 속성을 설정 합니다.

```
HRESULT SetInt64Value(
    REFPROPERTYKEY pkey,
    __int64 nVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>매개 변수

*pkey*<br/>
속성 키를 지정합니다.

*nVal*<br/>
설정할 청크 값을 지정 합니다.

*chunkType*<br/>
플래그는이 청크는 텍스트 형식 또는 값 형식 속성에 포함 되는지 여부를 나타냅니다. 플래그 값은 CHUNKSTATE 열거형에서 가져옵니다.

*locale*<br/>
언어 및 하위 텍스트의 청크를 사용 하 여 연결 합니다. 청크 로캘이 문서 인덱서에서 적절 한 단어 문자의 분리 하는 데 사용 됩니다. 청크 텍스트 형식이 아니고 VT_LPWSTR,: VT_LPSTR, 또는 VT_BSTR 데이터 형식과 값 형식의 경우이 필드는 무시 됩니다.

*cwcLenSource*<br/>
현재 청크가 파생 된 원본 텍스트의 문자 길이입니다. 값이 0 이면 소스 텍스트 및 파생된 텍스트의 문자 단위로 대응을 나타냅니다. 0이 아닌 값을 이러한 직접적인 대응이 없습니다 있음을 의미 합니다.

*cwcStartSource*<br/>
파생된 청크에 대 한 소스 텍스트 원본 청크의 시작 오프셋입니다.

*chunkBreakType*<br/>
형식에서 현재 청크가 이전 청크를 구분 하는 중단입니다. CHUNK_BREAKTYPE 열거형의 값은입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고 그렇지 않으면 오류 코드입니다.

### <a name="remarks"></a>설명

##  <a name="setintvalue"></a>  CMFCFilterChunkValueImpl::SetIntValue

정수를 키로 속성을 설정 합니다.

```
HRESULT SetIntValue(
    REFPROPERTYKEY pkey,
    int nVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>매개 변수

*pkey*<br/>
속성 키를 지정합니다.

*nVal*<br/>
설정할 청크 값을 지정 합니다.

*chunkType*<br/>
플래그는이 청크는 텍스트 형식 또는 값 형식 속성에 포함 되는지 여부를 나타냅니다. 플래그 값은 CHUNKSTATE 열거형에서 가져옵니다.

*locale*<br/>
언어 및 하위 텍스트의 청크를 사용 하 여 연결 합니다. 청크 로캘이 문서 인덱서에서 적절 한 단어 문자의 분리 하는 데 사용 됩니다. 청크 텍스트 형식이 아니고 VT_LPWSTR,: VT_LPSTR, 또는 VT_BSTR 데이터 형식과 값 형식의 경우이 필드는 무시 됩니다.

*cwcLenSource*<br/>
현재 청크가 파생 된 원본 텍스트의 문자 길이입니다. 값이 0 이면 소스 텍스트 및 파생된 텍스트의 문자 단위로 대응을 나타냅니다. 0이 아닌 값을 이러한 직접적인 대응이 없습니다 있음을 의미 합니다.

*cwcStartSource*<br/>
파생된 청크에 대 한 소스 텍스트 원본 청크의 시작 오프셋입니다.

*chunkBreakType*<br/>
형식에서 현재 청크가 이전 청크를 구분 하는 중단입니다. CHUNK_BREAKTYPE 열거형의 값은입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고 그렇지 않으면 오류 코드입니다.

### <a name="remarks"></a>설명

##  <a name="setlongvalue"></a>  CMFCFilterChunkValueImpl::SetLongValue

LONG 값을 키로 속성을 설정 합니다.

```
HRESULT SetLongValue(
    REFPROPERTYKEY pkey,
    long lVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>매개 변수

*pkey*<br/>
속성 키를 지정합니다.

*lVal*<br/>
설정할 청크 값을 지정 합니다.

*chunkType*<br/>
플래그는이 청크는 텍스트 형식 또는 값 형식 속성에 포함 되는지 여부를 나타냅니다. 플래그 값은 CHUNKSTATE 열거형에서 가져옵니다.

*locale*<br/>
언어 및 하위 텍스트의 청크를 사용 하 여 연결 합니다. 청크 로캘이 문서 인덱서에서 적절 한 단어 문자의 분리 하는 데 사용 됩니다. 청크 텍스트 형식이 아니고 VT_LPWSTR,: VT_LPSTR, 또는 VT_BSTR 데이터 형식과 값 형식의 경우이 필드는 무시 됩니다.

*cwcLenSource*<br/>
현재 청크가 파생 된 원본 텍스트의 문자 길이입니다. 값이 0 이면 소스 텍스트 및 파생된 텍스트의 문자 단위로 대응을 나타냅니다. 0이 아닌 값을 이러한 직접적인 대응이 없습니다 있음을 의미 합니다.

*cwcStartSource*<br/>
파생된 청크에 대 한 소스 텍스트 원본 청크의 시작 오프셋입니다.

*chunkBreakType*<br/>
형식에서 현재 청크가 이전 청크를 구분 하는 중단입니다. CHUNK_BREAKTYPE 열거형의 값은입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고 그렇지 않으면 오류 코드입니다.

### <a name="remarks"></a>설명

##  <a name="setsystemtimevalue"></a>  CMFCFilterChunkValueImpl::SetSystemTimeValue

속성을 SystemTime 키로 설정합니다.

```
HRESULT SetSystemTimeValue(
    REFPROPERTYKEY pkey,
    const SYSTEMTIME& systemTime,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale=0,
    DWORD cwcLenSource=0,
    DWORD cwcStartSource=0,
    CHUNK_BREAKTYPE chunkBreakType=CHUNK_NO_BREAK);
```

### <a name="parameters"></a>매개 변수

*pkey*<br/>
속성 키를 지정합니다.

*systemTime*<br/>
설정할 청크 값을 지정 합니다.

*chunkType*<br/>
플래그는이 청크는 텍스트 형식 또는 값 형식 속성에 포함 되는지 여부를 나타냅니다. 플래그 값은 CHUNKSTATE 열거형에서 가져옵니다.

*locale*<br/>
언어 및 하위 텍스트의 청크를 사용 하 여 연결 합니다. 청크 로캘이 문서 인덱서에서 적절 한 단어 문자의 분리 하는 데 사용 됩니다. 청크 텍스트 형식이 아니고 VT_LPWSTR,: VT_LPSTR, 또는 VT_BSTR 데이터 형식과 값 형식의 경우이 필드는 무시 됩니다.

*cwcLenSource*<br/>
현재 청크가 파생 된 원본 텍스트의 문자 길이입니다. 값이 0 이면 소스 텍스트 및 파생된 텍스트의 문자 단위로 대응을 나타냅니다. 0이 아닌 값을 이러한 직접적인 대응이 없습니다 있음을 의미 합니다.

*cwcStartSource*<br/>
파생된 청크에 대 한 소스 텍스트 원본 청크의 시작 오프셋입니다.

*chunkBreakType*<br/>
형식에서 현재 청크가 이전 청크를 구분 하는 중단입니다. CHUNK_BREAKTYPE 열거형의 값은입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고 그렇지 않으면 오류 코드입니다.

### <a name="remarks"></a>설명

##  <a name="settextvalue"></a>  CMFCFilterChunkValueImpl::SetTextValue

유니코드 문자열에 키로 속성을 설정합니다.

```
HRESULT SetTextValue(
    REFPROPERTYKEY pkey,
    LPCTSTR pszValue,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>매개 변수

*pkey*<br/>
속성 키를 지정합니다.

*pszValue*<br/>
설정할 청크 값을 지정 합니다.

*chunkType*<br/>
플래그는이 청크는 텍스트 형식 또는 값 형식 속성에 포함 되는지 여부를 나타냅니다. 플래그 값은 CHUNKSTATE 열거형에서 가져옵니다.

*locale*<br/>
언어 및 하위 텍스트의 청크를 사용 하 여 연결 합니다. 청크 로캘이 문서 인덱서에서 적절 한 단어 문자의 분리 하는 데 사용 됩니다. 청크 텍스트 형식이 아니고 VT_LPWSTR,: VT_LPSTR, 또는 VT_BSTR 데이터 형식과 값 형식의 경우이 필드는 무시 됩니다.

*cwcLenSource*<br/>
현재 청크가 파생 된 원본 텍스트의 문자 길이입니다. 값이 0 이면 소스 텍스트 및 파생된 텍스트의 문자 단위로 대응을 나타냅니다. 0이 아닌 값을 이러한 직접적인 대응이 없습니다 있음을 의미 합니다.

*cwcStartSource*<br/>
파생된 청크에 대 한 소스 텍스트 원본 청크의 시작 오프셋입니다.

*chunkBreakType*<br/>
형식에서 현재 청크가 이전 청크를 구분 하는 중단입니다. CHUNK_BREAKTYPE 열거형의 값은입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고 그렇지 않으면 오류 코드입니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
