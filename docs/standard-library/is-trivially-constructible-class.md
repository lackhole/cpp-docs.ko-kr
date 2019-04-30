---
title: is_trivially_constructible 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_constructible
helpviewer_keywords:
- is_trivially_constructible
ms.assetid: 3fa918c1-e66f-4d0e-a11b-be1fb2c02e7b
ms.openlocfilehash: c83bea8be5c88876ffa25337464caa62b998ab45
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413478"
---
# <a name="istriviallyconstructible-class"></a>is_trivially_constructible 클래스

지정된 인수 형식을 사용할 경우 형식이 일반적으로 생성 가능한지를 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class T, class... Args>
struct is_trivially_constructible;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
형식이 쿼리입니다.

*Args*<br/>
생성자에서 일치 시킬 인수 형식 *T*합니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스 형태인 경우 true 형식을 *T* 의 인수 형식을 사용 하 여 일반적으로 생성 가능한 됩니다 *Args*, 그렇지 않으면 false입니다. 형식 *T* 일반적으로 생성 가능한 경우 변수 정의 `T t(std::declval<Args>()...);` 올바른 형식이 고 없습니다 trivial이 아닌 작업을 호출 하 라고 합니다. 둘 다 *T* 와의 모든 형식 *Args* 완전 한 형식 이어야 합니다 **void**, 또는 범위를 알 수 없는 배열입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
