---
title: allocator&lt;void&gt; 클래스
ms.date: 11/04/2016
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
ms.openlocfilehash: c8d787fe03dfe6f67fb8e228308ec74b6e7f620a
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688525"
---
# <a name="allocatorltvoidgt-class"></a>allocator&lt;void&gt; 클래스

**Void**형식에 대 한 클래스 템플릿 할당자의 특수화로,이 컨텍스트에서 적합 한 형식을 정의 합니다.

## <a name="syntax"></a>구문

```cpp
template <>
class allocator<void> {
    typedef void *pointer;
    typedef const void *const_pointer;
    typedef void value_type;
    template <class Other>
    struct rebind;
    allocator();
    allocator(const allocator<void>&);

    template <class Other>
    allocator(const allocator<Other>&);

    template <class Other>
    allocator<void>& operator=(const allocator<Other>&);
};
```

## <a name="remarks"></a>주의

클래스는 **void**형식에 대 한 클래스 템플릿 [할당자](../standard-library/allocator-class.md) 를 명시적으로 특수화 합니다. 생성자와 대입 연산자는 클래스 템플릿과 동일 하 게 동작 하지만 다음 유형만 정의 합니다.

- [const_pointer](../standard-library/allocator-class.md#const_pointer).

- [pointer](../standard-library/allocator-class.md#pointer).

- [value_type](../standard-library/allocator-class.md#value_type).

- 다시 [바인딩](../standard-library/allocator-class.md#rebind)중첩 된 클래스 템플릿입니다.
