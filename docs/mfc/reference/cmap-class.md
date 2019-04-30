---
title: CMap 클래스
ms.date: 11/04/2016
f1_keywords:
- CMap
- AFXTEMPL/CMap
- AFXTEMPL/CMap::CPair
- AFXTEMPL/CMap::CMap
- AFXTEMPL/CMap::GetCount
- AFXTEMPL/CMap::GetHashTableSize
- AFXTEMPL/CMap::GetNextAssoc
- AFXTEMPL/CMap::GetSize
- AFXTEMPL/CMap::GetStartPosition
- AFXTEMPL/CMap::InitHashTable
- AFXTEMPL/CMap::IsEmpty
- AFXTEMPL/CMap::Lookup
- AFXTEMPL/CMap::PGetFirstAssoc
- AFXTEMPL/CMap::PGetNextAssoc
- AFXTEMPL/CMap::PLookup
- AFXTEMPL/CMap::RemoveAll
- AFXTEMPL/CMap::RemoveKey
- AFXTEMPL/CMap::SetAt
helpviewer_keywords:
- CMap [MFC], CPair
- CMap [MFC], CMap
- CMap [MFC], GetCount
- CMap [MFC], GetHashTableSize
- CMap [MFC], GetNextAssoc
- CMap [MFC], GetSize
- CMap [MFC], GetStartPosition
- CMap [MFC], InitHashTable
- CMap [MFC], IsEmpty
- CMap [MFC], Lookup
- CMap [MFC], PGetFirstAssoc
- CMap [MFC], PGetNextAssoc
- CMap [MFC], PLookup
- CMap [MFC], RemoveAll
- CMap [MFC], RemoveKey
- CMap [MFC], SetAt
ms.assetid: 640a45ab-0993-4def-97ec-42cc78eb10b9
ms.openlocfilehash: 58f9efb19988be8487ec87ce0c63d90ee1a97911
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62296581"
---
# <a name="cmap-class"></a>CMap 클래스

고유 키를 값에 매핑하는 사전 컬렉션 클래스입니다.

## <a name="syntax"></a>구문

```
template<class KEY, class ARG_KEY, class VALUE, class ARG_VALUE>class CMap : public CObject
```

#### <a name="parameters"></a>매개 변수

*KEY*<br/>
지도 키로 사용 되는 개체의 클래스입니다.

*ARG_KEY*<br/>
에 사용 되는 데이터 형식 *키* 인수에 대 한 참조, 대개 *키*합니다.

*VALUE*<br/>
Map에 저장 된 개체의 클래스입니다.

*ARG_VALUE*<br/>
에 사용 되는 데이터 형식 *값* 인수에 대 한 참조, 대개 *값*합니다.

## <a name="members"></a>멤버

### <a name="public-structures"></a>공용 구조체

|이름|설명|
|----------|-----------------|
|[CMap::CPair](#cpair)|키 값과 연결된 된 개체의 값을 포함 하는 중첩 된 구조입니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMap::CMap](#cmap)|키 값에 매핑하는 컬렉션을 생성 합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMap::GetCount](#getcount)|이 map에서 요소 수를 반환합니다.|
|[CMap::GetHashTableSize](#gethashtablesize)|해시 테이블에 있는 요소의 수를 반환합니다.|
|[CMap::GetNextAssoc](#getnextassoc)|반복에 대 한 다음 요소를 가져옵니다.|
|[CMap::GetSize](#getsize)|이 map에서 요소 수를 반환합니다.|
|[CMap::GetStartPosition](#getstartposition)|첫 번째 요소의 위치를 반환 합니다.|
|[CMap::InitHashTable](#inithashtable)|해시 테이블을 초기화 하 고 크기를 지정 합니다.|
|[CMap::IsEmpty](#isempty)|빈 맵을 조건 (요소 없음)에 대해 테스트 합니다.|
|[CMap::Lookup](#lookup)|지정된 된 키에 매핑된 값을 조회 합니다.|
|[CMap::PGetFirstAssoc](#pgetfirstassoc)|첫 번째 요소에 대 한 포인터를 반환합니다.|
|[CMap::PGetNextAssoc](#pgetnextassoc)|반복에 대 한 다음 요소에 대 한 포인터를 가져옵니다.|
|[CMap::PLookup](#plookup)|지정된 된 값을 일치 하는 값을 갖는 키에 대 한 포인터를 반환 합니다.|
|[CMap::RemoveAll](#removeall)|이 맵에서 모든 요소를 제거합니다.|
|[CMap::RemoveKey](#removekey)|키로 지정 된 요소를 제거 합니다.|
|[CMap::SetAt](#setat)|맵에; 요소를 삽입합니다. 일치 하는 키가 있을 경우 기존 요소를 바꿉니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CMap::operator \[ \]](#operator_at)|Map에 요소를 삽입-에 대 한 연산자 대체 `SetAt`합니다.|

## <a name="remarks"></a>설명

Map에는 키-값 쌍 (요소)가 삽입 되 면 효율적으로 검색 하거나 액세스 키를 사용 하 여 쌍을 삭제할 수 있습니다. 또한 map의 모든 요소를 반복할 수 있습니다.

위치 형식의 변수는 항목에 대 한 대체 액세스에 사용 됩니다. 항목을 "기억" 하 고 맵을 통해 반복 하는 위치를 사용할 수 있습니다. 이 반복은 키 값;으로 순차적는 생각 그것이 아니야. 검색 된 요소의 시퀀스를 결정 되지 않습니다.

전역 도우미 함수는이 클래스 호출의 특정 멤버 함수는 대부분의 사용에 대 한 사용자 지정 되어야 합니다는 `CMap` 클래스입니다. 참조 [컬렉션 클래스 도우미](../../mfc/reference/collection-class-helpers.md) 의 매크로 및 전역 섹션에는 **MFC 참조**합니다.

`CMap` 재정의 [cobject:: Serialize](../../mfc/reference/cobject-class.md#serialize) serialization 및 요소 덤프를 지원 하도록 합니다. 맵을 사용 하 여 보관 파일에 저장 되는 경우 `Serialize`, 각 지도 요소 차례로 serialize 됩니다. 기본 구현 된 `SerializeElements` 도우미 함수 비트 쓰기를 수행 합니다. 파생 된 포인터 컬렉션 항목의 serialization에 대 한 정보에 대 한 `CObject` 다른 사용자 정의 형식 참조 또는 [방법: 형식이 안전한 컬렉션 만들기](../../mfc/how-to-make-a-type-safe-collection.md)합니다.

진단 덤프 (키 및 값) 구조의 개별 요소에 필요한 경우 덤프 컨텍스트 깊이 1 이상으로 설정 해야 합니다.

경우는 `CMap` 개체를 삭제 하거나 해당 요소를 제거 하 고, 키 및 값 제거 됩니다.

Map 클래스를 파생 목록 파생 하는 것과 비슷합니다. 문서를 참조 하세요 [컬렉션](../../mfc/collections.md) 예시의 특수 한 용도의 목록 클래스를 파생 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CMap`

## <a name="requirements"></a>요구 사항

**헤더:** afxtempl.h

##  <a name="cmap"></a>  CMap::CMap

빈 맵을 생성합니다.

```
CMap(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>매개 변수

*nBlockSize*<br/>
맵을 확장 하는 것에 대 한 메모리 할당 세분성을 지정 합니다.

### <a name="remarks"></a>설명

메모리 단위에서 할당 되는 지도 늘어나면 *nBlockSize* 항목입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#56](../../mfc/codesnippet/cpp/cmap-class_1.cpp)]

##  <a name="cpair"></a>  CMap::CPair

키 값과 연결된 된 개체의 값을 포함합니다.

### <a name="remarks"></a>설명

이 클래스 내에서 중첩된 구조 [CMap](../../mfc/reference/cmap-class.md)합니다.

구조는 두 가지 필드로 구성 됩니다.

- `key` 실제 값 키 형식입니다.

- `value` 연결된 된 개체의 값입니다.

반환 값을 저장 하 되 [CMap::PLookup](#plookup)를 [CMap::PGetFirstAssoc](#pgetfirstassoc), 및 [CMap::PGetNextAssoc](#pgetnextassoc)합니다.

### <a name="example"></a>예제

사용 예에 대 한 예제를 참조 하세요 [CMap::PLookup](#plookup)합니다.

##  <a name="getcount"></a>  CMap::GetCount

Map의 요소 수를 검색 합니다.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>반환 값

요소의 수입니다.

### <a name="example"></a>예제

예를 참조 하세요 [CMap::Lookup](#lookup)합니다.

##  <a name="gethashtablesize"></a>  CMap::GetHashTableSize

맵에 대 한 해시 테이블에 있는 요소의 수를 결정합니다.

```
UINT GetHashTableSize() const;
```

### <a name="return-value"></a>반환 값

해시 테이블에 있는 요소의 수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#57](../../mfc/codesnippet/cpp/cmap-class_2.cpp)]

##  <a name="getnextassoc"></a>  CMap::GetNextAssoc

있는 지도 요소를 검색 `rNextPosition`, 다음 업데이트 `rNextPosition` 다음 지도 요소를 가리킵니다.

```
void GetNextAssoc(
    POSITION& rNextPosition,
    KEY& rKey,
    VALUE& rValue) const;
```

### <a name="parameters"></a>매개 변수

*rNextPosition*<br/>
이전 반환한 위치 값에 대 한 참조를 지정 `GetNextAssoc` 또는 `GetStartPosition` 호출 합니다.

*KEY*<br/>
템플릿 매개 변수 맵의 키의 형식을 지정 합니다.

*rKey*<br/>
검색 된 요소는 반환 된 키를 지정합니다.

*VALUE*<br/>
템플릿 매개 변수 맵의 값의 형식을 지정 합니다.

*rValue*<br/>
검색된 된 요소 반환 된 값을 지정합니다.

### <a name="remarks"></a>설명

이 함수는 map의 모든 요소를 반복 하는 데 가장 유용 합니다. 않음을 유의 위치 순서 반드시 키 값 시퀀스와 동일 합니다.

검색 된 요소가 있으면 맵의 마지막으로 다음의 새 값 *rNextPosition* NULL로 설정 됩니다.

### <a name="example"></a>예제

예를 참조 하세요 [CMap::SetAt](#setat)합니다.

##  <a name="getsize"></a>  CMap::GetSize

지도 요소 수를 반환 합니다.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>반환 값

지도 있는 항목의 수입니다.

### <a name="remarks"></a>설명

Map의 요소 수를 검색 하려면이 메서드를 호출 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]

##  <a name="getstartposition"></a>  CMap::GetStartPosition

맵 반복을 전달할 수 있는 위치 값을 반환 하 여 시작을 `GetNextAssoc` 호출 합니다.

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>반환 값

가 맵을 반복 시작 위치를 지정 하는 위치 값 또는 맵이 비어 있으면 NULL입니다.

### <a name="remarks"></a>설명

반복 시퀀스 예측 가능한; 아닙니다. 따라서 "첫 번째 요소를 맵" 특별 한 의미가 없습니다.

### <a name="example"></a>예제

예를 참조 하세요 [CMap::SetAt](#setat)합니다.

##  <a name="inithashtable"></a>  CMap::InitHashTable

해시 테이블을 초기화합니다.

```
void InitHashTable(UINT hashSize, BOOL  bAllocNow = TRUE);
```

### <a name="parameters"></a>매개 변수

*hashSize*<br/>
해시 테이블에 있는 엔트리의 수입니다.

*bAllocNow*<br/>
TRUE 인 경우 초기화 시 해시 테이블을 할당 합니다. 그렇지 않은 경우 테이블은 필요할 때 할당 됩니다.

### <a name="remarks"></a>설명

최상의 성능을 얻으려면 해시 테이블 크기에는 소수 여야 합니다. 충돌을 최소화 하려면 크기 있어야 약 20% 최대 예상된 데이터 집합 보다 큰 합니다.

### <a name="example"></a>예제

예를 참조 하세요 [CMap::Lookup](#lookup)합니다.

##  <a name="isempty"></a>  CMap::IsEmpty

Map이 비어 있는지 여부를 결정 합니다.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>반환 값

이 0이 아닌 지도 요소가 없는. 그렇지 않으면 0입니다.

### <a name="example"></a>예제

예를 참조 하세요 [CMap::RemoveAll](#removeall)합니다.

##  <a name="lookup"></a>  CMap::Lookup

지정된 된 키에 매핑된 값을 조회 합니다.

```
BOOL Lookup(ARG_KEY key, VALUE& rValue) const;
```

### <a name="parameters"></a>매개 변수

*ARG_KEY*<br/>
템플릿 매개 변수 형식을 지정 하는 *키* 값입니다.

*key*<br/>
조회 요소를 식별 하는 키를 지정 합니다.

*VALUE*<br/>
조회할 수 값의 형식을 지정 합니다.

*rValue*<br/>
조회 값을 받습니다.

### <a name="return-value"></a>반환 값

0이 아닌 요소를 찾을 수 있습니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`Lookup` 해시 알고리즘을를 사용 하 여 신속 하 게 정확 하 게 지정된 된 키를 일치 시키는 키를 사용 하 여 지도 요소를 찾습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]

##  <a name="operator_at"></a>  CMap::operator [ ]

대체 하는 편리한는 `SetAt` 멤버 함수입니다.

```
VALUE& operator[](arg_key key);
```

### <a name="parameters"></a>매개 변수

*VALUE*<br/>
템플릿 매개 변수를 지도 값의 형식을 지정 합니다.

*ARG_KEY*<br/>
템플릿 매개 변수를 키 값의 형식을 지정 합니다.

*key*<br/>
지도에서 값을 검색 하는 데 사용 된 키입니다.

### <a name="remarks"></a>설명

따라서 대입문 (l-value)의 왼쪽에만 사용할 수 있습니다. 지정된 된 키를 사용 하 여 지도 요소가 이면 새 요소가 만들어집니다.

경우 없음 "오른쪽" (r-value)이이 연산자에 해당 맵의 키를 찾을 수 없습니다 가능성이 있기 때문에 사용 된 `Lookup` 요소 검색에 대 한 멤버 함수입니다.

### <a name="example"></a>예제

예를 참조 하세요 [CMap::Lookup](#lookup)합니다.

##  <a name="pgetfirstassoc"></a>  CMap::PGetFirstAssoc

지도 개체의 첫 번째 항목을 반환합니다.

```
const CPair* PGetFirstAssoc() const;
CPair* PGetFirstAssoc();
```

### <a name="return-value"></a>반환 값

map에서 첫 번째 항목에 대 한 포인터 참조 [CMap::CPair](#cpair)합니다. 지도 항목이 없는 경우 값은 NULL입니다.

### <a name="remarks"></a>설명

Map 개체의 첫 번째 요소에 대 한 포인터를 반환 하려면이 함수를 호출 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#59](../../mfc/codesnippet/cpp/cmap-class_4.cpp)]

##  <a name="pgetnextassoc"></a>  CMap::PGetNextAssoc

지도 요소를 가리키는 검색 *pAssocRec*합니다.

```
const CPair *PGetNextAssoc(const CPair* pAssocRet) const;

CPair *PGetNextAssoc(const CPair* pAssocRet);
```

### <a name="parameters"></a>매개 변수

*pAssocRet*<br/>
이전 반환한 맵 항목을 가리키는 [PGetNextAssoc](#pgetnextassoc) 하거나 [CMap::PGetFirstAssoc](#pgetfirstassoc) 호출 합니다.

### <a name="return-value"></a>반환 값

지도;에서 다음 항목에 대 한 포인터 참조 [CMap::CPair](#cpair)합니다. Map에서 마지막 요소 이면 값은 NULL입니다.

### <a name="remarks"></a>설명

Map의 모든 요소를 반복 하려면이 메서드를 호출 합니다. 호출 하 여 첫 번째 요소를 검색할 `PGetFirstAssoc` 다음에 대 한 연속 호출을 사용 하 여 map을 반복 하 고 `PGetNextAssoc`입니다.

### <a name="example"></a>예제

예를 참조 하세요 [CMap::PGetFirstAssoc](#pgetfirstassoc)합니다.

##  <a name="plookup"></a>  CMap::PLookup

지정된 된 키에 매핑된 값을 찾습니다.

```
const CPair* PLookup(ARG_KEY key) const;
CPair* PLookup(ARG_KEY key);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
검색할 요소의 키입니다.

### <a name="return-value"></a>반환 값

키 구조에 대 한 포인터 참조 [CMap::CPair](#cpair)합니다. 일치 하는 항목이 없으면 `CMap::PLookup` NULL을 반환 합니다.

### <a name="remarks"></a>설명

지도 요소를 정확 하 게 지정된 된 키와 일치 하는 키를 검색 하려면이 메서드를 호출 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#60](../../mfc/codesnippet/cpp/cmap-class_5.cpp)]

##  <a name="removeall"></a>  CMap::RemoveAll

전역 도우미 함수를 호출 하 여 모든 값이 맵에서 제거 `DestructElements`합니다.

```
void RemoveAll();
```

### <a name="remarks"></a>설명

맵이 비어 이미 경우 함수가 제대로 작동 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#61](../../mfc/codesnippet/cpp/cmap-class_6.cpp)]

##  <a name="removekey"></a>  CMap::RemoveKey

제공 된 키;에 해당 하는 맵 항목을 조회 그런 다음 키가 있으면 항목을 제거 합니다.

```
BOOL RemoveKey(ARG_KEY key);
```

### <a name="parameters"></a>매개 변수

*ARG_KEY*<br/>
템플릿 매개 변수는 키의 형식을 지정 합니다.

*key*<br/>
제거할 요소의 키입니다.

### <a name="return-value"></a>반환 값

0이 아닌 항목을 찾아 제거 했습니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`DestructElements` 도우미 함수는 항목을 제거 하는 데 사용 됩니다.

### <a name="example"></a>예제

예를 참조 하세요 [CMap::SetAt](#setat)합니다.

##  <a name="setat"></a>  CMap::SetAt

기본 맵에서 요소를 삽입 한다는 의미입니다.

```
void SetAt(ARG_KEY key, ARG_VALUE newValue);
```

### <a name="parameters"></a>매개 변수

*ARG_KEY*<br/>
템플릿 매개 변수 형식을 지정 하는 *키* 매개 변수입니다.

*key*<br/>
새 요소의 키를 지정합니다.

*ARG_VALUE*<br/>
템플릿 매개 변수 형식을 지정 하는 *newValue* 매개 변수입니다.

*newValue*<br/>
새 요소의 값을 지정합니다.

### <a name="remarks"></a>설명

먼저 키를 찾습니다. 키가 있으면 해당 값이 변경 됩니다; 그런 다음 그렇지 않은 경우 새 키-값 쌍이 생성 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#62](../../mfc/codesnippet/cpp/cmap-class_7.cpp)]

## <a name="see-also"></a>참고자료

[MFC 샘플 수집](../../overview/visual-cpp-samples.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
