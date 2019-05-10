---
title: sqrt, sqrtf, sqrtl
ms.date: 04/05/2018
apiname:
- sqrtl
- sqrtf
- sqrt
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- sqrt
- sqrtf
- _sqrtl
helpviewer_keywords:
- sqrtf function
- sqrt function
- sqrtl function
- _sqrtl function
- calculating square roots
- square roots, calculating
ms.assetid: 2ba9467b-f172-41dc-8f10-b86f68fa813c
ms.openlocfilehash: 7c17c973b98638195e2e2d2a5f793578437d11ae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62354901"
---
# <a name="sqrt-sqrtf-sqrtl"></a>sqrt, sqrtf, sqrtl

제곱근을 계산합니다.

## <a name="syntax"></a>구문

```C
double sqrt(
   double x
);
float sqrt(
   float x
);  // C++ only
long double sqrt(
   long double x
);  // C++ only
float sqrtf(
   float x
);
long double sqrtl(
   long double x
);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
음수가 아닌 부동 소수점 값

## <a name="remarks"></a>설명

때문에 C++ 오버 로드를 사용 하면 오버 로드를 호출할 수 있습니다 **sqrt** 사용 하는 **float** 또는 **긴** **double** 형식입니다. C 프로그램에서 **sqrt** 항상 받아서 반환 **double**합니다.

## <a name="return-value"></a>반환 값

합니다 **sqrt** 의 제곱근을 반환 하는 함수 *x*합니다. 기본적으로 하는 경우 *x* 가 음수 이면 **sqrt** 는 무한 NaN을 반환 합니다.

|입력|SEH 예외|**_matherr** 예외|
|-----------|-------------------|--------------------------|
|± QNAN,IND|없음|_DOMAIN|
|- ∞|없음|_DOMAIN|
|x<0|없음|_DOMAIN|

## <a name="requirements"></a>요구 사항

|기능|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**sqrt**, **sqrtf**, **sqrtl**|\<math.h>|\<cmath>|

호환성에 대한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_sqrt.c
// This program calculates a square root.

#include <math.h>
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   double question = 45.35, answer;
   answer = sqrt( question );
   if( question < 0 )
      printf( "Error: sqrt returns %f\n", answer );
   else
      printf( "The square root of %.2f is %.2f\n", question, answer );
}
```

```Output
The square root of 45.35 is 6.73
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[exp, expf, expl](exp-expf.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
[pow, powf, powl](pow-powf-powl.md)<br/>
[_CIsqrt](../../c-runtime-library/cisqrt.md)<br/>
