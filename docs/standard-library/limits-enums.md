---
title: '&lt;limits&gt; 열거형'
ms.date: 11/04/2016
f1_keywords:
- limits/std::float_denorm_style
- limits/std::float_round_style
ms.assetid: c86680a2-ba97-4ed9-8c20-a448857d7dc5
ms.openlocfilehash: 567e0538f59c40d57f85d652a8919be6e034cf0b
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245352"
---
# <a name="ltlimitsgt-enums"></a>&lt;limits&gt; 열거형

## <a name="float_denorm_style"></a> float_denorm_style

이 열거형은 구현에서 비정규화된 부동 소수점 값(너무 작아서 정규화된 값으로 나타낼 수 없는 값)을 나타내기 위해 선택할 수 있는 다양한 메서드를 설명합니다.

```cpp
enum float_denorm_style {
    denorm_indeterminate = -1,
    denorm_absent = 0,
    denorm_present = 1    };
```

### <a name="return-value"></a>반환 값

이 열거형은 다음을 반환합니다.

- `denorm_indeterminate` 변환 시 비 정규화 된 폼의 유무를 확인할 수 없습니다 하는 경우.

- `denorm_absent` 비 정규화 된 폼 없는 경우.

- `denorm_present` 비 정규화 된 폼이 경우 다음을 제공 합니다.

### <a name="example"></a>예제

이 열거형의 값에 액세스할 수 있는 예제는 [numeric_limits::has_denorm](../standard-library/numeric-limits-class.md#has_denorm)을 참조하세요.

## <a name="float_round_style"></a> float_round_style

이 열거형은 구현에서 부동 소수점 값을 정수 값으로 반올림하기 위해 선택할 수 있는 다양한 메서드를 설명합니다.

```cpp
enum float_round_style {
    round_indeterminate = -1,
    round_toward_zero = 0,
    round_to_nearest = 1,
    round_toward_infinity = 2,
    round_toward_neg_infinity = 3    };
```

### <a name="return-value"></a>반환 값

이 열거형은 다음을 반환합니다.

- `round_indeterminate` 경우 반올림 방법을 확인할 수 없습니다.

- `round_toward_zero` 경우 0으로 반올림 합니다.

- `round_to_nearest` 경우는 가장 가까운 정수로 반올림 합니다.

- `round_toward_infinity` 경우 0에서 멀어지는 쪽 반올림 합니다.

- `round_toward_neg_infinity` 하는 경우 더 음의 정수는 반올림 합니다.

### <a name="example"></a>예제

이 열거형의 값에 액세스할 수 있는 예제는 [numeric_limits::round_style](../standard-library/numeric-limits-class.md#round_style)을 참조하세요.
