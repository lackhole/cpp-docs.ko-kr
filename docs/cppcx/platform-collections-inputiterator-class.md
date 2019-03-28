---
title: Platform::Collections::InputIterator 클래스
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::InputIterator::InputIterator
helpviewer_keywords:
- InputIterator Class
ms.assetid: ef72eea4-32a9-42b9-8119-ce87dbdcd3be
ms.openlocfilehash: 49b131b01fe3d9cad5f8366fd4cc0c110b5d060c
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565141"
---
# <a name="platformcollectionsinputiterator-class"></a>Platform::Collections::InputIterator 클래스

Windows Runtime에서 파생 된 컬렉션에 대 한 표준 템플릿 라이브러리 InputIterator를 제공 합니다.

## <a name="syntax"></a>구문

```
template <typename X>
class InputIterator;
```

#### <a name="parameters"></a>매개 변수

*X*<br/>
InputIterator 템플릿 클래스의 형식 이름입니다.

### <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|`difference_type`|포인터 차이(ptrdiff_t)입니다.|
|`iterator_category`|입력 반복기의 범주(::std::input_iterator_tag)입니다.|
|`pointer`|에 대 한 포인터를 `const X`|
|`reference`|에 대 한 참조는 `const X`|
|`value_type`|`X` 형식 이름입니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[InputIterator::InputIterator](#ctor)|InputIterator 클래스의 새 인스턴스를 초기화합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[InputIterator::operator!= 연산자](#operator-inequality)|현재 InputIterator가 지정된 InputIterator와 같지 않은지 여부를 나타냅니다.|
|[InputIterator::operator* 연산자](#operator-dereference)|현재 InputIterator가 지정하는 요소에 대한 참조를 검색합니다.|
|[InputIterator::operator++ 연산자](#operator-increment)|현재 InputIterator를 증가시킵니다.|
|[InputIterator::operator== 연산자](#operator-equality)|현재 InputIterator가 지정된 InputIterator와 같은지 여부를 나타냅니다.|
|[InputIterator::operator-> 연산자](#operator-arrow)|현재 InputIterator가 참조하는 요소의 주소를 검색합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`InputIterator`

### <a name="requirements"></a>요구 사항

**헤더:** collection.h

**네임스페이스:** Platform::Collections

## <a name="ctor"></a>  Inputiterator:: Inputiterator 생성자

InputIterator 클래스의 새 인스턴스를 초기화합니다.

### <a name="syntax"></a>구문

```
InputIterator();
explicit InputIterator(Windows::Foundation::Collections<X>^ iterator);
```

### <a name="parameters"></a>매개 변수

*iterator*<br/>
반복기 개체입니다.

## <a name="operator-arrow"></a>  InputIterator::operator-&gt; Operator

현재 InputIterator가 지정하는 요소의 주소를 검색합니다.

### <a name="syntax"></a>구문

```
pointer operator->() const;
```

### <a name="return-value"></a>반환 값

현재 InputIterator가 지정하는 요소의 주소입니다.

## <a name="operator-dereference"></a>  InputIterator::operator\* Operator

현재 InputIterator가 지정하는 요소에 대한 참조를 검색합니다.

### <a name="syntax"></a>구문

```
reference operator*() const;
```

### <a name="return-value"></a>반환 값

현재 InputIterator가 지정하는 요소입니다.

## <a name="operator-equality"></a>  InputIterator::operator== Operator

현재 InputIterator가 지정된 InputIterator와 같은지 여부를 나타냅니다.

### <a name="syntax"></a>구문

```
bool operator== (const InputIterator& other) const;
```

### <a name="parameters"></a>매개 변수

*other*<br/>
다른 InputIterator입니다.

### <a name="return-value"></a>반환 값

**true 이면** 현재 inputiterator가 같으면 *다른*이 고, 그렇지 않으면 **false**합니다.

## <a name="operator-increment"></a>  Inputiterator:: Operator + + 연산자

현재 InputIterator를 증가시킵니다.

### <a name="syntax"></a>구문

```
InputIterator& operator++();
InputIterator operator++(int);
```

### <a name="return-value"></a>반환 값

첫 번째 구문은 현재 InputIterator를 증가시킨 다음 반환합니다. 두 번째 구문은 현재 InputIterator의 복사본을 반환한 다음 현재 InputIterator를 증가시킵니다.

### <a name="remarks"></a>설명

첫 번째 InputIterator 구문은 현재 InputIterator를 사전에 증가시킵니다.

두 번째 구문은 현재 InputIterator를 사후에 증가시킵니다. 두 번째 구문의 `int` 형식은 실제 정수 연산자가 아니라 후위 증가 연산을 나타냅니다.

## <a name="operator-inequality"></a>  Inputiterator:: Operator! = 연산자

현재 InputIterator가 지정된 InputIterator와 같지 않은지 여부를 나타냅니다.

### <a name="syntax"></a>구문

```
bool operator!=(const InputIterator& other) const;
```

### <a name="parameters"></a>매개 변수

*other*<br/>
다른 InputIterator입니다.

### <a name="return-value"></a>반환 값

**true 이면** 현재 inputiterator가 같지 않은 경우 *다른*이 고, 그렇지 않으면 **false**합니다.

## <a name="see-also"></a>참고자료

[플랫폼 Namespace](platform-namespace-c-cx.md)
