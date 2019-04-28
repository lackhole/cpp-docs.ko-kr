---
title: isinf
ms.date: 01/31/2019
f1_keywords:
- isinf
- math/isinf
helpviewer_keywords:
- isinf function
ms.openlocfilehash: be99970a0c7b152ba213eabd59b53a7503cd3c54
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331612"
---
# <a name="isinf"></a>isinf

부동 소수점 값을 무한대 인지 확인 합니다.

## <a name="syntax"></a>구문

```C
int isinf(
   /* floating-point */ x
); /* C-only macro */

template <class FloatingType>
inline bool isinf(
   FloatingType x
) throw(); /* C++-only template function */
```

### <a name="parameters"></a>매개 변수

*x*<br/>
테스트할 부동 소수점 값입니다.

## <a name="return-value"></a>반환 값

**isinf** 0이 아닌 값을 반환 합니다 (**true** 에서 C++ 코드) 하는 경우 인수 *x* 는 양수 또는 음수 무한대. **isinf** 0을 반환 합니다 (**false** 에서 C++ 코드) 인수가 유한 인 경우 또는 NAN입니다. 일반 및 subnormal 부동 소수점 값은 유한 간주 됩니다.

## <a name="remarks"></a>설명

**isinf** 매크로로 컴파일할 때 인라인 템플릿 함수 C로 컴파일될 때 C++합니다.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더(C)|필수 헤더(C++)|
|--------------|---------------------------|-------------------------------|
|**isinf**|\<math.h>|\<math.h> 또는 \<cmath>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
