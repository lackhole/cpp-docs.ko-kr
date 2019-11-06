---
title: max_none 클래스
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::max_none
- allocators/stdext::max_none::allocated
- allocators/stdext::max_none::deallocated
- allocators/stdext::max_none::full
- allocators/stdext::max_none::released
- allocators/stdext::max_none::saved
helpviewer_keywords:
- stdext::max_none
- stdext::max_none [C++], allocated
- stdext::max_none [C++], deallocated
- stdext::max_none [C++], full
- stdext::max_none [C++], released
- stdext::max_none [C++], saved
ms.assetid: 12ab5376-412e-479c-86dc-2c3d6a3559b6
ms.openlocfilehash: b296c641be68efac7410328a448a4ad2bd0fa88e
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626820"
---
# <a name="max_none-class"></a>max_none 클래스

[freelist](../standard-library/freelist-class.md) 개체를 최대 길이 0으로 제한하는 [max 클래스](../standard-library/allocators-header.md) 개체를 설명합니다.

## <a name="syntax"></a>구문

```cpp
template <std::size_t Max>
class max_none
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*Max*|`freelist`에 저장할 요소의 최대 수를 결정하는 max 클래스입니다.|

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

## <a name="allocated"></a>  max_none::allocated

할당된 메모리 블록의 수를 늘립니다.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*_ Nx*|증분 값입니다.|

### <a name="remarks"></a>주의

이 멤버 함수는 아무 작업도 수행하지 않습니다. `cache_freelist::allocate`는 **new**연산자를 호출 하 여 각 호출이 성공한 후에 호출 됩니다. 인수 *_Nx* 는 operator **new**에 의해 할당 된 청크의 메모리 블록 수입니다.

## <a name="deallocated"></a>  max_none::deallocated

할당된 메모리 블록의 수를 줄입니다.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*_ Nx*|증분 값입니다.|

### <a name="remarks"></a>주의

멤버 함수는 아무 작업도 수행하지 않습니다. 이 멤버 함수는 각 호출에서 operator **delete**로 `cache_freelist::deallocate` 호출 된 후에 호출 됩니다. *_Nx* 인수는 operator **delete**에 의해 할당 취소 된 청크의 메모리 블록 수입니다.

## <a name="full"></a>  max_none::full

사용 가능한 목록에 더 많은 메모리 블록을 추가할지 여부를 지정하는 값을 반환합니다.

```cpp
bool full();
```

### <a name="return-value"></a>반환 값

이 멤버 함수는 항상 **true**를 반환 합니다.

### <a name="remarks"></a>주의

이 멤버 함수는 `cache_freelist::deallocate`에서 호출됩니다. 호출에서 **true**를 반환 하는 경우 `deallocate`는 사용 가능한 목록에 메모리 블록을 배치 합니다. **false**를 반환 하는 경우 **delete** 연산자를 호출 하 여 블록의 할당을 취소 `deallocate`.

## <a name="released"></a>  max_none::released

사용 가능한 목록에서 메모리 블록의 수를 줄입니다.

```cpp
void released();
```

### <a name="remarks"></a>주의

이 멤버 함수는 아무 작업도 수행하지 않습니다. 현재 max 클래스의 `released` 멤버 함수는 사용 가능한 목록에서 메모리 블록을 제거할 때마다 `cache_freelist::allocate`에서 호출됩니다.

## <a name="saved"></a>  max_none::saved

사용 가능한 목록에서 메모리 블록의 수를 늘립니다.

```cpp
void saved();
```

### <a name="remarks"></a>주의

이 멤버 함수는 아무 작업도 수행하지 않습니다. 이 멤버 함수는 사용 가능한 목록에 메모리 블록을 넣을 때마다 `cache_freelist::deallocate`에서 호출됩니다.

## <a name="see-also"></a>참조

[\<allocators>](../standard-library/allocators-header.md)
