---
title: CArray 클래스
ms.date: 11/04/2016
f1_keywords:
- CArray
- AFXTEMPL/CArray
- AFXTEMPL/CArray::CArray
- AFXTEMPL/CArray::Add
- AFXTEMPL/CArray::Append
- AFXTEMPL/CArray::Copy
- AFXTEMPL/CArray::ElementAt
- AFXTEMPL/CArray::FreeExtra
- AFXTEMPL/CArray::GetAt
- AFXTEMPL/CArray::GetCount
- AFXTEMPL/CArray::GetData
- AFXTEMPL/CArray::GetSize
- AFXTEMPL/CArray::GetUpperBound
- AFXTEMPL/CArray::InsertAt
- AFXTEMPL/CArray::IsEmpty
- AFXTEMPL/CArray::RemoveAll
- AFXTEMPL/CArray::RemoveAt
- AFXTEMPL/CArray::SetAt
- AFXTEMPL/CArray::SetAtGrow
- AFXTEMPL/CArray::SetSize
helpviewer_keywords:
- CArray [MFC], CArray
- CArray [MFC], Add
- CArray [MFC], Append
- CArray [MFC], Copy
- CArray [MFC], ElementAt
- CArray [MFC], FreeExtra
- CArray [MFC], GetAt
- CArray [MFC], GetCount
- CArray [MFC], GetData
- CArray [MFC], GetSize
- CArray [MFC], GetUpperBound
- CArray [MFC], InsertAt
- CArray [MFC], IsEmpty
- CArray [MFC], RemoveAll
- CArray [MFC], RemoveAt
- CArray [MFC], SetAt
- CArray [MFC], SetAtGrow
- CArray [MFC], SetSize
ms.assetid: fead8b00-4cfd-4625-ad0e-251df62ba92f
ms.openlocfilehash: f82dbf7dce2e14bf760bb76d23d23f667797ee0f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58779848"
---
# <a name="carray-class"></a>CArray 클래스

C 배열과 같습니다 이지만 수 동적으로 줄이고 필요에 따라 증가 하는 배열을 지원 합니다.

## <a name="syntax"></a>구문

```
template <class TYPE, class ARG_TYPE = const TYPE&>
class CArray : public CObject
```

#### <a name="parameters"></a>매개 변수

*TYPE*<br/>
배열에 저장 된 개체의 형식을 지정 하는 템플릿 매개 변수입니다. *형식* 에서 반환 되는 매개 변수는 `CArray`합니다.

*ARG_TYPE*<br/>
배열에 저장 하는 개체에 액세스 하는 데 사용 되는 인수 형식을 지정 하는 템플릿 매개 변수입니다. 에 대 한 참조 종종 *형식*합니다. *ARG_TYPE* 에 전달 되는 매개 변수는 `CArray`합니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CArray::CArray](#carray)|빈 배열을 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CArray::Add](#add)|배열 끝에 요소를 추가하고 필요하면 배열을 확장합니다.|
|[CArray::Append](#append)|배열;에 다른 배열을 추가합니다 필요 하면 배열을 확장합니다|
|[CArray::Copy](#copy)|배열에 다른 배열을 복사하고 필요하면 배열을 확장합니다.|
|[CArray::ElementAt](#elementat)|배열 내의 요소 포인터에 대한 임시 참조를 반환합니다.|
|[CArray::FreeExtra](#freeextra)|현재 상한을 초과하며 사용되지 않는 모든 메모리를 해제합니다.|
|[CArray::GetAt](#getat)|지정된 인덱스의 값을 반환합니다.|
|[CArray::GetCount](#getcount)|이 배열에 있는 요소의 수를 가져옵니다.|
|[CArray::GetData](#getdata)|배열의 요소에 대한 액세스를 허용합니다. NULL 일 수 있습니다.|
|[CArray::GetSize](#getsize)|이 배열에 있는 요소의 수를 가져옵니다.|
|[CArray::GetUpperBound](#getupperbound)|유효한 최대 인덱스를 반환합니다.|
|[CArray::InsertAt](#insertat)|지정한 인덱스에 요소 하나 또는 다른 배열의 모든 요소를 삽입합니다.|
|[CArray::IsEmpty](#isempty)|배열이 비어 있는지 여부를 결정 합니다.|
|[CArray::RemoveAll](#removeall)|이 배열의 모든 요소를 반환합니다.|
|[CArray::RemoveAt](#removeat)|특정 인덱스의 요소를 제거합니다.|
|[CArray::SetAt](#setat)|지정된 인덱스의 값을 설정합니다. 배열은 확장할 수 없습니다.|
|[CArray::SetAtGrow](#setatgrow)|지정된 인덱스의 값을 설정합니다. 필요한 경우 배열을 확장합니다.|
|[CArray::SetSize](#setsize)|이 배열에 포함된 요소의 수를 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[operator&#91;&#93;](#operator_at)|지정한 인덱스에 있는 요소를 설정하거나 가져옵니다.|

## <a name="remarks"></a>설명

배열 인덱스는 항상 0 위치에서 시작합니다. 상한 값은 수정 하거나 현재 바인딩된 이전 요소를 추가 하면 확장 배열 사용 여부를 결정할 수 있습니다. 메모리는 일부 요소가 null 인 경우에 상한를 연속적으로 할당 됩니다.

> [!NOTE]
>  크기가 조정 되는 대부분의 메서드를 `CArray` 개체 또는 요소를 사용 하 여 추가 [memcpy_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md) 요소를 이동 합니다. 때문에 이것이 문제가 `memcpy_s` 호출할 생성자는 필요한 모든 개체를 호환 되지 않습니다. 경우에 있는 항목을 `CArray` 와 호환 되지 않습니다 `memcpy_s`, 새로 만들어야 `CArray` 적절 한 크기의 합니다. 사용 해야 [CArray::Copy](#copy) 하 고 [CArray::SetAt](#setat) 이러한 메서드 대신 대입 연산자를 사용 하기 때문에 새 배열을 채우는 데 `memcpy_s`합니다.

에 대 한 액세스 시간을 C 배열과 마찬가지로 `CArray` 인덱싱된 요소는 상수 이며 배열 크기에 관계 없이 합니다.

> [!TIP]
>  배열을 사용 하기 전에 [SetSize](#setsize) 크기를 설정 하 여에 대 한 메모리를 할당 합니다. `SetSize`를 사용하지 않는 경우 배열에 요소를 추가하면 배열이 자주 다시 할당되고 복사됩니다. 이처럼 다시 할당 및 복사가 자주 수행되면 효율성이 떨어지며 메모리가 조각화될 수 있습니다.

배열에서 개별 요소의 덤프가 필요한 깊이를 설정 해야 합니다는 [CDumpContext](../../mfc/reference/cdumpcontext-class.md) 1 또는 더 큰 개체입니다.

전역 도우미 함수는이 클래스 호출의 특정 멤버 함수는 대부분의 사용에 대 한 사용자 지정 되어야 합니다는 `CArray` 클래스입니다. 항목을 참조 하세요 [컬렉션 클래스 도우미](../../mfc/reference/collection-class-helpers.md) MFC 매크로 및 전역 섹션에 있습니다.

배열 클래스를 파생 목록 파생과 같습니다.

사용 하는 방법에 대 한 자세한 내용은 `CArray`, 문서를 참조 하세요 [컬렉션](../../mfc/collections.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CArray`

## <a name="requirements"></a>요구 사항

**헤더:** afxtempl.h

##  <a name="add"></a>  CArray::Add

배열 1 씩 증가 하는 배열의 끝에 새 요소를 추가 합니다.

```
INT_PTR Add(ARG_TYPE newElement);
```

### <a name="parameters"></a>매개 변수

*ARG_TYPE*<br/>
템플릿 매개 변수를이 배열의 요소를 참조 하는 인수의 형식을 지정 합니다.

*newElement*<br/>
이 배열에 추가할 요소입니다.

### <a name="return-value"></a>반환 값

추가 된 요소의 인덱스입니다.

### <a name="remarks"></a>설명

하는 경우 [SetSize](#setsize) 사용 하 여 사용 된는 `nGrowBy` 추가 메모리를 1 보다 큰 값을 할당할 수 있습니다. 그러나 상한만 1 씩 증가 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#22](../../mfc/codesnippet/cpp/carray-class_1.cpp)]

##  <a name="append"></a>  CArray::Append

한 배열의 내용을 다른 끝에 추가 하려면이 멤버 함수를 호출 합니다.

```
INT_PTR Append(const CArray& src);
```

### <a name="parameters"></a>매개 변수

*src*<br/>
원본 배열에 추가할 요소입니다.

### <a name="return-value"></a>반환 값

추가 된 첫 번째 요소의 인덱스입니다.

### <a name="remarks"></a>설명

동일한 형식의 배열 이어야 합니다.

필요한 경우 `Append` 배열에 추가 된 요소에 맞게 추가 메모리를 할당할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#23](../../mfc/codesnippet/cpp/carray-class_2.cpp)]

##  <a name="carray"></a>  CArray::CArray

빈 배열을 생성합니다.

```
CArray();
```

### <a name="remarks"></a>설명

배열의 한 번에 하나의 요소를 증가합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#24](../../mfc/codesnippet/cpp/carray-class_3.cpp)]

##  <a name="copy"></a>  CArray::Copy

이 멤버 함수를 사용 하 여 다른 한 배열의 요소를 복사할 합니다.

```
void Copy(const CArray& src);
```

### <a name="parameters"></a>매개 변수

*src*<br/>
원본 배열에 복사할 요소입니다.

### <a name="remarks"></a>설명

다른 배열의 요소를 사용 하 여 한 배열의 요소를 덮어쓰려면이 멤버 함수를 호출 합니다.

`Copy` 메모리를 해제 하지 않는 그러나 필요한 경우 `Copy` 배열에 복사 된 요소에 맞게 추가 메모리를 할당할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#25](../../mfc/codesnippet/cpp/carray-class_4.cpp)]

##  <a name="elementat"></a>  CArray::ElementAt

배열 내의 지정된 된 요소에 대 한 임시 참조를 반환합니다.

```
TYPE& ElementAt(INT_PTR nIndex);
const TYPE& ElementAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
0 보다 크거나 같은 경우에 정수 인덱스에서 반환 된 값 보다 작거나 [GetUpperBound](#getupperbound)합니다.

### <a name="return-value"></a>반환 값

배열 요소에 대 한 참조입니다.

### <a name="remarks"></a>설명

배열에 대 한 왼쪽 대입 연산자를 구현 하는 것이 됩니다.

### <a name="example"></a>예제

  예를 참조 하세요 [GetSize](#getsize)합니다.

##  <a name="freeextra"></a>  CArray::FreeExtra

배열 된 증가 하는 동안 할당 된 모든 추가 메모리를 해제 합니다.

```
void FreeExtra();
```

### <a name="remarks"></a>설명

이 함수에 상한 값 배열 크기에 영향을 주지 않습니다.

### <a name="example"></a>예제

  예를 참조 하세요 [GetData](#getdata)합니다.

##  <a name="getat"></a>  CArray::GetAt

지정된 된 인덱스에 있는 배열 요소를 반환합니다.

```
TYPE& GetAt(INT_PTR nIndex);
const TYPE& GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>매개 변수

*TYPE*<br/>
템플릿 매개 변수 배열 요소의 형식을 지정 합니다.

*nIndex*<br/>
0 보다 크거나 같은 경우에 정수 인덱스에서 반환 된 값 보다 작거나 [GetUpperBound](#getupperbound)합니다.

### <a name="return-value"></a>반환 값

이 인덱스에 현재 배열 요소입니다.

### <a name="remarks"></a>설명

반환 된 값 보다 큰 음수 값 또는 값을 전달 `GetUpperBound` 실패 한 어설션이 발생 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#26](../../mfc/codesnippet/cpp/carray-class_5.cpp)]

##  <a name="getcount"></a>  CArray::GetCount

배열 요소의 수를 반환합니다.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>반환 값

배열의 항목 수입니다.

### <a name="remarks"></a>설명

배열의 요소 수를 검색 하려면이 메서드를 호출 합니다. 인덱스 0부터 시작 되므로, 크기가 1 가장 큰 인덱스 보다 큽니다. 와 동일한 결과 생성은이 메서드를 호출 합니다 [CArray::GetSize](#getsize) 메서드.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#27](../../mfc/codesnippet/cpp/carray-class_6.cpp)]

##  <a name="getdata"></a>  CArray::GetData

이 멤버 함수를 사용 하 여 배열 요소에 직접 액세스할 수 있습니다.

```
const TYPE* GetData() const;
TYPE* GetData();
```

### <a name="parameters"></a>매개 변수

*TYPE*<br/>
템플릿 매개 변수 배열 요소의 형식을 지정 합니다.

### <a name="return-value"></a>반환 값

배열 요소에 대 한 포인터입니다.

### <a name="remarks"></a>설명

요소가 없는 경우 `GetData` null 값을 반환 합니다.

배열의 요소에 대 한 직접 액세스를 손쉽게 보다 신속 하 게 작업할 수 있습니다, 하는 동안 주의 호출할 때 사용할 `GetData`; 직접적 오류 배열 요소에 영향을 줍니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#28](../../mfc/codesnippet/cpp/carray-class_7.cpp)]

##  <a name="getsize"></a>  CArray::GetSize

배열의 크기를 반환합니다.

```
INT_PTR GetSize() const;
```

### <a name="remarks"></a>설명

인덱스 0부터 시작 되므로, 크기가 1 가장 큰 인덱스 보다 큽니다. 와 동일한 결과 생성은이 메서드를 호출 합니다 [CArray::GetCount](#getcount) 메서드.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#29](../../mfc/codesnippet/cpp/carray-class_8.cpp)]

##  <a name="getupperbound"></a>  CArray::GetUpperBound

이 배열의 현재 상한 값을 반환합니다.

```
INT_PTR GetUpperBound() const;
```

### <a name="remarks"></a>설명

배열 인덱스 0부터 시작 되므로, 반환 값 1 보다 작은 `GetSize`합니다.

조건이 `GetUpperBound( )` =-1은 배열에 요소가 있는지를 나타냅니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CArray::GetAt](#getat)합니다.

##  <a name="insertat"></a>  CArray::InsertAt

첫 번째 버전 `InsertAt` 배열에서 지정된 된 인덱스에 요소가 하나 (또는 여러 개 요소)를 삽입 합니다.

```
void InsertAt(
    INT_PTR nIndex,
    ARG_TYPE newElement,
    INT_PTR nCount = 1);

void InsertAt(
    INT_PTR nStartIndex,
    CArray* pNewArray);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
반환 된 값 보다 클 수 있습니다 하는 정수 인덱스 `GetUpperBound`합니다.

*ARG_TYPE*<br/>
템플릿 매개 변수를이 배열에 있는 요소의 형식을 지정 합니다.

*newElement*<br/>
이 배열에 배치 될 요소입니다.

*nCount*<br/>
이 요소는 여야 하는 횟수 (기본값은 1)를 삽입 합니다.

*nStartIndex*<br/>
반환 된 값 보다 클 수 있습니다 하는 정수 인덱스 [GetUpperBound](#getupperbound)합니다.

*pNewArray*<br/>
이 배열에 추가할 요소를 포함 하는 다른 배열입니다.

### <a name="remarks"></a>설명

프로세스에서 이동 (인덱스 증가)에서 위의 모든 요소를 구성 하며이 인덱스에 있는 기존 요소 이동 합니다.

두 번째 버전에서 다른 모든 요소를 삽입 `CArray` 에서 시작 하는 컬렉션을 *nStartIndex* 위치 합니다.

`SetAt` 반면, 함수 한 지정 된 배열 요소 및 요소를 이동 하지 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#30](../../mfc/codesnippet/cpp/carray-class_9.cpp)]

##  <a name="isempty"></a>  CArray::IsEmpty

배열이 비어 있는지 여부를 결정 합니다.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>반환 값

배열에 요소가; 없으면 0이 아닌 값 그렇지 않으면 0입니다.

##  <a name="operator_at"></a>  CArray::operator \[\]

이러한 아래 첨자 연산자는 편리한 대체 합니다 [SetAt](#setat) 하 고 [GetAt](#getat) 함수입니다.

```
TYPE& operator[](int_ptr nindex);
const TYPE& operator[](int_ptr nindex) const;
```

### <a name="parameters"></a>매개 변수

*TYPE*<br/>
템플릿 매개 변수를이 배열에 있는 요소의 형식을 지정 합니다.

*nIndex*<br/>
액세스할 요소의 인덱스입니다.

### <a name="remarks"></a>설명

첫 번째 연산자를 호출 하지 않는 배열을 **const**, 대입문의 왼쪽 (l-value) 또는 오른쪽 (r-value)에 사용할 수 있습니다. 두 번째 호출 **const** 배열 오른쪽에만 사용할 수 있습니다.

라이브러리의 디버그 버전의 아래 첨자 (중 하나에 대입문의 왼쪽 또는 오른쪽) 범위를 벗어난 경우 어설션 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#34](../../mfc/codesnippet/cpp/carray-class_10.cpp)]

##  <a name="relocateelements"></a>  CArray::RelocateElements

배열 확대 되거나 축소 하는 경우 새 버퍼에 데이터를 재배치 합니다.

```
template<class TYPE, class ARG_TYPE>
AFX_INLINE void CArray<TYPE, ARG_TYPE>::RelocateElements(
    TYPE* pNewData,
    const TYPE* pData,
    INT_PTR nCount);
```

### <a name="parameters"></a>매개 변수

*pNewData*<br/>
요소의 배열에 대 한 새 버퍼입니다.

*pData*<br/>
이전 배열 요소입니다.

*nCount*<br/>
이전 배열의 요소 수입니다.

### <a name="remarks"></a>설명

*pNewData* 는 항상 모든 보유 하기에 충분 합니다 *pData* 요소입니다.

합니다 [CArray](../../mfc/reference/carray-class.md) 구현은이 메서드를 사용 하 여 배열 확대 되거나 축소 하는 경우 이전 데이터를 새 버퍼에 복사 (때 [SetSize](#setsize) 또는 [FreeExtra](#freeextra) 라고). 기본 구현만 데이터를 복사합니다.

해당 멤버 중 하나에 대 한 포인터를 포함 하는 요소 또는 배열 요소 중 하나에 대 한 포인터를 포함 하는 다른 구조체 배열에 대 한 포인터를 일반 복사본에서 업데이트 되지 않습니다. 이 경우의 특수화를 구현 하 여 포인터를 수정할 수 있습니다 `RelocateElements` 관련 형식입니다. 데이터 복사에 대 한도 담당합니다.

##  <a name="removeall"></a>  CArray::RemoveAll

이 배열의 모든 요소를 반환합니다.

```
void RemoveAll();
```

### <a name="remarks"></a>설명

배열이 비어 이미 함수는 계속 작동 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#31](../../mfc/codesnippet/cpp/carray-class_11.cpp)]

##  <a name="removeat"></a>  CArray::RemoveAt

배열에서 지정된 된 인덱스에서 시작 하는 하나 이상의 요소를 제거 합니다.

```
void RemoveAt(
    INT_PTR nIndex,
    INT_PTR nCount = 1);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
0 보다 크거나 같은 경우에 정수 인덱스에서 반환 된 값 보다 작거나 [GetUpperBound](#getupperbound)합니다.

*nCount*<br/>
제거할 요소의 수입니다.

### <a name="remarks"></a>설명

프로세스에서 제거 된 요소 위에 있는 모든 요소 아래로 이동합니다. 이 감소는 위 배열의 하지만 메모리를 해제 하지 않습니다.

제거 지점 위에 배열에 포함 된 보다 더 많은 요소를 제거 하려는 경우 라이브러리의 디버그 버전 어설션 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#32](../../mfc/codesnippet/cpp/carray-class_12.cpp)]

##  <a name="setat"></a>  CArray::SetAt

지정된 된 인덱스에 있는 배열 요소를 설정합니다.

```
void SetAt(INT_PTR nIndex, ARG_TYPE newElement);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
0 보다 크거나 같은 경우에 정수 인덱스에서 반환 된 값 보다 작거나 [GetUpperBound](#getupperbound)합니다.

*ARG_TYPE*<br/>
템플릿 매개 변수 배열 요소를 참조 하기 위해 사용 되는 인수 형식을 지정 합니다.

*newElement*<br/>
지정된 된 위치에 저장할 새 요소의 값입니다.

### <a name="remarks"></a>설명

`SetAt` 증가 된 배열의 발생 하지 않습니다. 사용 하 여 [SetAtGrow](#setatgrow) 배열 자동으로 증가 하도록 하려는 경우.

인덱스 값 배열에서 올바른 위치를 나타내도록 해야 합니다. 범위를 벗어난 경우 라이브러리의 디버그 버전 어설션 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [GetAt](#getat)합니다.

##  <a name="setatgrow"></a>  CArray::SetAtGrow

지정된 된 인덱스에 있는 배열 요소를 설정합니다.

```
void SetAtGrow(INT_PTR nIndex, ARG_TYPE newElement);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
정수 인덱스는 0 보다 크거나 같은 경우입니다.

*ARG_TYPE*<br/>
템플릿 매개 변수 배열에 있는 요소의 형식을 지정 합니다.

*newElement*<br/>
이 배열에 추가할 요소입니다. NULL 값이 허용 됩니다.

### <a name="remarks"></a>설명

필요한 경우 배열을 자동으로 증가 (상한 값은 새 요소에 맞게 조정 됩니다.).

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#33](../../mfc/codesnippet/cpp/carray-class_13.cpp)]

##  <a name="setsize"></a>  CArray::SetSize

비어 있거나 기존 배열의; 크기를 설정합니다. 필요한 경우 메모리를 할당 합니다.

```
void SetSize(
    INT_PTR nNewSize,
    INT_PTR nGrowBy = -1);
```

### <a name="parameters"></a>매개 변수

*nNewSize*<br/>
새 배열 크기 (요소 수)입니다. 0 보다 크거나 이어야 합니다.

*nGrowBy*<br/>
크기 증가 필요한 경우 할당할 요소 슬롯의 최소 수입니다.

### <a name="remarks"></a>설명

그런 다음 새 크기가 이전 크기 보다 작은 경우 배열이 잘리고 고 모든 사용 되지 않는 메모리 해제 됩니다.

배열 사용 하기 전에 배열의 크기를 설정 하려면이 함수를 사용 합니다. `SetSize`를 사용하지 않는 경우 배열에 요소를 추가하면 배열이 자주 다시 할당되고 복사됩니다. 이처럼 다시 할당 및 복사가 자주 수행되면 효율성이 떨어지며 메모리가 조각화될 수 있습니다.

합니다 *nGrowBy* 매개 변수 배열 증가 하는 동안 내부 메모리 할당에 영향을 줍니다. 용도 영향을 주지 않으며 배열 크기에서 보고 [GetSize](#getsize) 하 고 [GetUpperBound](#getupperbound)합니다. 기본값을 사용 하는 경우 MFC는 메모리 조각화를 방지 하 고 대부분의 효율성을 최적화 하기 위해 계산 하는 방식으로 메모리를 할당 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [GetData](#getdata)합니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 수집](../../overview/visual-cpp-samples.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CObArray 클래스](../../mfc/reference/cobarray-class.md)<br/>
[컬렉션 클래스 도우미](../../mfc/reference/collection-class-helpers.md)
