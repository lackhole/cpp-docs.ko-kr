---
title: isgreater isgreaterequal, isless, islessequal, islessgreater, isunordered
ms.date: 01/31/2019
f1_keywords:
- isgreater
- math/isgreater
- isgreaterequal
- math/isgreaterequal
- isless
- math/isless
- islessequal
- math/islessequal
- islessgreater
- math/islessgreater
- isunordered
- math/isunordered
helpviewer_keywords:
- isgreater function
- isgreaterequal function
- isless function
- islessequal function
- islessgreater function
- isunordered function
ms.openlocfilehash: 748360cae1dd0ee43645dee369c60c835246ed03
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333705"
---
# <a name="isgreater-isgreaterequal-isless-islessequal-islessgreater-isunordered"></a>isgreater isgreaterequal, isless, islessequal, islessgreater, isunordered

두 부동 소수점 값 사이의 관계 순서를 결정합니다.

## <a name="syntax"></a>구문

```C
int isgreater(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int isgreaterequal(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int isless(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int islessequal(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int islessgreater(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int isunordered(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */
```

```C++
template <class FloatingType1, class FloatingType2>
inline bool isgreater(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool isgreaterequal(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool isless(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool islessequal(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool islessgreater(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool isunordered(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */
```

### <a name="parameters"></a>매개 변수

*x*, *y*<br/>
비교할 부동 소수점 값입니다.

## <a name="return-value"></a>반환 값

모든 비교에서 무한대와 같은 부호의 동일한 것으로 비교합니다. 음의 무한대 유한 값 또는 양수 무한대 보다 작은 경우 양의 무한대가 유한 값 또는 음의 무한대 보다 큽니다. 0으로 기호에 관계 없이 동일합니다. Nan은 다른 NaN를 포함 하 여 모든 값 보다 크거나 같음, 보다 작지 않습니다.

모두 인수가 NaN, 순서 지정는 매크로 인지 하는 경우 **isgreater**, **isgreaterequal**하십시오 **isless**, 및 **islessequal** 0이 아닌 반환 값 간의 순서 지정 된 관계 *x* 하 고 *y* 마찬가지입니다. 이러한 매크로 중 하나 또는 두 인수가 Nan 이면 또는 순서 관계가 false 이면 0을 반환 합니다. 함수가 형태는 동일한 방식으로 동작 하지만 반환 **true** 하거나 **false**합니다.

합니다 **islessgreater** 매크로 둘 다 0이 아닌 값을 반환 *x* 및 *y* Nan, 되지 및 *x* 는 보다 작거나 보다큰*y*합니다. 인수 중 하나 또는 둘 다는 Nan, 아니면 값이 같으면 0을 반환 합니다. 함수 형식 동일 하 게 동작 하지만 반환 **true** 하거나 **false**합니다.

합니다 **isunordered** 매크로 경우 0이 아닌 값을 반환 *x*를 *y*, 둘 다 Nan 또는 합니다. 그렇지 않으면 0을 반환합니다. 함수 형식 동일 하 게 동작 하지만 반환 **true** 하거나 **false**합니다.

## <a name="remarks"></a>설명

이러한 비교 작업으로 컴파일할 때 인라인 템플릿 함수 C로 컴파일된 경우 매크로로 구현 됩니다 C++입니다.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더(C)|필수 헤더(C++)|
|--------------|---------------------------|-------------------------------|
| **isgreater**, **isgreaterequal**, **isless**,<br/>**islessequal**, **islessgreater**, **isunordered** | \<math.h> | \<math.h> 또는 \<cmath> |

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
