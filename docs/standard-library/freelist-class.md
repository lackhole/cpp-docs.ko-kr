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
ms.openlocfilehash: ef1f2e617e93869a1084dc030c6496c819f1ed96
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159394"
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

이 템플릿 클래스는 크기의 메모리 블록의 목록을 관리 *Sz* 전달 된 최대 클래스에 의해 결정 된 목록의 최대 길이 사용 하 여 *Max*합니다.

### <a name="constructors"></a>생성자

|생성자|설명|
|-|-|
|[freelist](#freelist)|`freelist` 형식의 개체를 생성합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|설명|
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

멤버 함수는 목록이 비어 있으면 NULL을 반환 합니다. 그렇지 않으면 목록에서 첫 번째 메모리 블록을 제거합니다.

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

**true** 경우는 `full` 최대 클래스의 반환 **false**이 고, 그렇지 않으면 합니다 `push` 함수에서 반환 **false**합니다.

### <a name="remarks"></a>설명

경우는 `full` max 클래스의 반환 **false**를 가리키는 메모리 블록을 추가 하는이 멤버 함수 *ptr* 목록 헤드에 합니다.

## <a name="see-also"></a>참고자료

[\<allocators>](../standard-library/allocators-header.md)<br/>
