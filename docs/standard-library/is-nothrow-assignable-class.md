---
title: is_nothrow_assignable 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_assignable
helpviewer_keywords:
- is_nothrow_assignable
ms.assetid: aa3aca92-308b-4b1d-b3f3-c54216c48fe7
ms.openlocfilehash: c59c3623f9c9548a7b7e59d0c56a2acd4d3883a3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383622"
---
# <a name="isnothrowassignable-class"></a>is_nothrow_assignable 클래스

값이 있는지 여부를 테스트 *에서* 형식에 할당할 수 있습니다 *하려면* 유형 및 할당은 throw 되지 않는 합니다.

## <a name="syntax"></a>구문

```cpp
template <class To, class From>
struct is_nothrow_assignable;
```

### <a name="parameters"></a>매개 변수

*대상*<br/>
할당을 받는 개체의 형식입니다.

*From*<br/>
값을 제공하는 개체의 형식입니다.

## <a name="remarks"></a>설명

`declval<To>() = declval<From>()` 식은 올바른 형식이어야 하며 throw되지 않는 것으로 컴파일러에 알려져 있어야 합니다. 둘 다 *에서* 하 고 *에* 완전 한 형식 이어야 합니다 **void**, 또는 범위를 알 수 없는 배열입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
