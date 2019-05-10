---
title: mem_fun_t 클래스
ms.date: 02/21/2019
f1_keywords:
- functional/std::mem_fun_t
helpviewer_keywords:
- mem_fun_t class
ms.assetid: 242566d4-750c-4c87-9d63-2e2c9d19ca2a
ms.openlocfilehash: cf1080f5f832bd79a347ee7fd847ff56a7567fdf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412893"
---
# <a name="memfunt-class"></a>mem_fun_t 클래스

허용 하는 어댑터 클래스를 `non_const` 멤버 함수 포인터 인수를 사용 하 여 초기화할 때 단항 함수 개체로 호출할 수 없는 인수입니다. C++17에서 제거 하는 C + + 11에서 사용 되지 않습니다.

## <a name="syntax"></a>구문

```cpp
template <class Result, class Type>
class mem_fun_t : public unary_function<Type *, Result> {
    explicit mem_fun_t(Result (Type::* _Pm)());

    Result operator()(Type* _Pleft) const;

};
```

### <a name="parameters"></a>매개 변수

*_Pm*<br/>
함수 개체로 변환할 `Type` 클래스의 멤버 함수 포인터입니다.

*_Pleft*<br/>
개체는 합니다 *_Pm* 멤버 함수가 호출 됩니다.

## <a name="return-value"></a>반환 값

조정 가능한 단항 함수입니다.

## <a name="remarks"></a>설명

복사본을 저장 하는 템플릿 클래스 *_Pm*, 클래스의 멤버 함수에 대 한 포인터 여야 `Type`, 전용 멤버 개체에 있습니다. 또한 해당 멤버 함수 `operator()`를 ( `_Pleft`->* `_Pm`)( )을 반환하는 것으로 정의합니다.

## <a name="example"></a>예제

`mem_fun_t`의 생성자는 일반적으로 직접 사용되지 않습니다. 도우미 함수 `mem_fun`은 멤버 함수를 적용하는 데 사용됩니다. 멤버 함수 어댑터를 사용하는 방법에 대한 예제는 [mem_fun](../standard-library/functional-functions.md#mem_fun)을 참조하세요.

## <a name="requirements"></a>요구 사항

**헤더:** \<functional>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[\<functional>](../standard-library/functional.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)<br/>
