---
title: allocator_unbounded 클래스
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocator_unbounded
- allocators/stdext::allocators::allocator_unbounded
helpviewer_keywords:
- allocator_unbounded class
ms.assetid: facbaea1-b320-4d99-96da-039b2642f352
ms.openlocfilehash: 4e5bf54b386a3c3fe4e2604a78437275707acbfd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179187"
---
# <a name="allocatorunbounded-class"></a>allocator_unbounded 클래스

저장소 할당 및 개체 형식에 대 한 해제를 관리 하는 개체를 설명 *형식* 형식의 캐시를 사용 하 여 [cache_freelist](../standard-library/cache-freelist-class.md) 관리 하는 길이가 [max_unbounded](../standard-library/max-unbounded-class.md).

## <a name="syntax"></a>구문

```cpp
template <class Type>
class allocator_unbounded;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*Type*|할당자에 의해 할당된 요소 형식입니다.|

## <a name="remarks"></a>설명

합니다 [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) 매크로로이 클래스를 전달 합니다 *이름* 다음 문에서 매개 변수: `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_unbounded), SYNC_DEFAULT, allocator_unbounded);`

## <a name="requirements"></a>요구 사항

**헤더:** \<allocators>

**네임스페이스:** stdext

## <a name="see-also"></a>참고자료

[\<allocators>](../standard-library/allocators-header.md)<br/>
