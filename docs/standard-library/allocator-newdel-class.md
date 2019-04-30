---
title: allocator_newdel 클래스
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocators::allocator_newdel
- allocators/stdext::allocator_newdel
- stdext::allocators::allocator_newdel
helpviewer_keywords:
- stdext::allocators [C++], allocator_newdel
- stdext::allocator_newdel
ms.assetid: 62666cd2-3afe-49f7-9dd1-9bbbb154da98
ms.openlocfilehash: eac2fb993eb3e9aab5d043debe6402576d7b49b0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411021"
---
# <a name="allocatornewdel-class"></a>allocator_newdel 클래스

사용 하는 할당자를 구현 **delete 연산자** 메모리 할당을 취소 하려면 블록 및 **new 연산자** 메모리 블록을 할당 하려면.

## <a name="syntax"></a>구문

```cpp
template <class Type>
class allocator_newdel;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*Type*|할당자에 의해 할당된 요소 형식입니다.|

## <a name="remarks"></a>설명

합니다 [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) 매크로로이 클래스를 전달 합니다 *이름* 다음 문에서 매개 변수: `ALLOCATOR_DECL(CACHE_FREELIST stdext::allocators::max_none), SYNC_DEFAULT, allocator_newdel);`

## <a name="requirements"></a>요구 사항

**헤더:** \<allocators>

**네임스페이스:** stdext

## <a name="see-also"></a>참고자료

[\<allocators>](../standard-library/allocators-header.md)<br/>
