---
title: 'Bessel 함수: _j0, _j1, _jn, _y0, _y1, _yn'
ms.date: 04/05/2018
apiname:
- _j0
- _j1
- _jn
- _y0
- _y1
- _yn
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
- c.bessel
- _j0
- _j1
- _jn
- _y0
- _y1
- _yn
helpviewer_keywords:
- Bessel functions
- _j0 function
- _j1 function
- _jn function
- _y0 function
- _y1 function
- _yn function
ms.assetid: a21a8bf1-df9d-4ba0-a8c2-e7ef71921d96
ms.openlocfilehash: 682eaa99d0be1b959152ff94cc10a86aa68d988d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62341123"
---
# <a name="bessel-functions-j0-j1-jn-y0-y1-yn"></a>Bessel 함수: _j0, _j1, _jn, _y0, _y1, _yn

첫 번째 또는 두 번째 종류의 Bessel 함수를 0, 1 또는 n 순서로 계산합니다. Bessel 함수는 일반적으로 전자기파 이론의 수학에 사용됩니다.

## <a name="syntax"></a>구문

```C
double _j0(
   double x
);
double _j1(
   double x
);
double _jn(
   int n,
   double x
);
double _y0(
   double x
);
double _y1(
   double x
);
double _yn(
   int n,
   double x
);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
부동 소수점 값입니다.

*n*<br/>
Bessel 함수의 정수 순서입니다.

## <a name="return-value"></a>반환 값

Bessel 함수를 반환 하는 이러한 각 루틴 *x*합니다. 경우 *x* 에서 음수인 합니다 **_y0**를 **_y1**, 또는 **_yn** 함수, 루틴 집합 **errno** 를 **EDOM**, 출력을 **(_d)** 오류 메시지를 **stderr**를 반환 합니다 **_HUGE_VAL**합니다. 사용 하 여 오류 처리를 수정할 수 있습니다 **_matherr**합니다.

## <a name="remarks"></a>설명

**_j0**, **_j1**, 및 **_jn** 루틴 반환 Bessel 함수의 첫 번째 종류: 각각 0, 1 및 n을 정렬 합니다.

|입력|SEH 예외|Matherr 예외|
|-----------|-------------------|-----------------------|
|± **QNAN**, **IND**|**INVALID**|**_DOMAIN**|

합니다 **_y0**, **_y1**, 및 **_yn** 루틴 반환 Bessel 함수의 두 번째 종류: 각각 0, 1 및 n을 정렬 합니다.

|입력|SEH 예외|Matherr 예외|
|-----------|-------------------|-----------------------|
|± **QNAN**, **IND**|**INVALID**|**_DOMAIN**|
|± 0|**ZERODIVIDE**|**_SING**|
|&#124;x&#124; < 0.0|**INVALID**|**_DOMAIN**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_j0**, **_j1**, **_jn**, **_y0**, **_y1**, **_yn**|\<cmath> (C++), \<math.h> (C, C++)|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_bessel1.c
#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 2.387;
   int n = 3, c;

   printf( "Bessel functions for x = %f:\n", x );
   printf( "   Kind   Order  Function     Result\n\n" );
   printf( "   First  0      _j0( x )     %f\n", _j0( x ) );
   printf( "   First  1      _j1( x )     %f\n", _j1( x ) );
   for( c = 2; c < 5; c++ )
      printf( "   First  %d      _jn( %d, x )  %f\n", c, c, _jn( c, x ) );
   printf( "   Second 0      _y0( x )     %f\n", _y0( x ) );
   printf( "   Second 1      _y1( x )     %f\n", _y1( x ) );
   for( c = 2; c < 5; c++ )
      printf( "   Second %d      _yn( %d, x )  %f\n", c, c, _yn( c, x ) );
}
```

```Output
Bessel functions for x = 2.387000:
   Kind   Order  Function     Result

   First  0      _j0( x )     0.009288
   First  1      _j1( x )     0.522941
   First  2      _jn( 2, x )  0.428870
   First  3      _jn( 3, x )  0.195734
   First  4      _jn( 4, x )  0.063131
   Second 0      _y0( x )     0.511681
   Second 1      _y1( x )     0.094374
   Second 2      _yn( 2, x )  -0.432608
   Second 3      _yn( 3, x )  -0.819314
   Second 4      _yn( 4, x )  -1.626833
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[_matherr](matherr.md)<br/>
