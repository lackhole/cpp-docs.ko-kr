---
title: invoke_result 클래스
ms.date: 02/21/2019
f1_keywords:
- type_traits/std::invoke_result
- type_traits/std::invoke_result_t
- type_traits/std::invoke_result::type
helpviewer_keywords:
- std::invoke_result
- std::invoke_result_t
- std::invoke_result::type
ms.openlocfilehash: 7c03240d3ee666fcda30562279a8dbda2ca8dc7b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404853"
---
# <a name="invokeresult-class"></a>invoke_result 클래스

컴파일 타임에 지정된 된 인수 형식과 사용 하는 호출 가능 형식의 반환 형식을 결정 합니다. C + + 17에 추가 합니다.

## <a name="syntax"></a>구문

```cpp
template <class Callable, class... Args>
   struct invoke_result<Callable(Args...)>;

// Helper type
template<lass Callable, class... Args>
   using invoke_result_t = typename invoke_result<Callable, Args...>::type;
```

### <a name="parameters"></a>매개 변수

*호출 가능*<br/>
쿼리할 호출 가능 형식입니다.

*Args*<br/>
쿼리할 호출 가능 형식에 대한 인수 목록의 형식입니다.

## <a name="remarks"></a>설명

이 템플릿을 사용 하 여 결과 형식을 결정 *Callable*(*Args*...) 컴파일 타임에 있는 *Callable* 모든 형식과 *Args* 모든 완전 한 형식, 범위를 알 수 없는, 배열 또는 가능한 경우 cv 한정 `void`합니다. 합니다 `type` 템플릿 클래스의 멤버의 반환 형식 이름을 *Callable* 인수를 사용 하 여 호출 되 면 *Args*... 합니다 `type` 경우에 멤버 란 *Callable* 인수를 사용 하 여 호출 될 때 호출할 수 있습니다 *Args*... 확인 되지 않은 컨텍스트에서 합니다. 그렇지 않은 경우 템플릿 클래스에 멤버가 없는 `type`, 컴파일 시간에 인수 형식의 특정 집합에서 테스트 SFINAE 수 있습니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[invoke](functional-functions.md#invoke)
