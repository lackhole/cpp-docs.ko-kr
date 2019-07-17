---
title: '&lt;new&gt; 형식 정의'
ms.date: 11/04/2016
f1_keywords:
- new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
ms.openlocfilehash: 80123bc35422984ef92bdba6da45052d3461b1d7
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245151"
---
# <a name="ltnewgt-typedefs"></a>&lt;new&gt; 형식 정의

## <a name="hardware_constructive_interference_size"></a> hardware_constructive_interference_size

```cpp
inline constexpr size_t hardware_constructive_interference_size = implementation-defined;
```

### <a name="remarks"></a>설명

이 숫자는 최대 동시 스레드에 의해 임시 위치를 사용 하 여 액세스 하는 두 개체가 차지 하는 인접 한 메모리의 크기를 추천 합니다. 이상 이어야 `alignof(max_align_t)`합니다.

### <a name="example"></a>예제

```cpp
struct together { 
    atomic<int> dog;
    int puppy;
};

struct kennel {
    // Other data members...
    alignas(sizeof(together)) together pack;
    // Other data members...
};

static_assert(sizeof(together) <= hardware_constructive_interference_size);
```

## <a name="hardware_destructive_interference_size"></a> hardware_destructive_interference_size

```cpp
inline constexpr size_t hardware_destructive_interference_size = implementation-defined;
```

### <a name="remarks"></a>설명

이 숫자는 구현에 의해 도입 된 경합으로 인 한 추가 성능 저하를 방지 하려면 동시에 액세스 하지 않는 두 개체 간의 최소 권장 되는 오프셋입니다. 이상 이어야 `alignof(max_align_t)`합니다.

### <a name="example"></a>예제

```cpp
struct keep_apart {
    alignas(hardware_destructive_interference_size) atomic<int> cat;
    alignas(hardware_destructive_interference_size) atomic<int> dog;
};
```

## <a name="new_handler"></a> new_handler

이 형식은 새 처리기로 사용하기에 적합한 함수를 가리킵니다.

```cpp
typedef void (*new_handler)();
```

### <a name="remarks"></a>설명

이 유형의 처리기 함수는 호출한 **new 연산자** 또는 `operator new[]` 때 추가 저장소에 대 한 요청을 충족할 수 없습니다.

### <a name="example"></a>예제

`new_handler`를 반환 값으로 사용하는 방법의 예제는 [set_new_handler](../standard-library/new-functions.md#set_new_handler)를 참조하세요.
