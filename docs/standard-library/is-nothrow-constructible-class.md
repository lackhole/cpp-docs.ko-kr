---
title: is_nothrow_constructible 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_constructible
helpviewer_keywords:
- is_nothrow_constructible
ms.assetid: 8be3f927-283e-4d67-95a5-8bf5dc4e7a3d
ms.openlocfilehash: 9ea11d54d49bf8f6ae6416f9663c2593cc66ea3e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383609"
---
# <a name="isnothrowconstructible-class"></a>is_nothrow_constructible 클래스

지정된 인수 형식을 사용할 경우 형식이 생성 가능한지와 throw되지 않는 것으로 알려져 있는지를 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class T, class... Args>
struct is_nothrow_constructible;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
형식이 쿼리입니다.

*Args*<br/>
생성자에서 일치 시킬 인수 형식 *T*합니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스 형태인 경우 true 형식을 *T* 의 인수 형식을 사용 하 여 형식이 되 *Args*, 생성자는 컴파일러에 의해 throw 되지 않는 하 고 그렇지 않으면 false입니다. 형식 *T* 생성 가능한 경우 변수 정의 `T t(std::declval<Args>()...);` 이 제대로 구성 합니다. 둘 다 *T* 와의 모든 형식 *Args* 완전 한 형식 이어야 합니다 **void**, 또는 범위를 알 수 없는 배열입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
