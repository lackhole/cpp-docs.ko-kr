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
ms.openlocfilehash: f60a3ef6528da33fd1117fc940e961e9fe0987df
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62185908"
---
# <a name="resultof-class"></a>result_of 클래스

지정된 인수 유형을 사용하는 호출 가능 형식의 반환 형식을 결정합니다. C++14, c++17에서 사용 되지 않는 추가 합니다.

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

*Fn*<br/>
쿼리할 호출 가능 형식입니다.

*ArgTypes*<br/>
쿼리할 호출 가능 형식에 대한 인수 목록의 형식입니다.

## <a name="remarks"></a>설명

이 템플릿을 사용 하 여의 결과 형식은 컴파일 타임에 결정 `Fn`(`ArgTypes`), 여기서 *Fn* 에서형식인수목록을사용하여호출할호출가능형식에대한참조,함수에대한참조또는호출가능형식 *ArgTypes*합니다. 템플릿 클래스의 `type` 구성원은 평가되지 않은 식 `std::invoke(declval<Fn>(), declval<ArgTypes>()...)`가 올바른 형식인 경우 `decltype(std::invoke(declval<Fn>(), declval<ArgTypes>()...))`의 결과 형식 이름을 지정합니다. 그렇지 않은 경우 템플릿 클래스에는 구성원 `type`이 없습니다. 형식 *Fn* 및 매개 변수 팩에는 모든 형식이 *ArgTypes* 완전 한 형식 이어야 합니다 **void**, 또는 범위를 알 수 없는 배열입니다. 위해 사용 되지 않는 [invoke_result](invoke-result-class.md) c++17에서.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[invoke_result 클래스](invoke-result-class.md)<br/>
