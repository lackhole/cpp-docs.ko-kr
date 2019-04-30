---
title: CTypedPtrArray 클래스
ms.date: 11/04/2016
f1_keywords:
- CTypedPtrArray
- AFXTEMPL/CTypedPtrArray
- AFXTEMPL/CTypedPtrArray::Add
- AFXTEMPL/CTypedPtrArray::Append
- AFXTEMPL/CTypedPtrArray::Copy
- AFXTEMPL/CTypedPtrArray::ElementAt
- AFXTEMPL/CTypedPtrArray::GetAt
- AFXTEMPL/CTypedPtrArray::InsertAt
- AFXTEMPL/CTypedPtrArray::SetAt
- AFXTEMPL/CTypedPtrArray::SetAtGrow
helpviewer_keywords:
- CTypedPtrArray [MFC], Add
- CTypedPtrArray [MFC], Append
- CTypedPtrArray [MFC], Copy
- CTypedPtrArray [MFC], ElementAt
- CTypedPtrArray [MFC], GetAt
- CTypedPtrArray [MFC], InsertAt
- CTypedPtrArray [MFC], SetAt
- CTypedPtrArray [MFC], SetAtGrow
ms.assetid: e3ecdf1a-a889-4156-92dd-ddbd36ccd919
ms.openlocfilehash: 080e47746b83b6ff12db9f6df0fc27bcd202bb51
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346094"
---
# <a name="ctypedptrarray-class"></a>CTypedPtrArray 클래스

`CPtrArray` 또는 `CObArray`클래스의 개체에 대해 형식 안전 "래퍼"를 제공합니다.

## <a name="syntax"></a>구문

```
template<class BASE_CLASS, class TYPE>
class CTypedPtrArray : public BASE_CLASS
```

#### <a name="parameters"></a>매개 변수

*BASE_CLASS*<br/>
형식화 된 포인터 배열 클래스의 기본 클래스 배열 클래스 여야 합니다 ( `CObArray` 또는 `CPtrArray`).

*TYPE*<br/>
기본 클래스 배열에 저장 된 요소의 형식입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CTypedPtrArray::Add](#add)|배열의 끝에 새 요소를 추가합니다. 필요 하면 배열을 확장합니다|
|[CTypedPtrArray::Append](#append)|한 배열의 내용을 다른 끝에 추가합니다. 필요 하면 배열을 확장합니다|
|[CTypedPtrArray::Copy](#copy)|배열에 다른 배열을 복사하고 필요하면 배열을 확장합니다.|
|[CTypedPtrArray::ElementAt](#elementat)|배열 내의 요소 포인터에 대한 임시 참조를 반환합니다.|
|[CTypedPtrArray::GetAt](#getat)|지정된 인덱스의 값을 반환합니다.|
|[CTypedPtrArray::InsertAt](#insertat)|지정한 인덱스에 요소 하나 또는 다른 배열의 모든 요소를 삽입합니다.|
|[CTypedPtrArray::SetAt](#setat)|지정된 인덱스의 값을 설정합니다. 배열은 확장할 수 없습니다.|
|[CTypedPtrArray::SetAtGrow](#setatgrow)|지정된 인덱스의 값을 설정합니다. 필요한 경우 배열을 확장합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CTypedPtrArray::operator \[ \]](#operator_at)|지정한 인덱스에 있는 요소를 설정하거나 가져옵니다.|

## <a name="remarks"></a>설명

사용 하는 경우 `CTypedPtrArray` 대신 `CPtrArray` 하거나 `CObArray`, C++ 형식 검사 기능에 일치 하지 않는 포인터 형식으로 인 한 오류를 제거 하는 데 도움이 됩니다.

또한 합니다 `CTypedPtrArray` 를 사용 하는 경우 캐스팅을 상당 부분을 수행 하는 래퍼 `CObArray` 또는 `CPtrArray`합니다.

때문에 모든 `CTypedPtrArray` 함수는 인라인,이 템플릿을 사용 하 여 크게 영향을 주지 않습니다 크기 또는 코드의 속도.

사용 하 여 대 한 자세한 내용은 `CTypedPtrArray`, 문서를 참조 하세요 [컬렉션](../../mfc/collections.md) 하 고 [템플릿 기반 클래스](../../mfc/template-based-classes.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`BASE_CLASS`

`CTypedPtrArray`

## <a name="requirements"></a>요구 사항

**헤더:** afxtempl.h

##  <a name="add"></a>  CTypedPtrArray::Add

이 멤버 함수 호출 `BASE_CLASS` **:: 추가**합니다.

```
INT_PTR Add(TYPE newElement);
```

### <a name="parameters"></a>매개 변수

*TYPE*<br/>
템플릿 매개 변수 배열에 추가할 요소의 형식을 지정 합니다.

*newElement*<br/>
이 배열에 추가할 요소입니다.

### <a name="return-value"></a>반환 값

추가 된 요소의 인덱스입니다.

### <a name="remarks"></a>설명

설명, 자세한 [CObArray::Add](../../mfc/reference/cobarray-class.md#add)합니다.

##  <a name="append"></a>  CTypedPtrArray::Append

이 멤버 함수 호출 `BASE_CLASS`:: 추가 * * 합니다.

```
INT_PTR Append(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```

### <a name="parameters"></a>매개 변수

*BASE_CLASS*<br/>
형식화 된 포인터 배열 클래스의 기본 클래스 배열 클래스 여야 합니다 ( [CObArray](../../mfc/reference/cobarray-class.md) 하거나 [CPtrArray](../../mfc/reference/cptrarray-class.md)).

*TYPE*<br/>
기본 클래스 배열에 저장 된 요소의 형식입니다.

*src*<br/>
원본 배열에 추가할 요소입니다.

### <a name="return-value"></a>반환 값

추가 된 첫 번째 요소의 인덱스입니다.

### <a name="remarks"></a>설명

설명, 자세한 [CObArray::Append](../../mfc/reference/cobarray-class.md#append)합니다.

##  <a name="copy"></a>  CTypedPtrArray::Copy

이 멤버 함수 호출 `BASE_CLASS` **:: 복사**합니다.

```
void Copy(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```

### <a name="parameters"></a>매개 변수

*BASE_CLASS*<br/>
형식화 된 포인터 배열 클래스의 기본 클래스 배열 클래스 여야 합니다 ( [CObArray](../../mfc/reference/cobarray-class.md) 하거나 [CPtrArray](../../mfc/reference/cptrarray-class.md)).

*TYPE*<br/>
기본 클래스 배열에 저장 된 요소의 형식입니다.

*src*<br/>
원본 배열에 복사할 요소입니다.

### <a name="remarks"></a>설명

설명, 자세한 [CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)합니다.

##  <a name="elementat"></a>  CTypedPtrArray::ElementAt

이 인라인 함수 호출 `BASE_CLASS` **:: ElementAt**합니다.

```
TYPE& ElementAt(INT_PTR nIndex);
```

### <a name="parameters"></a>매개 변수

*TYPE*<br/>
템플릿 매개 변수를이 배열에 저장 된 요소의 형식을 지정 합니다.

*nIndex*<br/>
0 보다 크거나 같은 경우에 정수 인덱스에서 반환 된 값 보다 작거나 `BASE_CLASS` **:: GetUpperBound**합니다.

### <a name="return-value"></a>반환 값

지정 된 위치에 있는 요소에 대 한 임시 참조 *nIndex*합니다. 이 요소는 템플릿 매개 변수로 지정 된 형식의 *형식*합니다.

### <a name="remarks"></a>설명

설명, 자세한 [CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)합니다.

##  <a name="getat"></a>  CTypedPtrArray::GetAt

이 인라인 함수 호출 `BASE_CLASS` **:: GetAt**합니다.

```
TYPE GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>매개 변수

*TYPE*<br/>
템플릿 매개 변수 배열에 저장 된 요소의 형식을 지정 합니다.

*nIndex*<br/>
0 보다 크거나 같은 경우에 정수 인덱스에서 반환 된 값 보다 작거나 `BASE_CLASS` **:: GetUpperBound**합니다.

### <a name="return-value"></a>반환 값

지정 된 위치에 있는 요소의 복사본 *nIndex*합니다. 이 요소는 템플릿 매개 변수로 지정 된 형식의 *형식*합니다.

### <a name="remarks"></a>설명

설명, 자세한 [CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)

##  <a name="insertat"></a>  CTypedPtrArray::InsertAt

이 멤버 함수 호출 `BASE_CLASS` **:: InsertAt**합니다.

```
void InsertAt(
    INT_PTR nIndex,
    TYPE newElement,
    INT_PTR nCount = 1);

void InsertAt(
    INT_PTR nStartIndex,
    CTypedPtrArray<BASE_CLASS, TYPE>* pNewArray);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
반환 된 값 보다 클 수 있습니다 하는 정수 인덱스 [CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)합니다.

*TYPE*<br/>
기본 클래스 배열에 저장 된 요소의 형식입니다.

*newElement*<br/>
이 배열에 배치할 개체 포인터입니다. A *newElement* 가치의 **NULL** 허용 됩니다.

*nCount*<br/>
이 요소는 여야 하는 횟수 (기본값은 1)를 삽입 합니다.

*nStartIndex*<br/>
반환 된 값 보다 클 수 있습니다 하는 정수 인덱스 `CObArray::GetUpperBound`합니다.

*BASE_CLASS*<br/>
형식화 된 포인터 배열 클래스의 기본 클래스 배열 클래스 여야 합니다 ( [CObArray](../../mfc/reference/cobarray-class.md) 하거나 [CPtrArray](../../mfc/reference/cptrarray-class.md)).

*pNewArray*<br/>
이 배열에 추가할 요소를 포함 하는 다른 배열입니다.

### <a name="remarks"></a>설명

설명, 자세한 [CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)합니다.

##  <a name="operator_at"></a>  CTypedPtrArray::operator [ ]

이러한 인라인 연산자 호출 `BASE_CLASS` **:: operator**합니다.

```
TYPE& operator[ ](int_ptr nindex);
TYPE operator[ ](int_ptr nindex) const;
```

### <a name="parameters"></a>매개 변수

*TYPE*<br/>
템플릿 매개 변수 배열에 저장 된 요소의 형식을 지정 합니다.

*nIndex*<br/>
0 보다 크거나 같은 경우에 정수 인덱스에서 반환 된 값 보다 작거나 `BASE_CLASS` **:: GetUpperBound**합니다.

### <a name="remarks"></a>설명

첫 번째 연산자를 호출 하지 않는 배열을 **const**, 대입문의 왼쪽 (l-value) 또는 오른쪽 (r-value)에서 사용할 수 있습니다. 두 번째 호출 **const** 배열 오른쪽 에서만 사용할 수 있습니다.

라이브러리의 디버그 버전의 아래 첨자 (중 하나에 대입문의 왼쪽 또는 오른쪽) 범위를 벗어난 경우 어설션 합니다.

##  <a name="setat"></a>  CTypedPtrArray::SetAt

이 멤버 함수 호출 `BASE_CLASS` **:: SetAt**합니다.

```
void SetAt(
    INT_PTR nIndex,
    TYPE ptr);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
0 보다 크거나 같은 경우에 정수 인덱스에서 반환 된 값 보다 작거나 [CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)합니다.

*TYPE*<br/>
기본 클래스 배열에 저장 된 요소의 형식입니다.

*ptr*<br/>
nIndex 배열에 삽입할 요소에 대 한 포인터입니다. NULL 값이 허용 됩니다.

### <a name="remarks"></a>설명

설명, 자세한 [CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat)합니다.

##  <a name="setatgrow"></a>  CTypedPtrArray::SetAtGrow

이 멤버 함수 호출 `BASE_CLASS` **:: SetAtGrow**합니다.

```
void SetAtGrow(
    INT_PTR nIndex,
    TYPE newElement);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
정수 인덱스는 0 보다 크거나 같은 경우입니다.

*TYPE*<br/>
기본 클래스 배열에 저장 된 요소의 형식입니다.

*newElement*<br/>
이 배열에 추가할 개체 포인터입니다. A **NULL** 값이 허용 됩니다.

### <a name="remarks"></a>설명

설명, 자세한 [CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)합니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 수집](../../overview/visual-cpp-samples.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CPtrArray 클래스](../../mfc/reference/cptrarray-class.md)<br/>
[CObArray 클래스](../../mfc/reference/cobarray-class.md)
