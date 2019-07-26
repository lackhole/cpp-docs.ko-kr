---
title: cache_suballoc 클래스
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::cache_suballoc
- allocators/stdext::cache_suballoc::allocate
- allocators/stdext::cache_suballoc::deallocate
helpviewer_keywords:
- stdext::cache_suballoc
- stdext::cache_suballoc [C++], allocate
- stdext::cache_suballoc [C++], deallocate
ms.assetid: 9ea9c5e9-1dcc-45d0-b3a7-a56a93d88898
ms.openlocfilehash: aa0ceda69fc169593719c3a4f81d308bb6cde284
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449651"
---
# <a name="cachesuballoc-class"></a>cache_suballoc 클래스

단일 크기의 메모리 블록을 할당하고 할당 취소하는 [블록 할당자](../standard-library/allocators-header.md)를 정의합니다.

## <a name="syntax"></a>구문

```cpp
template <std::size_t Sz, size_t Nelts = 20>
class cache_suballoc
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*Sz*|할당할 배열의 요소 수입니다.|

## <a name="remarks"></a>설명

Cache_suballoc 템플릿 클래스는 사용 가능한 목록에 할당 취소 된 메모리 블록을 저장 하 고 `freelist<sizeof(Type), max_unbounded>`,를 사용 하 고, 사용 가능한 목록이 비어 있을 때 **operator new** 로 할당 된 더 큰 청크의 메모리 블록을 할당 합니다.

각 청크는 `Sz * Nelts` 바이트의 사용 가능한 메모리와 **operator new** 및 **operator delete** 가 필요한 데이터를 보유 합니다. 할당된 청크는 해제되지 않습니다.

### <a name="constructors"></a>생성자

|생성자|설명|
|-|-|
|[cache_suballoc](#cache_suballoc)|`cache_suballoc` 형식의 개체를 생성합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|설명|
|-|-|
|[allocate](#allocate)|메모리 블록을 할당합니다.|
|[deallocate](#deallocate)|지정된 위치부터 시작하여 스토리지에서 지정된 개수의 개체를 해제합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<allocators>

**네임스페이스:** stdext

## <a name="allocate"></a>  cache_suballoc::allocate

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

## <a name="cache_suballoc"></a>  cache_suballoc::cache_suballoc

`cache_suballoc` 형식의 개체를 생성합니다.

```cpp
cache_suballoc();
```

### <a name="remarks"></a>설명

## <a name="deallocate"></a>  cache_suballoc::deallocate

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

[\<allocators>](../standard-library/allocators-header.md)
