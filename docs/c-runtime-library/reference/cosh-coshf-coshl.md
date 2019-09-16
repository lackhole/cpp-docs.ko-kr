---
title: cosh, coshf, coshl
ms.date: 04/11/2018
api_name:
- cosh
- coshf
- coshl
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
- cosh
- coshf
- coshl
helpviewer_keywords:
- cosh function
- coshf function
- coshl function
- trigonometric functions
- hyperbolic functions
ms.openlocfilehash: 446988e67ca6e3b4a3839a9336f1ea4e2755c124
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938991"
---
# <a name="cosh-coshf-coshl"></a>cosh, coshf, coshl

쌍곡선 코사인을 계산 합니다.

## <a name="syntax"></a>구문

```C
double cosh( double x );
float coshf( float x );
long double coshl( long double x );
```

```cpp
float cosh( float x );  // C++ only
long double cosh( long double x );  // C++ only
```

### <a name="parameters"></a>매개 변수

*x*<br/>
각도(라디안)입니다.

## <a name="return-value"></a>반환 값

*X*의 하이퍼볼릭 코사인입니다.

기본적으로 **cosh**, **coshf**또는 **coshl** 호출에서 결과가 너무 크면 함수는 **HUGE_VAL** 를 반환 하 고 **errno** 를 **ERANGE**로 설정 합니다.

|입력|SEH 예외|Matherr 예외|
|-----------|-------------------|-----------------------|
|± **QNAN**, **IND**|없음|**_DOMAIN**|
|*x* ≥ 7.104760e+002|**INEXACT**+**OVERFLOW**|**OVERFLOW**|

## <a name="remarks"></a>설명

는 C++ 오버 로드를 허용 하므로 **float** 또는 **long** **double** 값을 사용 하 고 반환 하는 **cosh** 의 오버 로드를 호출할 수 있습니다. C 프로그램에서 **cosh** 는 항상 **double**을 사용 하 고 반환 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더(C)|필수 헤더(C++)|
|-------------|---------------------|-|
|**coshf**, **cosl**, **coshl**|\<math.h>|\<cmath> 또는 \<math.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[Sinh, sinhf, sinhf](sinh-sinhf-sinhl.md)의 예제를 참조 하세요.

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[acosh, acoshf, acoshl](acosh-acoshf-acoshl.md)<br/>
[asinh, asinhf, asinhl](asinh-asinhf-asinhl.md)<br/>
[atanh, atanhf, atanhl](atanh-atanhf-atanhl.md)<br/>
[_matherr](matherr.md)<br/>
[sinh, sinhf, sinhl](sinh-sinhf-sinhl.md)<br/>
[tanh, tanhf, tanhl](tanh-tanhf-tanhl.md)<br/>
