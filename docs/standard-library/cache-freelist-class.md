---
title: cache_freelist 클래스
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::cache_freelist
- allocators/stdext::cache_freelist::allocate
- allocators/stdext::cache_freelist::deallocate
helpviewer_keywords:
- stdext::cache_freelist
- stdext::cache_freelist [C++], allocate
- stdext::cache_freelist [C++], deallocate
ms.assetid: 840694de-36ba-470f-8dae-2b723d5a8cd9
ms.openlocfilehash: 56fdfb191f9208a5ffa692e1d599545ddeaeb36c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352114"
---
# <a name="cachefreelist-class"></a>cache_freelist 클래스

단일 크기의 메모리 블록을 할당하고 할당 취소하는 [블록 할당자](../standard-library/allocators-header.md)를 정의합니다.

## <a name="syntax"></a>구문

```cpp
template <std::size_t Sz, class Max>
class cache_freelist
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*Sz*|할당할 배열의 요소 수입니다.|
|*Max*|사용 가능한 목록의 최대 크기를 나타내는 최대 클래스입니다. [max_fixed_size](../standard-library/max-fixed-size-class.md), [max_none](../standard-library/max-none-class.md), [max_unbounded](../standard-library/max-unbounded-class.md) 또는 [max_variable_size](../standard-library/max-variable-size-class.md)일 수 있습니다.|

## <a name="remarks"></a>설명

Cache_freelist 템플릿 클래스는 사용 가능한 메모리 블록 크기의 목록을 유지 관리 *Sz*합니다. 사용 하 여 사용 가능한 목록이 가득 **delete 연산자** 메모리를 할당 해제를 차단 합니다. 사용 하 여 사용 가능한 목록이 비어 있으면 **new 연산자** 새로운 메모리 블록을 할당 합니다. 사용 가능한 목록의 최대 크기에 전달 된 최대 클래스 클래스에 의해 결정 되는 *최대* 매개 변수입니다.

각 메모리 블록 보유 *Sz* 바이트의 사용 가능한 메모리 및 데이터는 **new 연산자** 및 **delete 연산자** 필요 합니다.

### <a name="constructors"></a>생성자

|생성자|설명|
|-|-|
|[cache_freelist](#cache_freelist)|`cache_freelist` 형식의 개체를 생성합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|설명|
|-|-|
|[allocate](#allocate)|메모리 블록을 할당합니다.|
|[deallocate](#deallocate)|지정된 위치부터 시작하여 스토리지에서 지정된 개수의 개체를 해제합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<allocators>

**네임스페이스:** stdext

## <a name="allocate"></a>  cache_freelist::allocate

메모리 블록을 할당합니다.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*count*|할당할 배열의 요소 수입니다.|

### <a name="return-value"></a>반환 값

할당된 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

## <a name="cache_freelist"></a>  cache_freelist::cache_freelist

`cache_freelist` 형식의 개체를 생성합니다.

```cpp
cache_freelist();
```

### <a name="remarks"></a>설명

## <a name="deallocate"></a>  cache_freelist::deallocate

지정된 위치부터 시작하여 스토리지에서 지정된 개수의 개체를 해제합니다.

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*ptr*|스토리지에서 할당을 취소할 첫 번째 개체에 대한 포인터입니다.|
|*count*|스토리지에서 할당을 취소할 개체의 수입니다.|

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[\<allocators>](../standard-library/allocators-header.md)<br/>
