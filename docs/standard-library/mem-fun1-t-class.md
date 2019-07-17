---
title: mem_fun1_t 클래스
ms.date: 02/21/2019
f1_keywords:
- functional/std::mem_fun1_t
helpviewer_keywords:
- mem_fun1_t class
ms.assetid: 01a8c2c2-b2f7-4e3f-869c-5b5b9f06ea54
ms.openlocfilehash: 822de97849750a72948137ba8fe23beab8554ff5
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245091"
---
# <a name="memfun1t-class"></a>mem_fun1_t 클래스

허용 하는 어댑터 클래스를 `non_const` 멤버 함수는 단일 인수를 포인터 인수를 사용 하 여 초기화할 때 이항 함수 개체로 호출할 수 있습니다. C++17에서 제거 하는 C + + 11에서 사용 되지 않습니다.

## <a name="syntax"></a>구문

```cpp
template <class Result, class Type, class Arg>
class mem_fun1_t : public binary_function<Type *, Arg, Result> {
    explicit mem_fun1_t(
    Result (Type::* _Pm)(Arg));

    Result operator()(
    Type* _Pleft,
    Arg right) const;
};
```

### <a name="parameters"></a>매개 변수

*_Pm*\
함수 개체로 변환할 `Type` 클래스의 멤버 함수 포인터입니다.

*_Pleft*\
개체는 합니다 *_Pm* 멤버 함수가 호출 됩니다.

*오른쪽*\
에 지정 되는 인수 *_Pm*합니다.

## <a name="return-value"></a>반환 값

조정 가능한 이항 함수입니다.

## <a name="remarks"></a>설명

복사본을 저장 하는 템플릿 클래스 *_Pm*, 클래스의 멤버 함수에 대 한 포인터 여야 `Type`, 전용 멤버 개체에 있습니다. 해당 멤버 함수 정의 `operator()` 반환 ( **_Pleft** -> \* `_Pm`) (**오른쪽**).

## <a name="example"></a>예제

`mem_fun1_t`의 생성자는 일반적으로 직접 사용되지 않습니다. 도우미 함수 `mem_fun`은 멤버 함수를 적용하는 데 사용됩니다. 멤버 함수 어댑터를 사용하는 방법에 대한 예제는 [mem_fun](../standard-library/functional-functions.md#mem_fun)을 참조하세요.
