---
title: '&lt;any&gt; 함수'
ms.date: 04/04/2019
f1_keywords:
- any/std::any_cast
- any/std::make_any
- any/std::swap
ms.openlocfilehash: bb5f8b4411477cfcd33613ee0395227dced784f6
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268745"
---
# <a name="ltanygt-functions"></a>&lt;any&gt; 함수

## <a name="any_cast"></a> any_cast

개체를 any로 만듭니다.

```cpp
template<class T>
    T any_cast(const any& operand);
template<class T>
    T any_cast(any& operand);
template<class T>
    T any_cast(any&& operand);
template<class T>
    const T* any_cast(const any* operand) noexcept;
template<class T>
    T* any_cast(any* operand) noexcept;
```

## <a name="make_any"></a> make_any

값을 사용하여 any 개체를 만듭니다.

```cpp
template <class T, class... Args>
    any make_any(Args&& ...args);
template <class T, class U, class... Args>
    any make_any(initializer_list<U> il, Args&& ...args);
```

## <a name="swap"></a> 교환

어떤 두 개체의 요소를 교환 합니다.

```cpp
void swap(any& left, any& right) noexcept;
```

### <a name="parameters"></a>매개 변수

*left*\
`any` 형식의 개체입니다.

*right*\
`any` 형식의 개체입니다.
