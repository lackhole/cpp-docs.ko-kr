---
title: '&lt;선택적&gt; 함수'
ms.date: 11/04/2016
f1_keywords:
- optional/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
ms.openlocfilehash: ebb7ccfb8a39bf1f45c7003d7c38e503ab20c89b
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268935"
---
# <a name="ltoptionalgt-functions"></a>&lt;선택적&gt; 함수

## <a name="make_optional"></a> make_optional

옵션 개체를 만듭니다.

```cpp
template <class T>
    constexpr optional<see below> make_optional(T&&);
template <class T, class... Args>
    constexpr optional<T> make_optional(Args&&... args);
template <class T, class U, class... Args>
    constexpr optional<T> make_optional(initializer_list<U> il, Args&&... args);
```

## <a name="nullopt"></a> nullopt

```cpp
inline constexpr nullopt_t nullopt(unspecified );
```

## <a name="swap"></a> 교환

```cpp
template <class T>
    void swap(optional<T>&, optional<T>&) noexcept(see below );
```
