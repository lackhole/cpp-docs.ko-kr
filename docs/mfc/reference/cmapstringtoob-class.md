---
title: CMapStringToOb 클래스
ms.date: 11/04/2016
f1_keywords:
- CMapStringToOb
- AFXCOLL/CMapStringToOb
- AFXCOLL/CMapStringToOb::CMapStringToOb
- AFXCOLL/CMapStringToOb::GetCount
- AFXCOLL/CMapStringToOb::GetHashTableSize
- AFXCOLL/CMapStringToOb::GetNextAssoc
- AFXCOLL/CMapStringToOb::GetSize
- AFXCOLL/CMapStringToOb::GetStartPosition
- AFXCOLL/CMapStringToOb::HashKey
- AFXCOLL/CMapStringToOb::InitHashTable
- AFXCOLL/CMapStringToOb::IsEmpty
- AFXCOLL/CMapStringToOb::Lookup
- AFXCOLL/CMapStringToOb::LookupKey
- AFXCOLL/CMapStringToOb::RemoveAll
- AFXCOLL/CMapStringToOb::RemoveKey
- AFXCOLL/CMapStringToOb::SetAt
helpviewer_keywords:
- CMapStringToOb [MFC], CMapStringToOb
- CMapStringToOb [MFC], GetCount
- CMapStringToOb [MFC], GetHashTableSize
- CMapStringToOb [MFC], GetNextAssoc
- CMapStringToOb [MFC], GetSize
- CMapStringToOb [MFC], GetStartPosition
- CMapStringToOb [MFC], HashKey
- CMapStringToOb [MFC], InitHashTable
- CMapStringToOb [MFC], IsEmpty
- CMapStringToOb [MFC], Lookup
- CMapStringToOb [MFC], LookupKey
- CMapStringToOb [MFC], RemoveAll
- CMapStringToOb [MFC], RemoveKey
- CMapStringToOb [MFC], SetAt
ms.assetid: 09653980-b885-4f3a-8594-0aeb7f94c601
ms.openlocfilehash: b56e9052533269ba62d248312f07ac16db71bf4a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62253051"
---
# <a name="cmapstringtoob-class"></a>CMapStringToOb 클래스

고유한 `CString` 개체를 `CObject` 포인터에 매핑하는 사전 컬렉션 클래스입니다.

## <a name="syntax"></a>구문

```
class CMapStringToOb : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMapStringToOb::CMapStringToOb](#cmapstringtoob)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMapStringToOb::GetCount](#getcount)|이 map에서 요소 수를 반환합니다.|
|[CMapStringToOb::GetHashTableSize](#gethashtablesize)|현재 해시 테이블에 있는 요소 수를 결정합니다.|
|[CMapStringToOb::GetNextAssoc](#getnextassoc)|반복에 대 한 다음 요소를 가져옵니다.|
|[CMapStringToOb::GetSize](#getsize)|이 map에서 요소 수를 반환합니다.|
|[CMapStringToOb::GetStartPosition](#getstartposition)|첫 번째 요소의 위치를 반환 합니다.|
|[CMapStringToOb::HashKey](#hashkey)|지정된 된 키의 해시 값을 계산합니다.|
|[CMapStringToOb::InitHashTable](#inithashtable)|해시 테이블을 초기화합니다.|
|[CMapStringToOb::IsEmpty](#isempty)|빈 맵을 조건 (요소 없음)에 대해 테스트 합니다.|
|[CMapStringToOb::Lookup](#lookup)|Void 포인터 키를 기반으로 void 포인터를 조회 합니다. 이것이 가리키는 엔터티가 아닌 포인터 값은 키 비교에 사용 됩니다.|
|[CMapStringToOb::LookupKey](#lookupkey)|지정된 된 키 값을 사용 하 여 연결 된 키에 대 한 참조를 반환 합니다.|
|[CMapStringToOb::RemoveAll](#removeall)|이 맵에서 모든 요소를 제거합니다.|
|[CMapStringToOb::RemoveKey](#removekey)|키로 지정 된 요소를 제거 합니다.|
|[CMapStringToOb::SetAt](#setat)|맵에; 요소를 삽입합니다. 일치 하는 키가 있을 경우 기존 요소를 바꿉니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CMapStringToOb::operator \[ \]](#operator_at)|Map에 요소를 삽입-에 대 한 연산자 대체 `SetAt`합니다.|

## <a name="remarks"></a>설명

삽입 한 후는 `CString` -  `CObject*` 쌍 (요소)를 map으로 효율적으로 검색 하거나 삭제할 수는 문자열을 사용 하 여 쌍 또는 `CString` 키 값입니다. 또한 map의 모든 요소를 반복할 수 있습니다.

위치 형식의 변수는 모든 지도 변형에 대 한 대체 항목 액세스에 사용 됩니다. 항목을 "기억" 하 고 맵을 통해 반복 하는 위치를 사용할 수 있습니다. 이 반복은 키 값;으로 순차적는 생각 그것이 아니야. 검색 된 요소의 시퀀스를 결정 되지 않습니다.

`CMapStringToOb`는 serialization 및 요소 덤프를 지원하기 위해 `IMPLEMENT_SERIAL` 매크로를 통합합니다. 지도 오버 로드 된 삽입을 사용 하 여 보관 파일에 저장 되는 경우 각 요소가 차례로 serialize 됩니다 ( **<<**) 연산자 또는 `Serialize` 멤버 함수입니다.

맵에서 개별 요소의 진단 덤프 해야 하는 경우 (합니다 `CString` 값 및 `CObject` 내용), 덤프 컨텍스트의 수준을 1 이상으로 설정 해야 합니다.

경우는 `CMapStringToOb` 개체를 삭제 하거나 해당 요소를 제거 하는 경우는 `CString` 개체 및 `CObject` 포인터 제거 됩니다. 참조 하는 개체는 `CObject` 포인터 소멸 되지 않습니다.

Map 클래스를 파생 목록 파생 하는 것과 비슷합니다. 문서를 참조 하세요 [컬렉션](../../mfc/collections.md) 예시의 특수 한 용도의 목록 클래스를 파생 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CMapStringToOb`

## <a name="requirements"></a>요구 사항

**헤더:** afxcoll.h

##  <a name="cmapstringtoob"></a>  CMapStringToOb::CMapStringToOb

빈 생성 `CString`-에- `CObject*` 맵.

```
CMapStringToOb(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>매개 변수

*nBlockSize*<br/>
맵을 확장 하는 것에 대 한 메모리 할당 세분성을 지정 합니다.

### <a name="remarks"></a>설명

메모리 단위에서 할당 되는 지도 늘어나면 *nBlockSize* 항목입니다.

다음 표에서 다른 멤버와 유사한 함수 `CMapStringToOb:: CMapStringToOb`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**CMapPtrToPtr( INT_PTR** `nBlockSize` **= 10 );**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**CMapPtrToWord( INT_PTR** `nBlockSize` **= 10 );**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**CMapStringToPtr( INT_PTR** `nBlockSize` **= 10 );**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**CMapStringToString( INT_PTR** `nBlockSize` **= 10 );**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CMapWordToOb( INT_PTR** `nBlockSize` **= 10 );**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**MapWordToPtr( INT_PTR** `nBlockSize` **= 10 );**|

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#63](../../mfc/codesnippet/cpp/cmapstringtoob-class_1.cpp)]

참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 모든 컬렉션 예제에서 사용 되는 클래스입니다.

##  <a name="getcount"></a>  CMapStringToOb::GetCount

지도에 있는 요소의 수를 결정 합니다.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>반환 값

이 맵에서 요소의 수입니다.

### <a name="remarks"></a>설명

다음 표에서 다른 멤버와 유사한 함수 `CMapStringToOb::GetCount`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**INT_PTR GetCount( ) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**INT_PTR GetCount( ) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**INT_PTR GetCount( ) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**INT_PTR GetCount( ) const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**INT_PTR GetCount( ) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**INT_PTR GetCount( ) const;**|

### <a name="example"></a>예제

참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 모든 컬렉션 예제에서 사용 되는 클래스입니다.

[!code-cpp[NVC_MFCCollections#64](../../mfc/codesnippet/cpp/cmapstringtoob-class_2.cpp)]

##  <a name="gethashtablesize"></a>  CMapStringToOb::GetHashTableSize

현재 해시 테이블에 있는 요소 수를 결정합니다.

```
UINT GetHashTableSize() const;
```

### <a name="return-value"></a>반환 값

해시 테이블에 있는 요소의 수를 반환합니다.

### <a name="remarks"></a>설명

다음 표에서 다른 멤버와 유사한 함수 `CMapStringToOb::GetHashTableSize`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**UINT GetHashTableSize( ) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**UINT GetHashTableSize( ) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**UINT GetHashTableSize( ) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**UINT GetHashTableSize( ) const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**UINT GetHashTableSize( ) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**UINT GetHashTableSize( ) const;**|

##  <a name="getnextassoc"></a>  CMapStringToOb::GetNextAssoc

있는 지도 요소를 검색 *rNextPosition*를 업데이트 한 다음 *rNextPosition* 다음 지도 요소를 가리킵니다.

```
void GetNextAssoc(
    POSITION& rNextPosition,
    CString& rKey,
    CObject*& rValue) const;
```

### <a name="parameters"></a>매개 변수

*rNextPosition*<br/>
이전 반환한 위치 값에 대 한 참조를 지정 `GetNextAssoc` 또는 `GetStartPosition` 호출 합니다.

*rKey*<br/>
검색 요소 (문자열)는 반환 된 키를 지정합니다.

*rValue*<br/>
검색된 된 요소 반환 된 값을 지정 합니다 (한 `CObject` 포인터). 이 매개 변수에 대 한 자세한 설명을 참조 하세요.

### <a name="remarks"></a>설명

이 함수는 map의 모든 요소를 반복 하는 데 가장 유용 합니다. 않음을 유의 위치 순서 반드시 키 값 시퀀스와 동일 합니다.

검색 된 요소가 있으면 맵의 마지막으로 다음의 새 값 *rNextPosition* NULL로 설정 됩니다.

에 대 한 합니다 *rValue* 매개 변수를 해당 개체 형식에 캐스팅 해야 **CObject\*&** 는 컴파일러의 필요를 다음 예제에서와 같이:

[!code-cpp[NVC_MFCCollections#65](../../mfc/codesnippet/cpp/cmapstringtoob-class_3.cpp)]

이는 적용 되지 않습니다 `GetNextAssoc` 템플릿을 기반으로 하는 지도 대 한 합니다.

다음 표에서 다른 멤버와 유사한 함수 `CMapStringToOb::GetNextAssoc`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void GetNextAssoc( POSITION&** *rNextPosition* **, void\*&** *rKey* **, void\*&** *rValue* **) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**GetNextAssoc void (위치 &** *rNextPosition* **, void\* &**  *rKey* **, 단어 &** *rValue* **) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void GetNextAssoc( POSITION&** *rNextPosition* **, CString&** *rKey* **, void\*&** *rValue* **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**GetNextAssoc void (위치 &** *rNextPosition* **, CString &** *rKey* **, CString &** *rValue* **) const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**GetNextAssoc void (위치 &** *rNextPosition* **, 단어 &** *rKey* **, CObject\* &**  *rValue* **) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void GetNextAssoc( POSITION&** *rNextPosition* **, WORD&** *rKey* **, void\*&** *rValue* **) const;**|

### <a name="example"></a>예제

참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 모든 컬렉션 예제에서 사용 되는 클래스입니다.

[!code-cpp[NVC_MFCCollections#66](../../mfc/codesnippet/cpp/cmapstringtoob-class_4.cpp)]

이 프로그램의 결과 아래와 같습니다.

```Output
Lisa : a CAge at $4724 11
Marge : a CAge at $47A8 35
Homer : a CAge at $4766 36
Bart : a CAge at $45D4 13
```

##  <a name="getsize"></a>  CMapStringToOb::GetSize

지도 요소 수를 반환 합니다.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>반환 값

지도 있는 항목의 수입니다.

### <a name="remarks"></a>설명

Map의 요소 수를 검색 하려면이 메서드를 호출 합니다.

다음 표에서 다른 멤버와 유사한 함수 `CMapStringToOb::GetSize`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**INT_PTR GetSize( ) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**INT_PTR GetSize( ) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**INT_PTR GetSize( ) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**INT_PTR GetSize( ) const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**INT_PTR GetSize( ) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**INT_PTR GetSize( ) const;**|

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#67](../../mfc/codesnippet/cpp/cmapstringtoob-class_5.cpp)]

##  <a name="getstartposition"></a>  CMapStringToOb::GetStartPosition

맵 반복을 전달할 수 있는 위치 값을 반환 하 여 시작을 `GetNextAssoc` 호출 합니다.

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>반환 값

가 맵을 반복 시작 위치를 지정 하는 위치 값 또는 맵이 비어 있으면 NULL입니다.

### <a name="remarks"></a>설명

반복 시퀀스 예측 가능한; 아닙니다. 따라서 "첫 번째 요소를 맵" 특별 한 의미가 없습니다.

다음 표에서 다른 멤버와 유사한 함수 `CMapStringToOb::GetStartPosition`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**Const; GetStartPosition ()를 배치 합니다.**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Const; GetStartPosition ()를 배치 합니다.**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**Const; GetStartPosition ()를 배치 합니다.**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**Const; GetStartPosition ()를 배치 합니다.**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**Const; GetStartPosition ()를 배치 합니다.**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**Const; GetStartPosition ()를 배치 합니다.**|

### <a name="example"></a>예제

예를 참조 하세요 [CMapStringToOb::GetNextAssoc](#getnextassoc)합니다.

##  <a name="hashkey"></a>  CMapStringToOb::HashKey

지정된 된 키의 해시 값을 계산합니다.

```
UINT HashKey(LPCTSTR key) const;
```

### <a name="parameters"></a>매개 변수

*key*<br/>
해시 값 계산 해야 하는 키입니다.

### <a name="return-value"></a>반환 값

키의 해시 값

### <a name="remarks"></a>설명

다음 표에서 다른 멤버와 유사한 함수 `CMapStringToOb::HashKey`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**UINT HashKey (void** <strong>\*</strong> `key` **) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**UINT HashKey (void** <strong>\*</strong> `key` **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**UINT HashKey (LPCTSTR** `key` **) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**UINT HashKey (LPCTSTR** `key` **) const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**UINT HashKey (단어** `key` **) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**UINT HashKey (단어** `key` **) const;**|

##  <a name="inithashtable"></a>  CMapStringToOb::InitHashTable

해시 테이블을 초기화합니다.

```
void InitHashTable(
    UINT hashSize,
    BOOL bAllocNow = TRUE);
```

### <a name="parameters"></a>매개 변수

*hashSize*<br/>
해시 테이블에 있는 엔트리의 수입니다.

*bAllocNow*<br/>
TRUE 인 경우 초기화 시 해시 테이블을 할당 합니다. 그렇지 않은 경우 테이블은 필요할 때 할당 됩니다.

### <a name="remarks"></a>설명

최상의 성능을 얻으려면 해시 테이블 크기에는 소수 여야 합니다. 충돌을 최소화 하려면 크기 있어야 약 20% 최대 예상된 데이터 집합 보다 큰 합니다.

다음 표에서 다른 멤버와 유사한 함수 `CMapStringToOb::InitHashTable`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void InitHashTable( UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE );**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void InitHashTable( UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE );**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void InitHashTable( UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE );**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void InitHashTable( UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE );**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void InitHashTable( UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE );**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void InitHashTable( UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE );**|

##  <a name="isempty"></a>  CMapStringToOb::IsEmpty

Map이 비어 있는지 여부를 결정 합니다.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>반환 값

이 0이 아닌 지도 요소가 없는. 그렇지 않으면 0입니다.

### <a name="example"></a>예제

예를 참조 하세요 [RemoveAll](#removeall)합니다.

### <a name="remarks"></a>설명

다음 표에서 다른 멤버와 유사한 함수 **CMapStringToOb:: IsEmpty**.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL IsEmpty( ) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL IsEmpty( ) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL IsEmpty( ) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL IsEmpty( ) const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL IsEmpty( ) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL IsEmpty( ) const;**|

##  <a name="lookup"></a>  CMapStringToOb::Lookup

반환 된 `CObject` 기반 포인터는 `CString` 값.

```
BOOL Lookup(
    LPCTSTR key,
    CObject*& rValue) const;
```

### <a name="parameters"></a>매개 변수

*key*<br/>
조회할 수 요소를 식별 하는 문자열 키를 지정 합니다.

*rValue*<br/>
찾는 구성 요소에서 반환된 된 값을 지정합니다.

### <a name="return-value"></a>반환 값

0이 아닌 요소를 찾을 수 있습니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`Lookup` 해시 알고리즘을 사용 하 여 신속 하 게 정확 하 게 일치 하는 키를 사용 하 여 지도 요소를 찾습니다 ( `CString` 값).

다음 표에서 다른 멤버와 유사한 함수 `CMapStringToOb::LookUp`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL 조회 (void** <strong>\*</strong> `key` **, void\* &**  `rValue` **) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL 조회 (void** <strong>\*</strong> `key` **, 단어 &** `rValue` **) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL 조회 (LPCTSTR** `key` **, void\* &**  `rValue` **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL 조회 (LPCTSTR** `key` **, CString &** `rValue` **) const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL 조회 (단어** `key` **, CObject\* &**  `rValue` **) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL 조회 (단어** `key` **, void\* &**  `rValue` **) const;**|

### <a name="example"></a>예제

참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 모든 컬렉션 예제에서 사용 되는 클래스입니다.

[!code-cpp[NVC_MFCCollections#68](../../mfc/codesnippet/cpp/cmapstringtoob-class_6.cpp)]

##  <a name="lookupkey"></a>  CMapStringToOb::LookupKey

지정된 된 키 값을 사용 하 여 연결 된 키에 대 한 참조를 반환 합니다.

```
BOOL LookupKey(
    LPCTSTR key,
    LPCTSTR& rKey) const;
```

### <a name="parameters"></a>매개 변수

*key*<br/>
조회할 수 요소를 식별 하는 문자열 키를 지정 합니다.

*rKey*<br/>
연결 된 키에 대 한 참조입니다.

### <a name="return-value"></a>반환 값

0이 아닌 키를 찾을 수 있습니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

키에 대 한 참조를 사용 하 여 연결된 된 요소 맵에서 제거 된 후 사용 하는 경우 또는 맵을 소멸 된 후에 안전 하지 않습니다.

다음 표에서 다른 멤버와 유사한 함수 `CMapStringToOb:: LookupKey`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL LookupKey (LPCTSTR** `key` **, LPCTSTR &** `rKey` **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL LookupKey (LPCTSTR** `key` **, LPCTSTR &** `rKey` **) const;**|

##  <a name="operator_at"></a>  CMapStringToOb::operator [ ]

대체 하는 편리한는 `SetAt` 멤버 함수입니다.

```
CObject*& operator[ ](lpctstr key);
```

### <a name="return-value"></a>반환 값

에 대 한 포인터에 대 한 참조를 `CObject` 개체 이거나 맵이 비어 있으면 NULL 또는 *키* 범위를 벗어났습니다.

### <a name="remarks"></a>설명

따라서 대입문 (l-value)의 왼쪽에만 사용할 수 있습니다. 지정된 된 키를 사용 하 여 지도 요소가 이면 새 요소가 만들어집니다.

경우 없음 "오른쪽" (r-value)이이 연산자에 해당 맵의 키를 찾을 수 없습니다 가능성이 있기 때문에 사용 된 `Lookup` 요소 검색에 대 한 멤버 함수입니다.

다음 표에서 다른 멤버와 유사한 함수 `CMapStringToOb::operator []`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|<strong>void\*& operator\[](void \*</strong> `key` **\);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**단어 & 연산자\[] (void** <strong>\*</strong> `key`  **\);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void\*& operator\[](lpctstr** `key` **\);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**CString & 연산자\[] (lpctstr** `key`  **\);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CObject\*& operator\[](word** `key` **\);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void\*& operator\[](word** `key` **\);**|

### <a name="example"></a>예제

참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 모든 컬렉션 예제에서 사용 되는 클래스입니다.

[!code-cpp[NVC_MFCCollections#72](../../mfc/codesnippet/cpp/cmapstringtoob-class_7.cpp)]

이 프로그램의 결과 아래와 같습니다.

```Output
Operator [] example: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $4A02 11
[Bart] = a CAge at $497E 13
```

##  <a name="removeall"></a>  CMapStringToOb::RemoveAll

이 맵에서 모든 요소를 제거 하 고 삭제를 `CString` 개체 키입니다.

```
void RemoveAll();
```

### <a name="remarks"></a>설명

`CObject` 각 키에서 참조 하는 개체는 소멸 되지 않습니다. 합니다 `RemoveAll` 함수를 확인 하지 않습니다는 참조 된 경우 메모리 누수가 발생할 수 있습니다 `CObject` 개체는 삭제 됩니다.

맵이 비어 이미 경우 함수가 제대로 작동 합니다.

다음 표에서 다른 멤버와 유사한 함수 `CMapStringToOb::RemoveAll`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void RemoveAll( );**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void RemoveAll( );**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void RemoveAll( );**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void RemoveAll( );**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void RemoveAll( );**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void RemoveAll( );**|

### <a name="example"></a>예제

참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 모든 컬렉션 예제에서 사용 되는 클래스입니다.

[!code-cpp[NVC_MFCCollections#69](../../mfc/codesnippet/cpp/cmapstringtoob-class_8.cpp)]

##  <a name="removekey"></a>  CMapStringToOb::RemoveKey

제공 된 키;에 해당 하는 맵 항목을 조회 그런 다음 키가 있으면 항목을 제거 합니다.

```
BOOL RemoveKey(LPCTSTR key);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
지도 조회에 사용 되는 문자열을 지정 합니다.

### <a name="return-value"></a>반환 값

0이 아닌 항목을 찾아 제거 했습니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 경우 메모리 누수를 발생할 수 있습니다는 `CObject` 개체가 다른 곳에서 삭제 되지 않습니다.

다음 표에서 다른 멤버와 유사한 함수 `CMapStringToOb::RemoveKey`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL RemoveKey( void** <strong>\*</strong> `key` **);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL RemoveKey( void** <strong>\*</strong> `key` **);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL RemoveKey( LPCTSTR** `key` **);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL RemoveKey( LPCTSTR** `key` **);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL RemoveKey( WORD** `key` **);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL RemoveKey( WORD** `key` **);**|

### <a name="example"></a>예제

참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 모든 컬렉션 예제에서 사용 되는 클래스입니다.

[!code-cpp[NVC_MFCCollections#70](../../mfc/codesnippet/cpp/cmapstringtoob-class_9.cpp)]

이 프로그램의 결과 아래와 같습니다.

```Output
RemoveKey example: A CMapStringToOb with 3 elements
[Marge] = a CAge at $49A0 35
[Homer] = a CAge at $495E 36
[Bart] = a CAge at $4634 13
```

##  <a name="setat"></a>  CMapStringToOb::SetAt

기본 맵에서 요소를 삽입 한다는 의미입니다.

```
void SetAt(
    LPCTSTR key,
    CObject* newValue);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
새 요소의 키 문자열을 지정 합니다.

*newValue*<br/>
지정 된 `CObject` 포인터는 새 요소의 값입니다.

### <a name="remarks"></a>설명

먼저 키를 찾습니다. 키가 있으면 해당 값이 변경 됩니다; 그런 다음 그렇지 않은 경우 새 키-값 요소 생성 됩니다.

다음 표에서 다른 멤버와 유사한 함수 `CMapStringToOb::SetAt`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void SetAt( void** <strong>\*</strong> `key` **, void** <strong>\*</strong> `newValue` **);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void SetAt( void** <strong>\*</strong> `key` **, WORD** `newValue` **);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void SetAt( LPCTSTR** `key` **, void** <strong>\*</strong> `newValue` **);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void SetAt( LPCTSTR** `key` **, LPCTSTR** `newValue` **);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void SetAt( WORD** `key` **, CObject** <strong>\*</strong> `newValue` **);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void SetAt( WORD** `key` **, void** <strong>\*</strong> `newValue` **);**|

### <a name="example"></a>예제

참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 모든 컬렉션 예제에서 사용 되는 클래스입니다.

[!code-cpp[NVC_MFCCollections#71](../../mfc/codesnippet/cpp/cmapstringtoob-class_10.cpp)]

이 프로그램의 결과 아래와 같습니다.

```Output
before Lisa's birthday: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $493C 11
[Bart] = a CAge at $4654 13
after Lisa's birthday: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $49C0 12
[Bart] = a CAge at $4654 13
```

## <a name="see-also"></a>참고자료

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CMapPtrToPtr 클래스](../../mfc/reference/cmapptrtoptr-class.md)<br/>
[CMapPtrToWord 클래스](../../mfc/reference/cmapptrtoword-class.md)<br/>
[CMapStringToPtr 클래스](../../mfc/reference/cmapstringtoptr-class.md)<br/>
[CMapStringToString 클래스](../../mfc/reference/cmapstringtostring-class.md)<br/>
[CMapWordToOb 클래스](../../mfc/reference/cmapwordtoob-class.md)<br/>
[CMapWordToPtr 클래스](../../mfc/reference/cmapwordtoptr-class.md)
