---
title: result_of 클래스
ms.date: 02/21/2019
f1_keywords:
- type_traits/std::result_of
- type_traits/std::result_of_t
- type_traits/std::result_of::type
helpviewer_keywords:
- std::result_of
- std::result_of_t
- std::result_of::type
ms.assetid: 5374a096-4b4a-4712-aa97-6852c5cdd6be
ms.openlocfilehash: ab575ac31936e7003f19fc2ceb3c5b1727d0728c
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689004"
---
# <a name="result_of-class"></a>result_of 클래스

지정된 인수 유형을 사용하는 호출 가능 형식의 반환 형식을 결정합니다. C + + 14에서 추가 되었고, c + + 17에서 사용 되지 않습니다.

## <a name="syntax"></a>구문

```cpp
template<class>
struct result_of; // Causes a static assert

template <class Fn, class... ArgTypes>
struct result_of<Fn(ArgTypes...)>;

// Helper type
template<class T>
   using result_of_t = typename result_of<T>::type;
```

### <a name="parameters"></a>매개 변수

*Fn* \
쿼리할 호출 가능 형식입니다.

*Argtypes* \
쿼리할 호출 가능 형식에 대한 인수 목록의 형식입니다.

## <a name="remarks"></a>주의

이 템플릿을 사용 하 여 컴파일 타임에 `Fn` (`ArgTypes`)의 결과 형식을 확인할 수 있습니다. 여기서 *Fn* 은 호출 가능 형식 이거나 함수에 대 한 참조 이거나 호출 가능 형식에 대 한 참조 이며, *argtypes*에서 형식의 인수 목록을 사용 하 여 호출 됩니다. 클래스 템플릿의 `type` 멤버는 확인 되지 않은 식 `std::invoke(declval<Fn>(), declval<ArgTypes>()...)` 형식이 올바른 경우 `decltype(std::invoke(declval<Fn>(), declval<ArgTypes>()...))`의 결과 형식에 이름을 입력 합니다. 그렇지 않으면 클래스 템플릿에 `type` 멤버가 없습니다. 매개 변수 팩 *argtypes* 의 형식 *Fn* 및 모든 형식은 완전 한 형식, **void**또는 알 수 없는 바인딩된 배열 이어야 합니다. C + + 17의 [invoke_result](invoke-result-class.md) 에는 더 이상 사용 되지 않습니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참조

[<type_traits>](../standard-library/type-traits.md)\
[invoke_result 클래스](invoke-result-class.md)
