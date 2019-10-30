---
title: cache_chunklist 클래스
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::cache_chunklist
- allocators/stdext::cache_chunklist::allocate
- allocators/stdext::cache_chunklist::deallocate
helpviewer_keywords:
- stdext::cache_chunklist
- stdext::cache_chunklist [C++], allocate
- stdext::cache_chunklist [C++], deallocate
ms.assetid: af19eccc-4ae7-4a34-bbb2-81e397424cb9
ms.openlocfilehash: 035e5153b4e4c84743a64bcc9cec24920a6a0336
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688358"
---
# <a name="cache_chunklist-class"></a>cache_chunklist 클래스

단일 크기의 메모리 블록을 할당하고 할당을 취소하는 [블록 할당자](../standard-library/allocators-header.md)를 정의합니다.

## <a name="syntax"></a>구문

```cpp
template <std::size_t Sz, std::size_t Nelts = 20>
class cache_chunklist
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*Sz*|할당할 배열의 요소 수입니다.|

## <a name="remarks"></a>주의

이 클래스 템플릿은 **new 연산자**를 사용하여 원시 메모리의 청크를 할당하고, 필요한 경우 메모리 블록에 대한 저장소를 할당하는 블록을 할당합니다. 각 청크에 대한 별도의 사용 가능한 목록에 할당 취소된 메모리 블록을 저장하고, **delete 연산자**를 사용하여 메모리 블록을 사용하고 있지 않은 경우 청크의 할당을 취소합니다.


각 메모리 블록은 사용 가능한 메모리의 *Sz* 바이트와 해당 메모리가 속한 청크에 대한 포인터를 포함합니다. 각 청크는 `Nelts` 메모리 블록, 3 개의 포인터, int, 그리고 **new 연산자** 및 **delete 연산자**에 필요한 데이터를 포함합니다.	


### <a name="constructors"></a>생성자

|생성자|설명|
|-|-|
|[cache_chunklist](#cache_chunklist)|`cache_chunklist` 형식의 개체를 생성합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|설명|
|-|-|
|[allocate](#allocate)|메모리 블록을 할당합니다.|
|[deallocate](#deallocate)|지정된 위치부터 시작하여 스토리지에서 지정된 개수의 개체를 해제합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<allocators>

**네임스페이스:** stdext

## <a name="allocate"></a>  cache_chunklist::allocate

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

### <a name="remarks"></a>주의

## <a name="cache_chunklist"></a>  cache_chunklist::cache_chunklist

`cache_chunklist` 형식의 개체를 생성합니다.

```cpp
cache_chunklist();
```

### <a name="remarks"></a>주의

## <a name="deallocate"></a>  cache_chunklist::deallocate

지정된 위치부터 시작하여 스토리지에서 지정된 개수의 개체를 해제합니다.

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*ptr*|스토리지에서 할당을 취소할 첫 번째 개체에 대한 포인터입니다.|
|*count*|스토리지에서 할당을 취소할 개체의 수입니다.|

### <a name="remarks"></a>주의

## <a name="see-also"></a>참조

[\<allocators>](../standard-library/allocators-header.md)
