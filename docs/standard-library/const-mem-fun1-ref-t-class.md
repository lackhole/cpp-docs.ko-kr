---
title: const_mem_fun1_ref_t 클래스
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun1_ref_t
helpviewer_keywords:
- const_mem_fun1_ref_t class
ms.assetid: 8220d373-fa1c-44be-a21d-96d49b3ea6bb
ms.openlocfilehash: 59790b5791dc50d217053dc7a13856d436101020
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244535"
---
# <a name="constmemfun1reft-class"></a>const_mem_fun1_ref_t 클래스

참조 인수를 사용하여 초기화할 때 단일 인수를 사용하는 **const** 멤버 함수를 이항 함수 개체로 호출할 수 있도록 하는 어댑터 클래스입니다. C++17에서 제거 하는 C + + 11에서 사용 되지 않습니다.

## <a name="syntax"></a>구문

```cpp
template <class Result, class Type, class Arg>
    class const_mem_fun1_ref_t
        : public binary_function<Type, Arg, Result>
{
    explicit const_mem_fun1_ref_t(Result (Type::* Pm)(Arg) const);
    Result operator()(const Type& left, Arg right) const;
};
```

### <a name="parameters"></a>매개 변수

*Pm*\
함수 개체로 변환할 `Type` 클래스의 멤버 함수 포인터입니다.

*왼쪽*\
**const** 개체를 *Pm* 멤버 함수가 호출 됩니다.

*오른쪽*\
에 지정 되는 인수 *Pm*합니다.

## <a name="return-value"></a>반환 값

조정 가능한 이항 함수입니다.

## <a name="remarks"></a>설명

복사본을 저장 하는 템플릿 클래스 *Pm*, 클래스의 멤버 함수에 대 한 포인터 여야 `Type`, 전용 멤버 개체에 있습니다. 해당 멤버 함수 정의 `operator()` 반환 (`left`합니다.\* *Pm*) (`right`) **const**합니다.

## <a name="example"></a>예제

`const_mem_fun1_ref_t`의 생성자는 일반적으로 직접 사용되지 않습니다. 도우미 함수 `mem_fun_ref`는 멤버 함수를 적용하는 데 사용됩니다. 멤버 함수 어댑터를 사용하는 방법의 예제에 대해서는 [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref)를 참조하세요.
