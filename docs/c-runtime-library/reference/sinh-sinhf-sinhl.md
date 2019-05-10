---
title: sinh, sinhf, sinhl
ms.date: 04/10/2018
apiname:
- sinhl
- sinhf
- sinhl
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
- sinh
- sinhf
- sinhl
helpviewer_keywords:
- sinh function
- sinhl function
- sinhf function
- calculating hyperbolic sines
- trigonometric functions
- sinhf function
- sinhl function
- hyperbolic functions
ms.openlocfilehash: 7327809a20569c520aa799690203458d54e30fb5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356279"
---
# <a name="sinh-sinhf-sinhl"></a>sinh, sinhf, sinhl

쌍 곡 사인을 계산합니다.

## <a name="syntax"></a>구문

```C
double sinh(double x);
float sinhf(float x);
long double sinhl(long double x);
```

```cpp
float sinh(float x);  // C++ only
long double sinh(long double x);  // C++ only
```

### <a name="parameters"></a>매개 변수

*x*<br/>
각도(라디안)입니다.

## <a name="return-value"></a>반환 값

합니다 **sinh** 의 쌍 곡 사인을 반환 하는 함수 *x*합니다. 기본적으로 결과 너무 크면 **sinh** 설정 **errno** 에 **ERANGE** 에서 반환 하 고**HUGE_VAL**합니다.

|입력|SEH 예외|Matherr 예외|
|-----------|-------------------|-----------------------|
|± QNAN,IND|없음|_DOMAIN|
|&#124;x&#124; ≥ 7.104760e+002|OVERFLOW+INEXACT|OVERFLOW|

반환 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

때문에 C++ 오버 로드를 사용 하면 오버 로드를 호출할 수 있습니다 **sinh** 및 반환 하는 **float** 또는 **긴** **double** 값입니다. C 프로그램에서 **sinh** 항상 받아서 반환 **double**합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더(C)|필수 헤더(C++)|
|-|-|-|
|**sinh**, **sinhf**, **sinhl**|\<math.h>|\<cmath> 또는 \<math.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_sinhcosh.c
// This program displays the hyperbolic
// sine and hyperbolic cosine of pi / 2.
// Compile by using: cl /W4 crt_sinhcosh.c

#include <math.h>
#include <stdio.h>

int main( void)
{
   double pi = 3.1415926535;
   double x, y;

   x = pi / 2;
   y = sinh( x );
   printf( "sinh( %f ) = %f\n",x, y );
   y = cosh( x );
   printf( "cosh( %f ) = %f\n",x, y );
}
```

```Output
sinh( 1.570796 ) = 2.301299
cosh( 1.570796 ) = 2.509178
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[acosh, acoshf, acoshl](acosh-acoshf-acoshl.md)<br/>
[asinh, asinhf, asinhl](asinh-asinhf-asinhl.md)<br/>
[atanh, atanhf, atanhl](atanh-atanhf-atanhl.md)<br/>
[cosh, coshf, coshl](cosh-coshf-coshl.md)<br/>
[tanh, tanhf, tanhl](tanh-tanhf-tanhl.md)<br/>
