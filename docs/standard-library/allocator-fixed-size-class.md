---
title: allocator_fixed_size 클래스
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocators::allocator_fixed_size
- allocators/stdext::allocator_fixed_size
- stdext::allocators::allocator_fixed_size
helpviewer_keywords:
- stdext::allocators [C++], allocator_fixed_size
- stdext::allocator_fixed_size
ms.assetid: 138f3ef8-b0b3-49c3-9486-58f2213c172f
ms.openlocfilehash: 5ee506838ea723b82f04bba301c19c0149d986bf
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451003"
---
# <a name="allocatorfixedsize-class"></a>allocator_fixed_size 클래스

[Max_fixed_size](../standard-library/max-fixed-size-class.md)에 의해 관리되는 길이를 사용하는 [cache_freelist](../standard-library/cache-freelist-class.md) 형식의 캐시를 사용하여 *Type* 형식인 개체에 대한 스토리지 할당 및 해제를 관리하는 개체에 대해 설명합니다.

## <a name="syntax"></a>구문

```cpp
template <class Type>
class allocator_fixed_size;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*Type*|할당자에 의해 할당된 요소 형식입니다.|

## <a name="remarks"></a>설명

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) 매크로는 다음 명령문에서 이 클래스를 *name* 매개 변수로 전달합니다:`ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_fixed_size<10>), SYNC_DEFAULT, allocator_fixed_size);`

## <a name="requirements"></a>요구 사항

**헤더:** \<allocators>

**네임스페이스:** stdext

## <a name="see-also"></a>참고자료

[\<allocators>](../standard-library/allocators-header.md)
