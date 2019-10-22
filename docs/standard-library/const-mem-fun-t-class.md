---
title: const_mem_fun_t 클래스
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun_t
helpviewer_keywords:
- const_mem_fun_t class
ms.assetid: f169d381-019b-4a0e-a9a3-54da6d948270
ms.openlocfilehash: 5263612a26b2bcb606ad712a2a8e0a521ce9437a
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688203"
---
# <a name="const_mem_fun_t-class"></a>const_mem_fun_t 클래스

참조 인수를 사용하여 초기화할 때 인수를 사용하지 않는 const 멤버 함수를 단항 함수 개체로 호출할 수 있도록 하는 어댑터 클래스입니다. C + + 11에서 사용 되지 않으며 c + + 17에서 제거 되었습니다.

## <a name="syntax"></a>구문

```cpp
template <class Result, class Type>
class const_mem_fun_t : public unary_function <Type *, Result>
{
    explicit const_mem_fun_t(Result (Type::* Pm)() const);
    Result operator()(const Type* Pleft) const;
};
```

### <a name="parameters"></a>매개 변수

*Pm* \
함수 개체로 변환할 `Type` 클래스의 멤버 함수 포인터입니다.

*Pleft* \
*Pm* 멤버 함수가 호출 되는 개체입니다.

## <a name="return-value"></a>반환 값

조정 가능한 단항 함수입니다.

## <a name="remarks"></a>주의

클래스 템플릿은 *Pm*의 복사본을 저장 합니다 .이 복사본은 private 멤버 개체에서 `Type` 클래스의 멤버 함수에 대 한 포인터 여야 합니다. @No__t_0 (`Pleft` -> \* `Pm`) () **const**를 반환 하는 멤버 함수를 정의 합니다.

## <a name="example"></a>예제

`const_mem_fun_t`의 생성자는 일반적으로 직접 사용되지 않습니다. 도우미 함수 `mem_fun`은 멤버 함수를 적용하는 데 사용됩니다. 멤버 함수 어댑터를 사용하는 방법에 대한 예제는 [mem_fun](../standard-library/functional-functions.md#mem_fun)을 참조하세요.
