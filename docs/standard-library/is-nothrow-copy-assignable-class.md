---
title: is_nothrow_copy_assignable 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_copy_assignable
helpviewer_keywords:
- is_nothrow_copy_assignable
ms.assetid: baa8abd6-4f53-489f-abba-8d5d5c53bbbc
ms.openlocfilehash: bb3aca47b61bdcc5b28eeedc1a6b4edefc303c4e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383596"
---
# <a name="isnothrowcopyassignable-class"></a>is_nothrow_copy_assignable 클래스

throw되지 않는 것으로 컴파일러에 알려진 복사 대입 연산자가 형식에 있는지를 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct is_nothrow_copy_assignable;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스 참조 가능한 형식에 대 한 마찬가지 *T* 여기서 `is_nothrow_assignable<T&, const T&>` 보유 true이 고 그렇지 않으면 false입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_nothrow_assignable 클래스](../standard-library/is-nothrow-assignable-class.md)<br/>
