---
title: scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl
ms.date: 04/05/2018
api_name:
- scalblnl
- scalbnl
- scalbnf
- scalblnf
- scalbn
- scalbln
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
- scalblnf
- scalbnl
- scalblnl
- scalbln
- scalbn
- scalbnf
helpviewer_keywords:
- scalbn function
- scalbln function
- scalblnl function
- scalbnl function
- scalbnf function
- scalblnf function
ms.assetid: df2f1543-8e39-4af4-a5cf-29307e64807d
ms.openlocfilehash: 794d0bdceb13aafb83de85fb29e47a4fa3125cd6
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948912"
---
# <a name="scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl"></a>scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl

부동 소수점 수에 FLT_RADIX의 정수 제곱을 곱합니다.

## <a name="syntax"></a>구문

```C
double scalbn(
   double x,
   int exp
);
float scalbn(
   float x,
   int exp
);  // C++ only
long double scalbn(
   long double x,
   int exp
);  // C++ only
float scalbnf(
   float x,
   int exp
);
long double scalbnl(
   long double x,
   int exp
);
double scalbln(
   double x,
   long exp
);
float scalbln(
   float x,
   long exp
);  // C++ only
long double scalbln(
   long double x,
   long exp
);  // C++ only
float scalblnf(
   float x,
   long exp
);
long double scalblnl(
   long double x,
   long exp
);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
부동 소수점 값입니다.

*exp*<br/>
정수 지수입니다.

## <a name="return-value"></a>반환 값

**Scalbn** 함수는 성공할 경우 *x* \* **FLT_RADIX**<sup>exp</sup> 의 값을 반환 합니다. 오버플로 시 ( *x*의 부호에 따라) **scalbn** 는 +/- **HUGE_VAL**;를 반환 합니다. **errno** 값은 **ERANGE**로 설정 됩니다.

**Errno** 및 가능한 오류 반환 값에 대 한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조 하세요.

## <a name="remarks"></a>설명

**FLT_RADIX** 는 네이티브 부동 \<소수점 기수로 서 >에 정의 되 고, 이진 시스템에서는 값이 2이 고, **scalbn** 는 [ldexp](ldexp.md)와 동일 합니다.

는 C++ 오버 로드를 허용 하므로 **float** 또는 **long** **double** 형식을 사용 하 고 반환 하는 **scalbn** 및 **scalbln** 오버 로드를 호출할 수 있습니다. C 프로그램에서 **scalbn** 는 항상 **double** 과 **int** 를 사용 하 고 **double**을 반환 하며 **scalbln** 는 항상 **double** 과 **long** 을 사용 하며 **double**을 반환 합니다.

## <a name="requirements"></a>요구 사항

|기능|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**scalbn**, **scalbnf**, **scalbnl**, **scalbln**, **scalblnf**, **scalblnl**|\<math.h>|\<cmath>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_scalbn.c
// Compile using: cl /W4 crt_scalbn.c
#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 6.4, y;
   int p = 3;

   y = scalbn( x, p );
   printf( "%2.1f times FLT_RADIX to the power of %d is %2.1f\n", x, p, y );
}
```

### <a name="output"></a>출력

```Output
6.4 times FLT_RADIX to the power of 3 is 51.2
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
[ldexp](ldexp.md)<br/>
[modf, modff, modfl](modf-modff-modfl.md)<br/>
