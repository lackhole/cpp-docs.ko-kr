---
title: max_variable_size 클래스
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::max_variable_size
- allocators/stdext::max_variable_size::allocated
- allocators/stdext::max_variable_size::deallocated
- allocators/stdext::max_variable_size::full
- allocators/stdext::max_variable_size::released
- allocators/stdext::max_variable_size::saved
helpviewer_keywords:
- stdext::max_variable_size
- stdext::max_variable_size [C++], allocated
- stdext::max_variable_size [C++], deallocated
- stdext::max_variable_size [C++], full
- stdext::max_variable_size [C++], released
- stdext::max_variable_size [C++], saved
ms.assetid: 9f2e9df0-4148-4b37-bc30-f8eca0ef86ae
ms.openlocfilehash: a7fde40352a878575ddce8b48b4c97093ae7a960
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412932"
---
# <a name="maxvariablesize-class"></a>max_variable_size 클래스

[freelist](../standard-library/freelist-class.md) 개체를 할당된 메모리 블록의 수에 거의 비례하는 최대 길이로 제한하는 [max 클래스](../standard-library/allocators-header.md) 개체를 설명합니다.

## <a name="syntax"></a>구문

```cpp
class max_variable_size
```

### <a name="constructors"></a>생성자

|생성자|설명|
|-|-|
|[max_variable_size](#max_variable_size)|`max_variable_size` 형식의 개체를 생성합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|설명|
|-|-|
|[allocated](#allocated)|할당된 메모리 블록의 수를 늘립니다.|
|[deallocated](#deallocated)|할당된 메모리 블록의 수를 줄입니다.|
|[full](#full)|사용 가능한 목록에 더 많은 메모리 블록을 추가할지 여부를 지정하는 값을 반환합니다.|
|[released](#released)|사용 가능한 목록에서 메모리 블록의 수를 줄입니다.|
|[saved](#saved)|사용 가능한 목록에서 메모리 블록의 수를 늘립니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<allocators>

**네임스페이스:** stdext

## <a name="allocated"></a>  max_variable_size::allocated

할당된 메모리 블록의 수를 늘립니다.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*_Nx*|증분 값입니다.|

### <a name="remarks"></a>설명

이 멤버 함수 추가 *_Nx* 저장된 된 값에 `_Nallocs`입니다. 이 멤버 함수를 호출 하 여 성공적으로 호출할 때마다 `cache_freelist::allocate` 운영자에 게 **새**합니다. 인수 *_Nx* 연산자가 할당 하는 청크에서 메모리 블록 수가 **새**합니다.

## <a name="deallocated"></a>  max_variable_size::deallocated

할당된 메모리 블록의 수를 줄입니다.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*_Nx*|증분 값입니다.|

### <a name="remarks"></a>설명

멤버 함수를 뺍니다 *_Nx* 저장된 된 값에서 `_Nallocs`합니다. 이 멤버 함수는 호출할 때마다 호출 됩니다 `cache_freelist::deallocate` 운영자에 게 **삭제**합니다. 인수 *_Nx* 연산자가 할당 취소 하는 청크에서 메모리 블록 수가 **삭제**합니다.

## <a name="full"></a>  max_variable_size::full

사용 가능한 목록에 더 많은 메모리 블록을 추가할지 여부를 지정하는 값을 반환합니다.

```cpp
bool full();
```

### <a name="return-value"></a>반환 값

**true 이면** 경우 `_Nallocs / 16 + 16 <= _Nblocks`합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 `cache_freelist::deallocate`에서 호출됩니다. 호출 반환 하는 경우 **true**를 `deallocate` false를 반환 하는 경우 사용 가능한 목록;에서 메모리 블록을 배치 `deallocate` 호출 연산자 **삭제** 할당을 취소 하려면 블록입니다.

## <a name="max_variable_size"></a>  max_variable_size::max_variable_size

`max_variable_size` 형식의 개체를 생성합니다.

```cpp
max_variable_size();
```

### <a name="remarks"></a>설명

이 생성자는 저장된 값 `_Nblocks` 및 `_Nallocs`를 0으로 초기화합니다.

## <a name="released"></a>  max_variable_size::released

사용 가능한 목록에서 메모리 블록의 수를 줄입니다.

```cpp
void released();
```

### <a name="remarks"></a>설명

이 멤버 함수는 저장된 값 `_Nblocks`를 줄입니다. 현재 max 클래스의 `released` 멤버 함수는 사용 가능한 목록에서 메모리 블록을 제거할 때마다 `cache_freelist::allocate`에서 호출됩니다.

## <a name="saved"></a>  max_variable_size::saved

사용 가능한 목록에서 메모리 블록의 수를 늘립니다.

```cpp
void saved();
```

### <a name="remarks"></a>설명

이 멤버 함수는 저장된 값 `_Nblocks`를 늘립니다. 이 멤버 함수는 사용 가능한 목록에 메모리 블록을 넣을 때마다 `cache_freelist::deallocate`에서 호출됩니다.

## <a name="see-also"></a>참고자료

[\<allocators>](../standard-library/allocators-header.md)<br/>
