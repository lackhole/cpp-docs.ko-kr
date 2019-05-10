---
title: allocator_chunklist 클래스
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocator_chunklist
- allocators/stdext::allocators::allocator_chunklist
helpviewer_keywords:
- stdext::allocator_chunklist
- stdext::allocators [C++], allocator_chunklist
ms.assetid: ea72ed0a-dfdb-4c8b-8096-e4baf567b80f
ms.openlocfilehash: d52eeb1f34938958c9716692ed6bbd7d830c93b5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411060"
---
# <a name="allocatorchunklist-class"></a>allocator_chunklist 클래스

[cache_chunklist](../standard-library/cache-chunklist-class.md) 유형의 캐시를 사용하여 개체에 대한 스토리지 할당 및 해제를 관리하는 개체를 설명합니다.

## <a name="syntax"></a>구문

```cpp
template <class Type>
class allocator_chunklist;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*Type*|할당자에 의해 할당된 요소 형식입니다.|

## <a name="remarks"></a>설명

합니다 [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) 매크로로이 클래스를 전달 합니다 *이름* 다음 문에서 매개 변수: `ALLOCATOR_DECL(CACHE_CHUNKLIST, SYNC_DEFAULT, allocator_chunklist);`

## <a name="requirements"></a>요구 사항

**헤더:** \<allocators>

**네임스페이스:** stdext

## <a name="see-also"></a>참고자료

[\<allocators>](../standard-library/allocators-header.md)<br/>
