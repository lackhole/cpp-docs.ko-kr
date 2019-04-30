---
title: isnormal
ms.date: 01/31/2019
f1_keywords:
- isnormal
- math/isnormal
helpviewer_keywords:
- isnormal function
ms.openlocfilehash: e426fbce71efff1e810a03b8347e7c48aa0d91d2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62286442"
---
# <a name="isnormal"></a>isnormal

부동 소수점 값을 일반 값인지 여부를 결정 합니다.

## <a name="syntax"></a>구문

```C
int isnormal(
   /* floating-point */ x
); /* C-only macro */

template <class FloatingType>
inline bool isnormal(
   FloatingType x
) throw(); /* C++-only function template */
```

### <a name="parameters"></a>매개 변수

*x*<br/>
테스트할 부동 소수점 값입니다.

## <a name="return-value"></a>반환 값

**isnormal** 0이 아닌 값을 반환 합니다 (**true** 에서 C++ 코드) 하는 경우 인수 *x* 은 0, subnormal, infinite로도 아니고 NaN입니다. 그렇지 않으면 **isnormal** 0을 반환 합니다 (**false** 에서 C++ 코드).

## <a name="remarks"></a>설명

**isnormal** 매크로가 C로 컴파일된 경우에 인라인 함수 템플릿을로 컴파일될 때 C++합니다.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더(C)|필수 헤더(C++)|
|--------------|---------------------------|-------------------------------|
|**isnormal**|\<math.h>|\<math.h> 또는 \<cmath>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
