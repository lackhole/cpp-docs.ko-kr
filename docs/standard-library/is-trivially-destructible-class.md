---
title: is_trivially_destructible 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_destructible
helpviewer_keywords:
- is_trivially_destructible
ms.assetid: 3f7a787d-2448-40c5-ac51-a228318e02ce
ms.openlocfilehash: 6a978b7cc32e6de3d4b1d811b9aa6f52cf0370d7
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459635"
---
# <a name="istriviallydestructible-class"></a>is_trivially_destructible 클래스

형식이 일반적으로 소멸 가능한지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct is_trivially_destructible;
```

### <a name="parameters"></a>매개 변수

*트*\
형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스는 *T* 형식이 소멸 가능한 형식인 경우 true이 고, 소멸자는 특수 작업을 사용 하지 않는 컴파일러에 알려집니다. 그렇지 않으면 false입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)
