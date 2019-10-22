---
title: mem_fun1_ref_t 클래스
ms.date: 02/21/2019
f1_keywords:
- functional/std::mem_fun1_ref_t
helpviewer_keywords:
- mem_fun1_ref_t class
ms.assetid: 7d6742f6-19ba-4523-b3c8-0e5b8f11464f
ms.openlocfilehash: 238d6147b2afa5ca3e143bc57aa4892e17d2c869
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687749"
---
# <a name="mem_fun1_ref_t-class"></a>mem_fun1_ref_t 클래스

참조 인수를 사용 하 여 초기화할 때 단일 인수를 사용 하는 `non_const` 멤버 함수를 이항 함수 개체로 호출할 수 있도록 하는 어댑터 클래스입니다. C + + 11에서 사용 되지 않으며 c + + 17에서 제거 되었습니다.

## <a name="syntax"></a>구문

```cpp
template <class Result, class Type, class Arg>
class mem_fun1_ref_t : public binary_function<Type, Arg, Result> {
    explicit mem_fun1_ref_t(
    Result (Type::* _Pm)(Arg));

    Result operator()(
    Type& left,
    Arg right) const;
};
```

### <a name="parameters"></a>매개 변수

*Pm \ (_e)*
함수 개체로 변환할 `Type` 클래스의 멤버 함수 포인터입니다.

*왼쪽* \
*_Pm* 멤버 함수가 호출 되는 개체입니다.

*오른쪽* \
*_ _ Pm*으로 지정 되는 인수입니다.

## <a name="return-value"></a>반환 값

조정 가능한 이항 함수입니다.

## <a name="remarks"></a>주의

클래스 템플릿은 전용 멤버 개체에서 `Type` 클래스의 멤버 함수에 대 한 포인터 여야 하는 *_Pm*의 복사본을 저장 합니다. @No__t_2 `_Pm`) (**right**)를 반환 하는 `operator()` 멤버 함수를 정의**합니다.**

## <a name="example"></a>예제

`mem_fun1_ref_t`의 생성자는 일반적으로 직접 사용되지 않습니다. 도우미 함수 `mem_fun_ref`은 멤버 함수를 적용하는 데 사용됩니다. 멤버 함수 어댑터를 사용하는 방법에 대한 예제는 [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref)를 참조하세요.
