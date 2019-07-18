---
title: const_mem_fun_ref_t 클래스
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun_ref_t
helpviewer_keywords:
- const_mem_fun_ref_t class
ms.assetid: 316ddbaa-9f46-4931-8eba-ea4ca66360ef
ms.openlocfilehash: 7e208364e2cac0e0d4e020dc865b299fbd2bde2c
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244557"
---
# <a name="constmemfunreft-class"></a>const_mem_fun_ref_t 클래스

참조 인수를 사용하여 초기화할 때 인수를 사용하지 않는 **const** 멤버 함수를 단항 함수 개체로 호출할 수 있도록 하는 어댑터 클래스입니다. C++17에서 제거 하는 C + + 11에서 사용 되지 않습니다.

## <a name="syntax"></a>구문

```cpp
template <class Result, class Type>
    class const_mem_fun_ref_t
: public unary_function<Type, Result>
{
    explicit const_mem_fun_t(Result (Type::* Pm)() const);
    Result operator()(const Type& left) const;
};
```

### <a name="parameters"></a>매개 변수

*Pm*\
함수 개체로 변환할 `Type` 클래스의 멤버 함수 포인터입니다.

*왼쪽*\
개체는 합니다 *Pm* 멤버 함수가 호출 됩니다.

## <a name="return-value"></a>반환 값

조정 가능한 단항 함수입니다.

## <a name="remarks"></a>설명

복사본을 저장 하는 템플릿 클래스 *Pm*, 클래스의 멤버 함수에 대 한 포인터 여야 `Type`, 전용 멤버 개체에 있습니다. 해당 멤버 함수 정의 `operator()` 반환 (**왼쪽**.\* `Pm`) () **const**합니다.

## <a name="example"></a>예제

`const_mem_fun_ref_t`의 생성자는 일반적으로 직접 사용되지 않습니다. 도우미 함수 `mem_fun_ref`은 멤버 함수를 적용하는 데 사용됩니다. 멤버 함수 어댑터를 사용하는 방법에 대한 예제는 [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref)를 참조하세요.
