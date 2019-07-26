---
title: is_assignable 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_assignable
helpviewer_keywords:
- is_assignable
ms.assetid: 53444287-c8be-4ad2-9487-a85c066a4f84
ms.openlocfilehash: 33b0ce6112119c935ff70e5d619b284acc6ee8c2
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456676"
---
# <a name="isassignable-class"></a>is_assignable 클래스

`From` 형식의 값을 `To` 형식에 할당할 수 있는지 여부를 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class To, class From>
struct is_assignable;
```

### <a name="parameters"></a>매개 변수

*받는 사람*\
할당을 받는 개체의 형식입니다.

*보낸 사람*\
값을 제공하는 개체의 형식입니다.

## <a name="remarks"></a>설명

평가되지 않은 `declval<To>() = declval<From>()` 식은 올바른 형식이어야 합니다. 및 `From` 둘`To` 다 완전 한 형식, **void**또는 알 수 없는 바인딩된 배열 이어야 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)
