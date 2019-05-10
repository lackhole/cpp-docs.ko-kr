---
title: is_trivially_move_constructible 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_move_constructible
helpviewer_keywords:
- is_trivially_move_constructible
ms.assetid: 740bdec7-65e5-47b3-b94f-a2479ceac3ec
ms.openlocfilehash: a1aef356716fac903b4e44a358602c709572e8ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413396"
---
# <a name="istriviallymoveconstructible-class"></a>is_trivially_move_constructible 클래스

형식에 Trivial 이동 생성자가 있는지 여부를 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct is_trivially_move_constructible;
```

### <a name="parameters"></a>매개 변수

*Ty*<br/>
형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스 형태인 경우 true 형식을 *Ty* 는 클래스에 trivial 이동 생성자가 있는 그렇지 않으면 false입니다.

클래스에 대 한 이동 생성자 *Ty* 간단 하는 경우:

암시적으로 선언된 경우

매개 변수 형식이 암시적 선언의 형식과 동일한 경우

클래스 *Ty* 에 가상 함수가 없는

클래스 *Ty* 에 없는 가상 기본

클래스에 휘발성 비정적 데이터 멤버가 없는 경우

모든 직접 기본 클래스의 *Ty* trivial 이동 생성자가 있는 경우

클래스 형식의 모든 비정적 데이터 멤버의 클래스에 Trivial 이동 생성자가 있는 경우

클래스 배열 형식의 모든 비정적 데이터 멤버의 클래스에 Trivial 이동 생성자가 있는 경우

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
