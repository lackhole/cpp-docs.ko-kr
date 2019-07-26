---
title: is_nothrow_destructible 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_destructible
helpviewer_keywords:
- is_nothrow_destructible
ms.assetid: 0bbd8a28-e312-4d72-bd28-aac027f974d3
ms.openlocfilehash: 44de1f1fae1ea542aa247c0b39f04ee6bbd6308a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455901"
---
# <a name="isnothrowdestructible-class"></a>is_nothrow_destructible 클래스

형식이 소멸 가능하며 소멸자가 throw되지 않는 것으로 컴파일러에 알려져 있는지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct is_nothrow_destructible;
```

### <a name="parameters"></a>매개 변수

*트*\
형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스는 *T* 형식이 소멸 가능한 형식인 경우 true이 고, 소멸자는 throw 하지 않도록 컴파일러에 알려집니다. 그렇지 않으면 false입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)
