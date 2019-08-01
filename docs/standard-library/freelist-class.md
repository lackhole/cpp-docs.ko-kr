---
title: freelist 클래스
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::freelist
- allocators/stdext::freelist::pop
- allocators/stdext::freelist::push
helpviewer_keywords:
- stdext::freelist
- stdext::freelist [C++], pop
- stdext::freelist [C++], push
ms.assetid: 8ad7e35c-4c80-4479-8ede-1a2497b06d71
ms.openlocfilehash: 8a504f58f9f64aa8b0d26b17090387c5c2b5de21
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454136"
---
# <a name="freelist-class"></a>freelist 클래스

메모리 블록의 목록을 관리합니다.

## <a name="syntax"></a>구문

```cpp
template <std::size_t Sz, class Max>
class freelist : public Max
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*Sz*|할당할 배열의 요소 수입니다.|
|*Max*|사용 가능 목록에 저장할 최대 요소 수를 나타내는 최대 클래스입니다. 최대 클래스는 [max_none](../standard-library/max-none-class.md), [max_unbounded](../standard-library/max-unbounded-class.md), [max_fixed_size](../standard-library/max-fixed-size-class.md) 또는 [max_variable_size](../standard-library/max-variable-size-class.md)가 될 수 있습니다.|

## <a name="remarks"></a>설명

이 템플릿 클래스는 *max*로 전달 된 최대 클래스에 의해 결정 되는 목록의 최대 길이를 사용 하 여 *Sz* 크기의 메모리 블록 목록을 관리 합니다.

### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[freelist](#freelist)|`freelist` 형식의 개체를 생성합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|Description|
|-|-|
|[pop](#pop)|사용 가능 목록에서 첫 번째 메모리 블록을 제거합니다.|
|[push](#push)|목록에 메모리 블록을 추가합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<allocators>

**네임스페이스:** stdext

## <a name="freelist"></a>  freelist::freelist

`freelist` 형식의 개체를 생성합니다.

```cpp
freelist();
```

### <a name="remarks"></a>설명

## <a name="pop"></a>  freelist::pop

사용 가능 목록에서 첫 번째 메모리 블록을 제거합니다.

```cpp
void *pop();
```

### <a name="return-value"></a>반환 값

목록에서 제거된 메모리 블록의 포인터를 반환합니다.

### <a name="remarks"></a>설명

목록이 비어 있으면 멤버 함수는 NULL을 반환 합니다. 그렇지 않으면 목록에서 첫 번째 메모리 블록을 제거합니다.

## <a name="push"></a>  freelist::push

목록에 메모리 블록을 추가합니다.

```cpp
bool push(void* ptr);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*ptr*|사용 가능 목록에 추가할 메모리 블록의 포인터입니다.|

### <a name="return-value"></a>반환 값

max 클래스의 `full` 함수가 **false를**반환 하면 true이 고, 그렇지 않으면 **false**를 반환합니다.`push`

### <a name="remarks"></a>설명

Max 클래스의 함수가false를반환하는경우이멤버함수는ptr에서가리키는메모리블록을목록의맨`full` 위에 추가 합니다.

## <a name="see-also"></a>참고자료

[\<allocators>](../standard-library/allocators-header.md)
