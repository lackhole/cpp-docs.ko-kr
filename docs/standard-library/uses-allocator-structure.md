---
title: uses_allocator 구조체
ms.date: 11/04/2016
f1_keywords:
- future/std::uses_allocator
ms.assetid: c418f002-62e9-4806-b70c-41c663cae583
ms.openlocfilehash: 4dc0094d46c005e4af62924bc785a05b3ca43090
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454665"
---
# <a name="usesallocator-structure"></a>uses_allocator 구조체

항상 true인 특수화입니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty, class Alloc>
struct uses_allocator<promise<Ty>, Alloc> : true_type;
template <class Ty, class Alloc>
struct uses_allocator<packaged_task<Ty>, Alloc> : true_type;
```

## <a name="requirements"></a>요구 사항

**헤더:** \<이후 >

**네임스페이스:** std

## <a name="specializations"></a>특수화

### <a name="tuple"></a>\<튜플 >

```cpp
template <class... Types, class Alloc>
struct uses_allocator<tuple<Types...>, Alloc>;
```

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)\
[\<future>](../standard-library/future.md)
