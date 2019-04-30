---
title: is_rvalue_reference 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_rvalue_reference
helpviewer_keywords:
- is_rvalue_reference class
- is_rvalue_reference
ms.assetid: 40a97072-7b5c-4274-9154-298d3dcf064a
ms.openlocfilehash: ea3be02db2a4a840ed8f8b8a253d7409c26cf759
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413595"
---
# <a name="isrvaluereference-class"></a>is_rvalue_reference 클래스

형식이 rvalue 참조인지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct is_rvalue_reference;
```

### <a name="parameters"></a>매개 변수

*Ty*<br/>
형식이 쿼리입니다.

## <a name="remarks"></a>설명

이 형식 조건자의 인스턴스 형태인 경우 true 형식을 *Ty* 되는 [rvalue 참조](../cpp/rvalue-reference-declarator-amp-amp.md)합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[Lvalue 및 Rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md)<br/>
