---
title: frexp, frexpf, frexpl
ms.date: 04/05/2018
apiname:
- frexp
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
- frexp
- _frexpl
helpviewer_keywords:
- _frexpl function
- mantissas, floating-point variables
- frexpl function
- exponent, floating-point numbers
- frexp function
- floating-point functions, mantissa and exponent
ms.assetid: 9b020f2e-3967-45ec-a6a8-d467a071aa55
ms.openlocfilehash: c9e259f730d2d63d07032735be930f6f0fdb17e5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62332977"
---
# <a name="frexp-frexpf-frexpl"></a>frexp, frexpf, frexpl

부동 소수점 숫자의 가수 및 지수를 가져옵니다.

## <a name="syntax"></a>구문

```C
double frexp(
   double x,
   int *expptr
);
float frexpf(
   float x,
   int * expptr
);
long double frexpl(
   long double x,
   int * expptr
);
float frexp(
   float x,
   int * expptr
);  // C++ only
long double frexp(
   long double x,
   int * expptr
);  // C++ only
```

### <a name="parameters"></a>매개 변수

*x*<br/>
부동 소수점 값입니다.

*expptr*<br/>
저장된 정수 지수에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

**frexp** 가 수를 반환 합니다. 하는 경우 *x* 가 0 이면 함수는가 수 및 지 수는 0을 반환 합니다. 하는 경우 *expptr* 됩니다 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 됩니다 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 이 함수를 설정 하는 경우는 계속 실행 하도록 허용 합니다 **errno** 하 **EINVAL** 0을 반환 합니다.

## <a name="remarks"></a>설명

합니다 **frexp** 함수는 부동 소수점 값을 세분화 (*x*)가 (*m*) 및 지 수 (*n*), 절대 값 *m* 0.5 보다 크거나 같고 1.0 보다 작은 되 고 *x* = *m* * 2<sup>*n*</sup>. 정수 지 수 *n* 가리키는 위치에 저장 된 *expptr*합니다.

C++오버 로드를 호출할 수 있도록 오버 로드를 허용 **frexp**합니다. C 프로그램에서 **frexp** 는 항상 사용을 **double** 및 **int** 포인터와 반환을 **double**.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**frexp**, **frexpf**, **frexpl**|\<math.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_frexp.c
// This program calculates frexp( 16.4, &n )
// then displays y and n.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x, y;
   int n;

   x = 16.4;
   y = frexp( x, &n );
   printf( "frexp( %f, &n ) = %f, n = %d\n", x, y, n );
}
```

```Output
frexp( 16.400000, &n ) = 0.512500, n = 5
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[ldexp](ldexp.md)<br/>
[modf, modff, modfl](modf-modff-modfl.md)<br/>
