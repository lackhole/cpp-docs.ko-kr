---
title: CAtlArray 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlArray
- ATLCOLL/ATL::CAtlArray
- ATLCOLL/ATL::Add
- ATLCOLL/ATL::Append
- ATLCOLL/ATL::AssertValid
- ATLCOLL/ATL::Copy
- ATLCOLL/ATL::FreeExtra
- ATLCOLL/ATL::GetAt
- ATLCOLL/ATL::GetCount
- ATLCOLL/ATL::GetData
- ATLCOLL/ATL::InsertArrayAt
- ATLCOLL/ATL::InsertAt
- ATLCOLL/ATL::IsEmpty
- ATLCOLL/ATL::RemoveAll
- ATLCOLL/ATL::RemoveAt
- ATLCOLL/ATL::SetAt
- ATLCOLL/ATL::SetAtGrow
- ATLCOLL/ATL::SetCount
- ATLCOLL/ATL::INARGTYPE
- ATLCOLL/ATL::OUTARGTYPE
helpviewer_keywords:
- CAtlArray class
ms.assetid: 0b503aa8-2357-40af-a326-6654bf1da098
ms.openlocfilehash: 6a0b83f722d1b616e9c10713646d337f9cb090a4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260846"
---
# <a name="catlarray-class"></a>CAtlArray 클래스

이 클래스는 배열 개체를 구현합니다.

## <a name="syntax"></a>구문

```
template<typename E, class ETraits = CElementTraits<E>>
class CAtlArray
```

#### <a name="parameters"></a>매개 변수

*E*<br/>
배열에 저장할 데이터의 형식입니다.

*ETraits*<br/>
요소 이동 하거나 복사 하는 데 사용 되는 코드입니다.

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[추가](#add)|배열 개체에 요소를 추가 하려면이 메서드를 호출 합니다.|
|[추가](#append)|한 배열의 내용을 다른 끝에 추가 하려면이 메서드를 호출 합니다.|
|[AssertValid](#assertvalid)|배열 개체에 유효한 지 확인 하려면이 메서드를 호출 합니다.|
|[CAtlArray](#catlarray)|생성자입니다.|
|[~CAtlArray](#dtor)|소멸자입니다.|
|[복사](#copy)|다른 한 배열의 요소를 복사 하려면이 메서드를 호출 합니다.|
|[FreeExtra](#freeextra)|배열에서 빈 요소를 제거 하려면이 메서드를 호출 합니다.|
|[GetAt](#getat)|배열 개체의 단일 요소를 검색 하려면이 메서드를 호출 합니다.|
|[GetCount](#getcount)|배열에 저장 된 요소의 수를 반환 하려면이 메서드를 호출 합니다.|
|[GetData](#getdata)|배열의 첫 번째 요소에 대 한 포인터를 반환 하려면이 메서드를 호출 합니다.|
|[InsertArrayAt](#insertarrayat)|다른 하나의 배열만 삽입 하려면이 메서드를 호출 합니다.|
|[InsertAt](#insertat)|배열 개체에 새 요소 (또는 여러 개 요소)를 삽입 하려면이 메서드를 호출 합니다.|
|[IsEmpty](#isempty)|배열이 비어 있는지 테스트 하려면이 메서드를 호출 합니다.|
|[RemoveAll](#removeall)|배열 개체에서 모든 요소를 제거 하려면이 메서드를 호출 합니다.|
|[RemoveAt](#removeat)|배열에서 하나 이상의 요소를 제거 하려면이 메서드를 호출 합니다.|
|[SetAt](#setat)|배열 개체에는 요소의 값을 설정 하려면이 메서드를 호출 합니다.|
|[SetAtGrow](#setatgrow)|필요에 따라 배열 확장 배열 개체에는 요소의 값을 설정 하려면이 메서드를 호출 합니다.|
|[SetCount](#setcount)|배열 개체의 크기를 설정 하려면이 메서드를 호출 합니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[연산자&#91;&#93;](#operator_at)|배열의 요소에 대 한 참조를 반환 하도록이 연산자를 호출 합니다.|

### <a name="typedefs"></a>형식 정의

|||
|-|-|
|[INARGTYPE](#inargtype)|배열에 요소를 추가 하는 데 데이터 형식입니다.|
|[OUTARGTYPE](#outargtype)|배열에서 요소를 검색에 사용할 데이터 형식입니다.|

## <a name="remarks"></a>설명

`CAtlArray` 만들기 및 관리는 사용자 정의 형식 요소의 배열에 대 한 메서드를 제공 합니다. 하지만 표준 C 배열과 유사한는 `CAtlArray` 개체 수 동적으로 축소 하 고 필요에 따라 증가 합니다. 배열 인덱스는 항상 0 위치에서 시작 됩니다 및 상한을 수 수정 되거나 새 요소 추가 됨에 따라 확장을 허용 합니다.

적은 수의 요소를 ATL 클래스를 사용 하 여 배열에 대 한 [CSimpleArray](../../atl/reference/csimplearray-class.md) 사용할 수 있습니다.

`CAtlArray` MFC의와 밀접 한 관련이 `CArray` 클래스 및 serialization 지원 하지 않는 라도 MFC 프로젝트에서 작동 합니다.

자세한 내용은 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlcoll.h

##  <a name="add"></a>  CAtlArray::Add

배열 개체에 요소를 추가 하려면이 메서드를 호출 합니다.

```
size_t Add(INARGTYPE element);
size_t Add();
```

### <a name="parameters"></a>매개 변수

*element*<br/>
배열에 추가할 요소입니다.

### <a name="return-value"></a>반환 값

추가 된 요소의 인덱스를 반환합니다.

### <a name="remarks"></a>설명

새 요소를 배열의 끝에 추가 됩니다. 빈 요소 추가 됩니다; 제공 된 요소가 없는 경우 즉, 실제 요소가 추가 된 것 처럼 배열 크기 증가 됩니다. 작업이 실패 하는 경우 [AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow) E_OUTOFMEMORY 인수를 사용 하 여 호출 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#1](../../atl/codesnippet/cpp/catlarray-class_1.cpp)]

##  <a name="append"></a>  CAtlArray::Append

한 배열의 내용을 다른 끝에 추가 하려면이 메서드를 호출 합니다.

```
size_t Append(const CAtlArray<E, ETraits>& aSrc);
```

### <a name="parameters"></a>매개 변수

*aSrc*<br/>
추가할 배열입니다.

### <a name="return-value"></a>반환 값

추가 된 첫 번째 요소의 인덱스를 반환합니다.

### <a name="remarks"></a>설명

제공 된 배열의 요소는 기존 배열의 끝에 추가 됩니다. 필요한 경우 새 요소를 수용 하기 위해 메모리를 할당 됩니다.

배열에는 동일한 형식 이어야 하 고 배열 자체에 추가할 수 없는 합니다.

디버그 빌드에서 ATLASSERT 발생 하는 경우는 `CAtlArray` 인수가 올바른 배열이 아닙니다. 이거나 *aSrc* 동일한 개체를 가리킵니다. 릴리스 빌드에서 잘못 된 인수는 예기치 않은 동작이 발생할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#2](../../atl/codesnippet/cpp/catlarray-class_2.cpp)]

##  <a name="assertvalid"></a>  CAtlArray::AssertValid

배열 개체에 유효한 지 확인 하려면이 메서드를 호출 합니다.

```
void AssertValid() const;
```

### <a name="remarks"></a>설명

배열 개체 올바르지 않으면 ATLASSERT 어설션을 발생 시킵니다. 이 메서드는 _DEBUG이 정의 하는 경우에 사용할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#3](../../atl/codesnippet/cpp/catlarray-class_3.cpp)]

##  <a name="catlarray"></a>  CAtlArray::CAtlArray

생성자입니다.

```
CAtlArray() throw();
```

### <a name="remarks"></a>설명

배열 개체를 초기화합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#4](../../atl/codesnippet/cpp/catlarray-class_4.cpp)]

##  <a name="dtor"></a>  CAtlArray::~CAtlArray

소멸자입니다.

```
~CAtlArray() throw();
```

### <a name="remarks"></a>설명

배열 개체에서 사용 하는 모든 리소스를 해제 합니다.

##  <a name="copy"></a>  CAtlArray::Copy

다른 한 배열의 요소를 복사 하려면이 메서드를 호출 합니다.

```
void Copy(const CAtlArray<E, ETraits>& aSrc);
```

### <a name="parameters"></a>매개 변수

*aSrc*<br/>
원본 배열에 복사할 요소입니다.

### <a name="remarks"></a>설명

다른 배열의 요소를 사용 하 여 한 배열의 요소를 덮어쓰려면이 메서드를 호출 합니다. 필요한 경우 새 요소를 수용 하기 위해 메모리를 할당 됩니다. 자신에 게 배열의 요소를 복사 하는 것이 불가능 합니다.

사용 하 여 배열의 기존 내용을 보존 해야 할 경우 [CAtlArray::Append](#append) 대신 합니다.

디버그 빌드에서 ATLASSERT 발생 하는 경우 기존 `CAtlArray` 개체가 유효 하지 않은 경우 *aSrc* 동일한 개체를 가리킵니다. 릴리스 빌드에서 잘못 된 인수는 예기치 않은 동작이 발생할 수 있습니다.

> [!NOTE]
> `CAtlArray::Copy` 사용 하 여 만든 요소로 구성 된 배열을 지원 하지 않습니다 합니다 [CAutoPtr](../../atl/reference/cautoptr-class.md) 클래스입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#5](../../atl/codesnippet/cpp/catlarray-class_5.cpp)]

##  <a name="freeextra"></a>  CAtlArray::FreeExtra

배열에서 빈 요소를 제거 하려면이 메서드를 호출 합니다.

```
void FreeExtra() throw();
```

### <a name="remarks"></a>설명

모든 빈 요소가 제거 되지만 크기와 배열 상한 그대로 유지 됩니다.

CAtlArray 개체 유효 하지 않은 경우 또는 배열의 최대 크기를 초과 하는 경우 디버그 빌드에서 ATLASSERT이 발생 합니다.

##  <a name="getat"></a>  CAtlArray::GetAt

배열 개체의 단일 요소를 검색 하는이 메서드를 호출 합니다.

```
const E& GetAt(size_t iElement) const throw();
E& GetAt(size_t iElement) throw();
```

### <a name="parameters"></a>매개 변수

*iElement*<br/>
반환할 배열 요소의 인덱스 값입니다.

### <a name="return-value"></a>반환 값

필요한 배열 요소에 대 한 참조를 반환합니다.

### <a name="remarks"></a>설명

디버그 빌드에서 ATLASSERT 발생 *iElement* 배열의 요소 개수를 초과 합니다. 릴리스 빌드에서 잘못 된 인수는 예기치 않은 동작이 발생할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#6](../../atl/codesnippet/cpp/catlarray-class_6.cpp)]

##  <a name="getcount"></a>  CAtlArray::GetCount

배열에 저장 된 요소의 수를 반환 하려면이 메서드를 호출 합니다.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>반환 값

배열에 저장 된 요소의 수를 반환 합니다.

### <a name="remarks"></a>설명

반환 되는 값 배열에 첫 번째 요소 위치 0에 그대로 `GetCount` 항상 1 보다 크면 가장 큰 인덱스입니다.

### <a name="example"></a>예제

예를 참조 하세요 [CAtlArray::GetAt](#getat)합니다.

##  <a name="getdata"></a>  CAtlArray::GetData

배열의 첫 번째 요소에 대 한 포인터를 반환 하려면이 메서드를 호출 합니다.

```
E* GetData() throw();
const E* GetData() const throw();
```

### <a name="return-value"></a>반환 값

배열의 첫 번째 요소를 저장 하는 메모리 위치에 대 한 포인터를 반환 합니다. 사용할 수 있는 요소가 없는 경우 NULL이 반환 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#7](../../atl/codesnippet/cpp/catlarray-class_7.cpp)]

##  <a name="inargtype"></a>  CAtlArray::INARGTYPE

배열에 요소를 추가 하는 데 데이터 형식입니다.

```
typedef ETraits::INARGTYPE INARGTYPE;
```

##  <a name="insertarrayat"></a>  CAtlArray::InsertArrayAt

다른 하나의 배열만 삽입 하려면이 메서드를 호출 합니다.

```
void InsertArrayAt(size_t iStart, const CAtlArray<E, ETraits>* paNew);
```

### <a name="parameters"></a>매개 변수

*iStart*<br/>
배열을 삽입할 인덱스입니다.

*paNew*<br/>
삽입 될 배열입니다.

### <a name="remarks"></a>설명

배열에서 요소 *paNew* 요소부터 배열 개체에 복사 됩니다 *iStart*합니다. 기존 배열 요소를 덮어쓰지 않으려면 이동 됩니다.

디버그 빌드에서 ATLASSERT 발생 하는 경우는 `CAtlArray` 개체가 유효 하지 않은 경우는 *paNew* 포인터가 NULL 이거나 잘못 되었거나 합니다.

> [!NOTE]
> `CAtlArray::InsertArrayAt` 사용 하 여 만든 요소로 구성 된 배열을 지원 하지 않습니다 합니다 [CAutoPtr](../../atl/reference/cautoptr-class.md) 클래스입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#8](../../atl/codesnippet/cpp/catlarray-class_8.cpp)]

##  <a name="insertat"></a>  CAtlArray::InsertAt

배열 개체에 새 요소 (또는 여러 개 요소)를 삽입 하려면이 메서드를 호출 합니다.

```
void InsertAt(size_t iElement, INARGTYPE element, size_t nCount = 1);
```

### <a name="parameters"></a>매개 변수

*iElement*<br/>
요소 또는 요소를 삽입 하는 인덱스입니다.

*element*<br/>
값을 삽입할 요소입니다.

*nCount*<br/>
추가할 요소의 수입니다.

### <a name="remarks"></a>설명

인덱스에서 시작 하는 배열에 하나 이상의 요소를 삽입 *iElement*합니다. 기존 요소는 덮어쓰지 않으려면 이동 됩니다.

디버그 빌드에서 ATLASSERT 발생 하는 경우는 `CAtlArray` 개체가 올바르지 않습니다, 요소를 추가할 수는 0 또는 조합 된 요소 수가 포함 된 배열에 대 한 너무 큽니다. 일반 정품 빌드에서 잘못 된 매개 변수를 전달 하면 예기치 않은 결과가 발생할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#9](../../atl/codesnippet/cpp/catlarray-class_9.cpp)]

##  <a name="isempty"></a>  CAtlArray::IsEmpty

배열이 비어 있는지 테스트 하려면이 메서드를 호출 합니다.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>반환 값

배열이 비어 있는 경우 false이 고, 그렇지 true를 반환 합니다.

### <a name="remarks"></a>설명

배열에 요소가 없으면 비워 라고 합니다. 따라서 빈 요소를 포함 하는 경우에이 비어 있지 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#10](../../atl/codesnippet/cpp/catlarray-class_10.cpp)]

##  <a name="operator_at"></a>  CAtlArray::operator []

배열의 요소에 대 한 참조를 반환 하도록이 연산자를 호출 합니다.

```
E& operator[](size_t ielement) throw();
const E& operator[](size_t ielement) const throw();
```

### <a name="parameters"></a>매개 변수

*iElement*<br/>
반환할 배열 요소의 인덱스 값입니다.

### <a name="return-value"></a>반환 값

필요한 배열 요소에 대 한 참조를 반환합니다.

### <a name="remarks"></a>설명

비슷한 기능을 수행 [CAtlArray::GetAt](#getat)합니다. MFC 클래스와 달리 [CArray](../../mfc/reference/carray-class.md),이 연산자의 대 안으로 사용할 수 없습니다 [CAtlArray::SetAt](#setat)합니다.

디버그 빌드에서 ATLASSERT 발생 *iElement* 배열에 있는 요소의 총 수를 초과 합니다. 일반 정품 빌드에서 잘못 된 매개 변수는 예기치 않은 결과가 발생할 수 있습니다.

##  <a name="outargtype"></a>  CAtlArray::OUTARGTYPE

배열에서 요소를 검색에 사용할 데이터 형식입니다.

```
typedef ETraits::OUTARGTYPE OUTARGTYPE;
```

##  <a name="removeall"></a>  CAtlArray::RemoveAll

배열 개체에서 모든 요소를 제거 하려면이 메서드를 호출 합니다.

```
void RemoveAll() throw();
```

### <a name="remarks"></a>설명

배열 개체에서 모든 요소를 제거합니다.

이 메서드를 호출 [CAtlArray::SetCount](#setcount) 배열 크기를 조정 하 고 이후에 할당 된 메모리를 해제 합니다.

### <a name="example"></a>예제

예를 참조 하세요 [CAtlArray::IsEmpty](#isempty)합니다.

##  <a name="removeat"></a>  CAtlArray::RemoveAt

배열에서 하나 이상의 요소를 제거 하려면이 메서드를 호출 합니다.

```
void RemoveAt(size_t iElement, size_t nCount = 1);
```

### <a name="parameters"></a>매개 변수

*iElement*<br/>
제거할 첫 번째 요소의 인덱스입니다.

*nCount*<br/>
제거할 요소의 수입니다.

### <a name="remarks"></a>설명

배열에서 하나 이상의 요소를 제거합니다. 나머지 요소 아래로 이동 합니다. 상한 값은 감소, 이지만 메모리에 대 한 호출 될 때까지 해제 되지 않습니다 [CAtlArray::FreeExtra](#freeextra) 이루어집니다.

디버그 빌드에서 ATLASSERT 발생 하는 경우는 `CAtlArray` 개체가 유효 하지 않은 경우 결합된 된 총 *iElement* 및 *nCount* 배열에 있는 요소의 총 수를 초과 합니다. 일반 정품 빌드에서 잘못 된 매개 변수는 예기치 않은 결과가 발생할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#11](../../atl/codesnippet/cpp/catlarray-class_11.cpp)]

##  <a name="setat"></a>  CAtlArray::SetAt

배열 개체에는 요소의 값을 설정 하려면이 메서드를 호출 합니다.

```
void SetAt(size_t iElement, INARGTYPE element);
```

### <a name="parameters"></a>매개 변수

*iElement*<br/>
설정할 배열 요소를 가리키는 인덱스입니다.

*element*<br/>
지정 된 요소의 새 값입니다.

### <a name="remarks"></a>설명

디버그 빌드에서 ATLASSERT 발생 *iElement* 배열의 요소 개수를 초과 합니다. 일반 정품 빌드에서 잘못 된 매개 변수 예상치 못한 결과가 발생할 수 있습니다.

### <a name="example"></a>예제

예를 참조 하세요 [CAtlArray::GetAt](#getat)합니다.

##  <a name="setcount"></a>  CAtlArray::SetCount

배열 개체의 크기를 설정 하려면이 메서드를 호출 합니다.

```
bool SetCount(size_t nNewSize, int nGrowBy = - 1);
```

### <a name="parameters"></a>매개 변수

*nNewSize*<br/>
필요한 크기의 배열입니다.

*nGrowBy*<br/>
결정 하는 데 사용 하는 값을 얼마나 큰 버퍼를 확인 합니다. 값이-1 이면는 내부적으로 계산 된 값을 사용할 수입니다.

### <a name="return-value"></a>반환 값

그렇지 않으면 배열의 성공적으로 크기 조정, false true를 반환 합니다.

### <a name="remarks"></a>설명

배열 증가 또는 크기를 줄일 수 있습니다. 증가 하는 경우 추가 빈 요소를 배열에 추가 됩니다. 감소 하는 경우 가장 큰 인덱스를 사용 하 여 요소 삭제 되 고 메모리를 해제 합니다.

사용 하기 전에 배열의 크기를 설정 하려면이 메서드를 사용 합니다. 경우 `SetCount` 를 사용 하지 않으면 요소를 추가 하는 프로세스-후속 메모리 할당을 수행 하 고-성능이 저하 되 고 메모리를 조각화 됩니다.

### <a name="example"></a>예제

예를 참조 하세요 [CAtlArray::GetData](#getdata)합니다.

##  <a name="setatgrow"></a>  CAtlArray::SetAtGrow

필요에 따라 배열 확장 배열 개체에는 요소의 값을 설정 하려면이 메서드를 호출 합니다.

```
void SetAtGrow(size_t iElement, INARGTYPE element);
```

### <a name="parameters"></a>매개 변수

*iElement*<br/>
설정할 배열 요소를 가리키는 인덱스입니다.

*element*<br/>
지정 된 요소의 새 값입니다.

### <a name="remarks"></a>설명

인덱스에서 가리키는 요소의 값을 바꿉니다. 하는 경우 *iElement* 현재 크기 보다 크면 배열의 배열을 자동으로 증가에 대 한 호출을 사용 하 여 [CAtlArray::SetCount](#setcount)합니다. 디버그 빌드에서 ATLASSERT 발생 하는 경우는 `CAtlArray` 개체가 잘못 되었습니다. 일반 정품 빌드에서 잘못 된 매개 변수는 예기치 않은 결과가 발생할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#12](../../atl/codesnippet/cpp/catlarray-class_12.cpp)]

## <a name="see-also"></a>참고자료

[MMXSwarm 샘플](../../overview/visual-cpp-samples.md)<br/>
[DynamicConsumer 샘플](../../overview/visual-cpp-samples.md)<br/>
[UpdatePV 샘플](../../overview/visual-cpp-samples.md)<br/>
[움직이는 텍스트 샘플](../../overview/visual-cpp-samples.md)<br/>
[CArray 클래스](../../mfc/reference/carray-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
