---
title: nullopt_t 구조체
ms.date: 08/04/2019
f1_keywords:
- optional/std::nullopt_t
- optional/std::nullopt
ms.openlocfilehash: 1f453a5d75de3f6dedb133d55c094a4f4274e08f
ms.sourcegitcommit: 16c0392fc8d96e814c3a40b0c5346d7389aeb525
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/12/2019
ms.locfileid: "68957052"
---
# <a name="nullopt_t-struct"></a>nullopt_t 구조체

`nullopt_t` 형식은 [선택적](optional-class.md) 개체에 값이 포함 되지 않음을 나타내는 데 사용 되는 고유하고 빈 형식입니다.

`optional` 형식의 `nullopt` 상수는형식에초기화되지않은`nullopt_t` 상태가 있음을 나타냅니다. `optional` 개체를 초기화 하거나 개체와 비교 하는 데 사용할 수 있습니다.

## <a name="syntax"></a>구문

```cpp
struct nullopt_t;
inline constexpr nullopt_t nullopt{ /*implementation-defined*/ };
```

## <a name="see-also"></a>참고자료

[\<선택적 >](optional.md)\
[선택적 클래스](optional-class.md)
