---
title: is_trivially_copy_assignable 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_copy_assignable
helpviewer_keywords:
- is_trivially_copy_assignable
ms.assetid: 7410133e-f367-493f-92a7-e34e3ec5e879
ms.openlocfilehash: 831e7c5afdd39980876a8e8284a68fec2084a4e5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413465"
---
# <a name="istriviallycopyassignable-class"></a>is_trivially_copy_assignable 클래스

형식에 Trivial 복사 할당 연산자가 있는지 여부를 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct is_trivially_copy_assignable;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스 형태인 경우 true 형식을 *T* 는 클래스에 trivial 복사 할당 연산자를, 그렇지 않으면 false입니다.

클래스에 대 한 할당 생성자는 *T* 암시적으로 제공 되는 클래스 경우 trivial *T* 에 클래스 가상 함수가 없는 *T* 에 없는 가상 기본을 클래스 클래스 형식의 모든 비정적 데이터 멤버에 trivial 대입 연산자 및 클래스 배열 형식의 모든 비정적 데이터 멤버의 클래스에 trivial 대입 연산자입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
