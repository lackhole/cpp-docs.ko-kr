---
title: is_trivially_move_assignable 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_move_assignable
helpviewer_keywords:
- is_trivially_move_assignable
ms.assetid: 374f7322-0706-4bc1-a1a5-4191d0315e28
ms.openlocfilehash: b25d16658def4e3cf620ab707d2dabacb2620f33
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413395"
---
# <a name="istriviallymoveassignable-class"></a>is_trivially_move_assignable 클래스

형식에 trivial 이동 할당 연산자가 있는지 여부를 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct is_trivially_move_assignable;
```

### <a name="parameters"></a>매개 변수

*Ty*<br/>
형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스 형태인 경우 true 형식을 *Ty* 는 클래스에 trivial 이동 할당 연산자를, 그렇지 않으면 false입니다.

클래스에 대 한 이동 할당 연산자 *Ty* 간단 하는 경우:

암시적으로 제공된 경우

클래스 *Ty* 에 가상 함수가 없는

클래스 *Ty* 에 없는 가상 기본

클래스 형식의 모든 비정적 데이터 멤버의 클래스에 trivial 이동 할당 연산자가 있는 경우

클래스 형식 배열의 모든 비정적 데이터 멤버의 클래스에 trivial 이동 할당 연산자가 있는 경우

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
