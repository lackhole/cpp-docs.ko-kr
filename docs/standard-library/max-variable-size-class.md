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
ms.openlocfilehash: f8b3c61676f784bf9369c22b5db97d7b251f7ac6
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447291"
---
# <a name="maxvariablesize-class"></a>max_variable_size 클래스

[freelist](../standard-library/freelist-class.md) 개체를 할당된 메모리 블록의 수에 거의 비례하는 최대 길이로 제한하는 [max 클래스](../standard-library/allocators-header.md) 개체를 설명합니다.

## <a name="syntax"></a>구문

```cpp
class max_variable_size
```

### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[max_variable_size](#max_variable_size)|`max_variable_size` 형식의 개체를 생성합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|Description|
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

이 멤버 함수는 저장 된 값 `_Nallocs`에 *_nx* 를 추가 합니다. 이 멤버 함수는의 각 호출이 `cache_freelist::allocate` 성공한 후에 호출 됩니다 **.** 인수 *_Nx* 는 operator **new**에 의해 할당 된 청크의 메모리 블록 수입니다.

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

멤버 함수는 저장 된 값 `_Nallocs`에서 *_nx* 를 뺍니다. 이 멤버 함수는 `cache_freelist::deallocate` 에 대 한 각 호출 후 operator **delete**를 호출 하 여 호출 됩니다. *_Nx* 인수는 operator **delete**에 의해 할당 취소 된 청크의 메모리 블록 수입니다.

## <a name="full"></a>  max_variable_size::full

사용 가능한 목록에 더 많은 메모리 블록을 추가할지 여부를 지정하는 값을 반환합니다.

```cpp
bool full();
```

### <a name="return-value"></a>반환 값

이면`_Nallocs / 16 + 16 <= _Nblocks`true입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 `cache_freelist::deallocate`에서 호출됩니다. 호출에서 **true**를 `deallocate` 반환 하면는 사용 가능한 목록에 메모리 블록을 저장 하 고 false를 `deallocate` 반환 하면 **delete** 연산자를 호출 하 여 블록의 할당을 취소 합니다.

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

[\<allocators>](../standard-library/allocators-header.md)
