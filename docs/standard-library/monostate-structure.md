---
title: monostate 구조체
ms.date: 04/04/2019
f1_keywords:
- variant/std::monostate
helpviewer_keywords:
- monostate struct
ms.openlocfilehash: f083b5f4abd6e9fc482007744683342f7ab92fc0
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68269335"
---
# <a name="monostate-struct"></a>monostate 구조체

클래스 monostate 변형 형식은 기본 형식이 되도록 변형에 대 한 대체 형식으로 사용 됩니다.

## <a name="syntax"></a>구문

```cpp
struct monostate;

constexpr bool operator<(monostate, monostate) noexcept;
constexpr bool operator>(monostate, monostate) noexcept;
constexpr bool operator<=(monostate, monostate) noexcept;
constexpr bool operator>=(monostate, monostate) noexcept;
constexpr bool operator==(monostate, monostate) noexcept;
constexpr bool operator!=(monostate, monostate) noexcept;
```
