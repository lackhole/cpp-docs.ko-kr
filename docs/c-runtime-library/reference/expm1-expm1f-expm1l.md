---
title: expm1, expm1f, expm1l
ms.date: 04/05/2018
apiname:
- expm1l
- expm1
- expm1f
apilocation:
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
apitype: DLLExport
f1_keywords:
- expm1l
- expm1
- expm1f
helpviewer_keywords:
- expm1f function
- expm1l function
- expm1 function
ms.assetid: 2a4dd2d9-370c-42b0-9067-0625efa272e0
ms.openlocfilehash: 5971f879ecef7d4fa1027849cc44d598e877b5f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334985"
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

합니다 **expm1** e를 나타내는 부동 소수점 값을 반환 하는 함수<sup>x</sup> -1 성공 합니다. 오버플로에서 **expm1** 반환 **HUGE_VAL**를 **expm1f** 반환 **HUGE_VALF**를 **expm1l** 반환 **HUGE_VALL**, 및 **errno** 로 설정 되어 **ERANGE**합니다. 반환 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

때문에 C++ 오버 로드를 사용 하면 오버 로드를 호출할 수 있습니다 **expm1** 및 반환 하는 **float** 및 **긴** **double** 값입니다. C 프로그램에서 **expm1** 항상 받아서 반환 된 **double**합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**expm1**, **expm1f**, **expm1l**|\<math.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[exp2, exp2f, exp2l](exp2-exp2f-exp2l.md)<br/>
[pow, powf, powl](pow-powf-powl.md)<br/>
