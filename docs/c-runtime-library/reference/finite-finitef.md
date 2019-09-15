---
title: isfinite, _finite, _finitef
ms.date: 01/31/2019
api_name:
- _finite
- _finitef
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- isfinite
- finite
- _finite
- _finitef
- math/isfinite
- math/_finite
- math/_finitef
- float/_finite
helpviewer_keywords:
- finite function
- _finite function
- _finitef function
ms.assetid: 5a7d7ca7-befb-4e1f-831d-28713c6eb805
ms.openlocfilehash: a2cde4d3a57884413f0c48aa299b171334c5f988
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957176"
---
# <a name="isfinite-_finite-_finitef"></a>isfinite, _finite, _finitef

부동 소수점 값이 유한인지 확인합니다.

## <a name="syntax"></a>구문

```C
int isfinite(
   /* floating-point */ x
); /* C-only macro */

template <class FloatingType>
inline bool isfinite(
   FloatingType x
) throw(); /* C++-only template function */

int _finite(
   double x
);

int _finitef(
   float x
); /* x64 and ARM/ARM64 only */
```

### <a name="parameters"></a>매개 변수

*x*<br/>
테스트할 부동 소수점 값입니다.

## <a name="return-value"></a>반환 값

X가 법선 또는 `_finite` subnormal 유한 값인 경우 `_finitef` 매크로와 및 함수는 0이 아닌 값을 반환 합니다. `isfinite` 인수가 무한 또는 NaN 인 경우 0을 반환 합니다. 인라인 C++ 템플릿 함수 `isfinite` 는 동일한 방식으로 동작 하지만 **true** 또는 **false**를 반환 합니다.

## <a name="remarks"></a>설명

`isfinite`는 C로 컴파일된 매크로 이며로 C++컴파일될 때 인라인 템플릿 함수를 말합니다. `_finite` 및`_finitef` 함수는 Microsoft 전용입니다. `_finitef` 함수는 x86, ARM 또는 ARM64 플랫폼용으로 컴파일된 경우에만 사용할 수 있습니다.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더(C)|필수 헤더(C++)|
|--------------|---------------------------|-------------------------------|
|`_finite`|\<float.h> 또는 \<math.h>|\<float.h>, \<math.h>, \<cfloat> 또는 \<cmath>|
|`isfinite`, `_finitef`|\<math.h>|\<math.h> 또는 \<cmath>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
[isinf](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
