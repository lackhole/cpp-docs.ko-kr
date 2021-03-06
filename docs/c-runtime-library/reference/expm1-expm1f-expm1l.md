---
title: expm1, expm1f, expm1l
ms.date: 04/05/2018
api_name:
- expm1l
- expm1
- expm1f
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- expm1l
- expm1
- expm1f
helpviewer_keywords:
- expm1f function
- expm1l function
- expm1 function
ms.assetid: 2a4dd2d9-370c-42b0-9067-0625efa272e0
ms.openlocfilehash: 77bd44975e97cc646f7d2fd100d86b6661b8c2e9
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941541"
---
# <a name="expm1-expm1f-expm1l"></a>expm1, expm1f, expm1l

값의 밑이 e인 지수 - 1을 계산합니다.

## <a name="syntax"></a>구문

```C
double expm1(
   double x
);
float expm1(
   float x
);  // C++ only
long double expm1(
   long double x
);  // C++ only
float expm1f(
   float x
);
long double expm1l(
   long double x
);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
부동 소수점 지수 값입니다.

## <a name="return-value"></a>반환 값

**Expm1** 함수는 성공 하면 e<sup>x</sup> -1을 나타내는 부동 소수점 값을 반환 합니다. 오버플로 시 **expm1** 는 **HUGE_VAL**를 반환 하 고 **expm1f** 는 **HUGE_VALF**를 반환 하며 Expm1l **는 HUGE_VALL** **를 반환 하며** **errno는** **ERANGE**로 설정 됩니다. 반환 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

는 C++ 오버 로드를 허용 하기 때문에 **float** 및 **long** **double** 값을 사용 하 고 반환 하는 **expm1** 의 오버 로드를 호출할 수 있습니다. C 프로그램에서 **expm1** 은 항상 **double**을 사용 하 고 반환 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**expm1**, **expm1f**, **expm1l**|\<math.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[exp2, exp2f, exp2l](exp2-exp2f-exp2l.md)<br/>
[pow, powf, powl](pow-powf-powl.md)<br/>
