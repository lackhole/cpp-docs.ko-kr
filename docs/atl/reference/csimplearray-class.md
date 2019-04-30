---
title: CSimpleArray 클래스
ms.date: 11/04/2016
f1_keywords:
- CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray::CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray::Add
- ATLSIMPCOLL/ATL::CSimpleArray::Find
- ATLSIMPCOLL/ATL::CSimpleArray::GetData
- ATLSIMPCOLL/ATL::CSimpleArray::GetSize
- ATLSIMPCOLL/ATL::CSimpleArray::Remove
- ATLSIMPCOLL/ATL::CSimpleArray::RemoveAll
- ATLSIMPCOLL/ATL::CSimpleArray::RemoveAt
- ATLSIMPCOLL/ATL::CSimpleArray::SetAtIndex
helpviewer_keywords:
- CSimpleArray class
ms.assetid: ee0c9f39-b61c-4c18-bc43-4eada21dca3a
ms.openlocfilehash: 8c050002549fc6b7a18acb34f0e4f9a2f278db82
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62278009"
---
# <a name="csimplearray-class"></a>CSimpleArray 클래스

이 클래스는 간단한 배열을 관리 하기 위한 메서드를 제공 합니다.

## <a name="syntax"></a>구문

```
template <class T, class TEqual = CSimpleArrayEqualHelper<T>>
class CSimpleArray
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
배열에 저장할 데이터의 형식입니다.

*TEqual*<br/>
형식의 요소에 대 한 같음 테스트를 정의 하는 특성 (trait) 개체 *T*합니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CSimpleArray::CSimpleArray](#csimplearray)|간단한 배열에 대 한 생성자입니다.|
|[CSimpleArray::~CSimpleArray](#dtor)|간단한 배열에 대 한 소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CSimpleArray::Add](#add)|배열에 새 요소를 추가합니다.|
|[CSimpleArray::Find](#find)|배열의 요소를 찾습니다.|
|[CSimpleArray::GetData](#getdata)|배열에 저장 된 데이터에 대 한 포인터를 반환 합니다.|
|[CSimpleArray::GetSize](#getsize)|배열에 저장 된 요소의 수를 반환 합니다.|
|[CSimpleArray::Remove](#remove)|배열에서 지정된 된 요소를 제거합니다.|
|[CSimpleArray::RemoveAll](#removeall)|배열에서 모든 요소를 제거합니다.|
|[CSimpleArray::RemoveAt](#removeat)|배열에서 지정된 된 요소를 제거합니다.|
|[CSimpleArray::SetAtIndex](#setatindex)|배열에서 지정된 된 요소를 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CSimpleArray::operator\[\]](#operator_at)|배열에서 요소를 검색합니다.|
|[CSimpleArray::operator =](#operator_eq)|대입 연산자입니다.|

## <a name="remarks"></a>설명

`CSimpleArray` 만들기 및 관리를 간단한 배열에 지정 된 형식의 메서드를 제공 `T`합니다.

매개 변수 `TEqual` 형식의 두 요소에 대 한 같음 함수를 정의 하는 수단을 제공 `T`합니다. 클래스를 만들어 비슷합니다 [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md), 지정 된 배열에 대 한 같음 테스트의 동작을 변경 하는 것이 가능 합니다. 예를 들어, 포인터 배열을 처리할 때 포인터 참조 값에 따라으로 같음을 정의에 유용할 수 있습니다. 기본 구현은 활용 **operator=()** 합니다.

둘 다 `CSimpleArray` 하 고 [CSimpleMap](../../atl/reference/csimplemap-class.md) 작은 수의 요소를 위해 설계 되었습니다. [CAtlArray](../../atl/reference/catlarray-class.md) 하 고 [CAtlMap](../../atl/reference/catlmap-class.md) 배열에는 많은 수의 요소를 포함 하는 경우에 사용 해야 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlsimpcoll.h

## <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#86](../../atl/codesnippet/cpp/csimplearray-class_1.cpp)]

##  <a name="add"></a>  CSimpleArray::Add

배열에 새 요소를 추가합니다.

```
BOOL Add(const T& t);
```

### <a name="parameters"></a>매개 변수

*t*<br/>
배열에 추가할 요소입니다.

### <a name="return-value"></a>반환 값

경우 요소가 성공적으로 추가 된 배열에 FALSE이 고, 그렇지 TRUE를 반환 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#87](../../atl/codesnippet/cpp/csimplearray-class_2.cpp)]

##  <a name="csimplearray"></a>  CSimpleArray::CSimpleArray

배열 개체에 대 한 생성자입니다.

```
CSimpleArray(const CSimpleArray<T, TEqual>& src);
CSimpleArray();
```

### <a name="parameters"></a>매개 변수

*src*<br/>
기존 `CSimpleArray` 개체입니다.

### <a name="remarks"></a>설명

데이터 멤버를 비어 있는 새 만들기 초기화 `CSimpleArray` 개체나 기존 복사본 `CSimpleArray` 개체입니다.

##  <a name="dtor"></a>  CSimpleArray::~CSimpleArray

소멸자입니다.

```
~CSimpleArray();
```

### <a name="remarks"></a>설명

할당 된 모든 리소스를 해제합니다.

##  <a name="find"></a>  CSimpleArray::Find

배열의 요소를 찾습니다.

```
int Find(const T& t) const;
```

### <a name="parameters"></a>매개 변수

*t*<br/>
검색할 요소입니다.

### <a name="return-value"></a>반환 값

요소가 없는 경우 찾은 요소의 또는-1의 인덱스를 반환 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#88](../../atl/codesnippet/cpp/csimplearray-class_3.cpp)]

##  <a name="getdata"></a>  CSimpleArray::GetData

배열에 저장 된 데이터에 대 한 포인터를 반환 합니다.

```
T* GetData() const;
```

### <a name="return-value"></a>반환 값

배열의 데이터에 대 한 포인터를 반환합니다.

##  <a name="getsize"></a>  CSimpleArray::GetSize

배열에 저장 된 요소의 수를 반환 합니다.

```
int GetSize() const;
```

### <a name="return-value"></a>반환 값

배열에 저장 된 요소의 수를 반환 합니다.

##  <a name="operator_at"></a>  CSimpleArray::operator \[\]

배열에서 요소를 검색합니다.

```
T& operator[](int nindex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
요소의 인덱스입니다.

### <a name="return-value"></a>반환 값

참조 하는 배열의 요소를 반환 *nIndex*합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#89](../../atl/codesnippet/cpp/csimplearray-class_4.cpp)]

##  <a name="operator_eq"></a>  CSimpleArray::operator =

대입 연산자입니다.

```
CSimpleArray<T, TEqual>
& operator=(
    const CSimpleArray<T, TEqual>& src);
```

### <a name="parameters"></a>매개 변수

*src*<br/>
복사할 배열입니다.

### <a name="return-value"></a>반환 값

업데이트에 대 한 포인터를 반환 합니다 `CSimpleArray` 개체입니다.

### <a name="remarks"></a>설명

모든 요소를 복사 합니다 `CSimpleArray` 개체에서 참조 *src* 현재 배열 개체에 모든 기존 데이터를 바꿉니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#90](../../atl/codesnippet/cpp/csimplearray-class_5.cpp)]

##  <a name="remove"></a>  CSimpleArray::Remove

배열에서 지정된 된 요소를 제거합니다.

```
BOOL Remove(const T& t);
```

### <a name="parameters"></a>매개 변수

*t*<br/>
배열에서 제거할 요소입니다.

### <a name="return-value"></a>반환 값

경우 요소를 발견 및 제거, FALSE 그렇지 않으면 TRUE를 반환 합니다.

### <a name="remarks"></a>설명

요소를 제거 하는 경우 배열의 나머지 요소는 빈 공간을 채우기 위해 매겨집니다.

##  <a name="removeall"></a>  CSimpleArray::RemoveAll

배열에서 모든 요소를 제거합니다.

```
void RemoveAll();
```

### <a name="remarks"></a>설명

현재 배열에 저장 하는 모든 요소를 제거 합니다.

##  <a name="removeat"></a>  CSimpleArray::RemoveAt

배열에서 지정된 된 요소를 제거합니다.

```
BOOL RemoveAtint nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
제거할 요소를 가리키는 인덱스입니다.

### <a name="return-value"></a>반환 값

요소가 제거, 인덱스 잘못 되었으면 FALSE 경우 TRUE를 반환 합니다.

### <a name="remarks"></a>설명

요소를 제거 하는 경우 배열의 나머지 요소는 빈 공간을 채우기 위해 매겨집니다.

##  <a name="setatindex"></a>  CSimpleArray::SetAtIndex

배열에서 지정된 된 요소를 설정 합니다.

```
BOOL SetAtIndex(
    int nIndex,
    const T& t);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
변경 하는 요소의 인덱스입니다.

*t*<br/>
지정된 요소에 할당할 값입니다.

### <a name="return-value"></a>반환 값

경우 TRUE를 반환 성공적이 고 FALSE 인덱스가 잘못 되었습니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)
