---
title: is_lvalue_reference 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_lvalue_reference
helpviewer_keywords:
- is_lvalue_reference class
- is_lvalue_reference
ms.assetid: 7f11896b-935c-4de1-9c87-9d0127f904e2
ms.openlocfilehash: e032522e790b7027886ba1a6199ed7fdf86c0936
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351945"
---
# <a name="islvaluereference-class"></a>is_lvalue_reference 클래스

형식이 lvalue 참조인지 여부를 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct is_lvalue_reference;
```

### <a name="parameters"></a>매개 변수

*Ty*<br/>
형식이 쿼리입니다.

## <a name="remarks"></a>설명

이 형식 조건자의 인스턴스 형태인 경우 true 형식을 *Ty* 함수, 그렇지 않으면 false 또는 개체에 대 한 참조입니다. 사실은 *Ty* rvalue 참조 되지 않을 수 있습니다. rvalue에 대한 자세한 내용은 [Rvalue 참조 선언자: &&](../cpp/rvalue-reference-declarator-amp-amp.md)를 참조하세요.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[Lvalue 및 Rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md)<br/>
