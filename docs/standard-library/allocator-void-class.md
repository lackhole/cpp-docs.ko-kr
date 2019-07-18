---
title: allocator&lt;void&gt; 클래스
ms.date: 11/04/2016
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
ms.openlocfilehash: 7ac7fbaa8c50eb13457271cf96ddc3412733c833
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245876"
---
# <a name="allocatorltvoidgt-class"></a>allocator&lt;void&gt; 클래스

형식으로 템플릿 클래스 할당자의 특수화 **void**를이 컨텍스트에서 의미가 있는 형식을 정의 합니다.

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

## <a name="remarks"></a>설명

클래스는 템플릿 클래스를 명시적으로 특수화 [할당자](../standard-library/allocator-class.md) 형식용 **void**합니다. 해당 생성자 및 대입 연산자는 템플릿 클래스에 대해 동일하게 동작하지만 다음 형식만 정의합니다.

- [const_pointer](../standard-library/allocator-class.md#const_pointer).

- [pointer](../standard-library/allocator-class.md#pointer).

- [value_type](../standard-library/allocator-class.md#value_type).

- [rebind](../standard-library/allocator-class.md#rebind), 중첩된 템플릿 클래스.
