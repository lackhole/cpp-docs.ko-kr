---
title: 부동 소수점 기본 형식
ms.date: 01/31/2019
apiname:
- _dclass
- _ldclass
- _fdclass
- _dsign
- _ldsign
- _fdsign
- _dpcomp
- _ldpcomp
- _fdpcomp
- _dtest
- _ldtest
- _fdtest
- _d_int
- _ld_int
- _fd_int
- _dscale
- _ldscale
- _fdscale
- _dunscale
- _ldunscale
- _fdunscale
- _dexp
- _ldexp
- _fdexp
- _dnorm
- _fdnorm
- _dpoly
- _ldpoly
- _fdpoly
- _dlog
- _ldlog
- _fdlog
- _dsin
- _ldsin
- _fdsin
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
- _dclass
- _ldclass
- _fdclass
- _dsign
- _ldsign
- _fdsign
- _dpcomp
- _ldpcomp
- _fdpcomp
- _dtest
- _ldtest
- _fdtest
- _d_int
- _ld_int
- _fd_int
- _dscale
- _ldscale
- _fdscale
- _dunscale
- _ldunscale
- _fdunscale
- _dexp
- _ldexp
- _fdexp
- _dnorm
- _fdnorm
- _dpoly
- _ldpoly
- _fdpoly
- _dlog
- _ldlog
- _fdlog
- _dsin
- _ldsin
- _fdsin
helpviewer_keywords:
- _dclass
- _ldclass
- _fdclass
- _dsign
- _ldsign
- _fdsign
- _dpcomp
- _ldpcomp
- _fdpcomp
- _dtest
- _ldtest
- _fdtest
- _d_int
- _ld_int
- _fd_int
- _dscale
- _ldscale
- _fdscale
- _dunscale
- _ldunscale
- _fdunscale
- _dexp
- _ldexp
- _fdexp
- _dnorm
- _fdnorm
- _dpoly
- _ldpoly
- _fdpoly
- _dlog
- _ldlog
- _fdlog
- _dsin
- _ldsin
- _fdsin
ms.openlocfilehash: 230d0def145bcb443437b59303b2b36e348da2bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333614"
---
# <a name="floating-point-primitives"></a>부동 소수점 기본 형식

일부 표준 C 런타임 라이브러리 (CRT) 부동 소수점 함수를 구현 하는 데 사용 되는 기본 함수 Microsoft 전용입니다. 완성도 위해 여기서 설명 하 고 있지만 용도로 권장 되지 않습니다. 이러한 함수 중 일부는 알려진 전체 자릿수, 예외 처리 및 IEEE-754 동작에 대 한 규칙에 문제가 있기 때문에 사용 되지 않는 것으로 설명 합니다. 이전 버전과 호환성을 위해서만 라이브러리에 존재합니다. 올바른 동작, 이식성 및 표준 준수, 이러한 함수를 통해 표준 부동 소수점 함수를 선호 합니다.

## <a name="dclass-ldclass-fdclass"></a>_dclass, _ldclass, _fdclass

### <a name="syntax"></a>구문

```C
short __cdecl _dclass(double x);
short __cdecl _ldclass(long double x);
short __cdecl _fdclass(float x);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
부동 소수점 함수 인수입니다.

### <a name="remarks"></a>설명

CRT 매크로 C 버전을 구현 하는 부동 소수점 이러한 기본형 [fpclassify](fpclassify.md) 부동 소수점 형식에 대 한 합니다. 인수의 분류 *x* math.h에 정의 된 이러한 상수 중 하나로 반환 됩니다.

|값|설명|
|-----------|-----------------|
| **FP_NAN** | 자동, 신호 또는 비활성화 상태 NaN |
| **FP_INFINITE** | 양수 또는 음수 무한대 |
| **FP_NORMAL** | 정규화된 0이 아닌 양수 또는 음수 값 |
| **FP_SUBNORMAL** | 양수 또는 음수 subnormal (비 정규화 된) 값 |
| **FP_ZERO** | 양수 또는 음수 0 값 |

추가 세부 정보에 대 한 Microsoft 전용을 사용할 수 있습니다 [_fpclass, _fpclassf](fpclass-fpclassf.md) 함수입니다. 사용 된 [fpclassify](fpclassify.md) 매크로 또는 이식성에 대 한 함수입니다.

## <a name="dsign-ldsign-fdsign"></a>_dsign, _ldsign, _fdsign

### <a name="syntax"></a>구문

```C
int __cdecl _dsign(double x);
int __cdecl _ldsign(long double x);
int __cdecl _fdsign(float x);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
부동 소수점 함수 인수입니다.

### <a name="remarks"></a>설명

부동 소수점 이러한 기본형을 구현 합니다 [signbit](signbit.md) 매크로 또는 CRT 함수입니다. 부호 비트 significand (가) 인수에 설정 된 경우 0이 아닌 값 반환 *x*를 부호 비트로 설정 되어 있지 않으면 0입니다.

## <a name="dpcomp-ldpcomp-fdpcomp"></a>_dpcomp, _ldpcomp, _fdpcomp

### <a name="syntax"></a>구문

```C
int __cdecl _dpcomp(double x, double y);
int __cdecl _ldpcomp(long double x, long double y);
int __cdecl _fdpcomp(float x, float y);
```

### <a name="parameters"></a>매개 변수

*x*, *y*<br/>
부동 소수점 함수 인수입니다.

### <a name="remarks"></a>설명

이러한 부동 소수점 기본 인수 두 개 *x* 및 *y*, 비트 또는 math.h에 정의 된 이러한 상수를 표현 되는 해당 순서 관계를 보여 주는 값을 반환 합니다.

| 값 | 설명 |
|------------|-----------------|
| **_FP_LT** | *x* 간주할 수 미만 *y* |
| **_FP_EQ** | *x* 같은 것으로 간주 될 수 있습니다 *y* |
| **_FP_GT** | *x* 보다 큰 것으로 간주 될 수 있습니다 *y* |

이러한 기본형을 구현 합니다 [isgreater, isgreaterequal, isless, islessequal, islessgreater, 및 isunordered](floating-point-ordering.md) 매크로 및 함수가 CRT에서.

## <a name="dtest-ldtest-fdtest"></a>_dtest, _ldtest, _fdtest

### <a name="syntax"></a>구문

```C
short __cdecl _dtest(double* px);
short __cdecl _ldtest(long double* px);
short __cdecl _fdtest(float* px);
```

### <a name="parameters"></a>매개 변수

*px*<br/>
부동 소수점 인수에 대 한 포인터입니다.

### <a name="remarks"></a>설명

같은 부동 소수점 기본 형식 구현 된 C++ 버전의 CRT 함수가 [fpclassify](fpclassify.md) 부동 소수점 형식에 대 한 합니다. 인수 *x* 평가 분류 math.h에 정의 된 이러한 상수 중 하나로 반환 됩니다.

|값|설명|
|-----------|-----------------|
| **FP_NAN** | 자동, 신호 또는 비활성화 상태 NaN |
| **FP_INFINITE** | 양수 또는 음수 무한대 |
| **FP_NORMAL** | 정규화된 0이 아닌 양수 또는 음수 값 |
| **FP_SUBNORMAL** | 양수 또는 음수 subnormal (비 정규화 된) 값 |
| **FP_ZERO** | 양수 또는 음수 0 값 |

추가 세부 정보에 대 한 Microsoft 전용을 사용할 수 있습니다 [_fpclass, _fpclassf](fpclass-fpclassf.md) 함수입니다. 사용 된 [fpclassify](fpclassify.md) 이식성에 대 한 함수입니다.

## <a name="dint-ldint-fdint"></a>_d_int, _ld_int, _fd_int

### <a name="syntax"></a>구문

```C
short __cdecl _d_int(double* px, short exp);
short __cdecl _ld_int(long double* px, short exp);
short __cdecl _fd_int(float* px, short exp);
```

### <a name="parameters"></a>매개 변수

*px*<br/>
부동 소수점 인수에 대 한 포인터입니다.

*exp*<br/>
정수 계열 형식으로는 지 수입니다.

### <a name="remarks"></a>설명

같은 부동 소수점 기본 형식 부동 소수점 값으로 포인터를 이동 *px* 고 지 수 값을 *exp*, 가능한 경우 지정 된 지 수 아래 부동 소수점 값의 소수 부분을 제거 하 고 . 반환 된 값의 결과인 **fpclassify** 입력된 값에 따라 *px* 무한대 또는 NaN 인 경우 및 출력 값에 따라 *px* 그렇지 않은 경우.

## <a name="dscale-ldscale-fdscale"></a>_dscale, _ldscale, _fdscale

### <a name="syntax"></a>구문

```C
short __cdecl _dscale(double* px, long exp);
short __cdecl _ldscale(long double* px, long exp);
short __cdecl _fdscale(float* px, long exp);
```

### <a name="parameters"></a>매개 변수

*px*<br/>
부동 소수점 인수에 대 한 포인터입니다.

*exp*<br/>
정수 계열 형식으로는 지 수입니다.

### <a name="remarks"></a>설명

같은 부동 소수점 기본 형식 부동 소수점 값으로 포인터를 이동 *px* 및 지 수 값을 *exp*, 및의 값을 크기 조정 *px* 2로<sup> *exp*</sup>가능한 경우. 반환 된 값의 결과인 **fpclassify** 입력된 값에 따라 *px* 무한대 또는 NaN 인 경우 및 출력 값에 따라 *px* 그렇지 않은 경우. 이식성을 선호 합니다 [ldexp, ldexpf, 및 ldexpl](ldexp.md) 함수입니다.

## <a name="dunscale-ldunscale-fdunscale"></a>_dunscale, _ldunscale, _fdunscale

### <a name="syntax"></a>구문

```C
short __cdecl _dunscale(short* pexp, double* px);
short __cdecl _ldunscale(short* pexp, long double* px);
short __cdecl _fdunscale(short* pexp, float* px);
```

### <a name="parameters"></a>매개 변수

*pexp*<br/>
정수 계열 형식으로 지 수에 대 한 포인터입니다.

*px*<br/>
부동 소수점 인수에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이러한 부동 소수점 기본 형식을 가리키는 부동 소수점 값을 세분화 *px* (가)는 기호 및 지 수, 가능한 경우에 합니다. 유효 숫자는 절대값은 0.5 보다 크거나 같고 1.0 보다 작은 크기가 조정 됩니다. 지 수 값입니다 *n*여기서 원래 부동 소수점 값은 2 번 확장된 significand 같음<sup>*n*</sup>합니다. 이 정수 지 수 *n* 가리키는 위치에 저장 된 *pexp*합니다. 반환 된 값의 결과인 **fpclassify** 입력된 값에 따라 *px* 무한대 또는 NaN 인 경우와 그렇지 않은 경우 출력 값입니다. 이식성을 선호 합니다 [frexp, frexpf, frexpl](frexp.md) 함수입니다.

## <a name="dexp-ldexp-fdexp"></a>_dexp, _ldexp, _fdexp

### <a name="syntax"></a>구문

```C
short __cdecl _dexp(double* px, double y, long exp);
short __cdecl _ldexp(long double* px, long double y, long exp);
short __cdecl _fdexp(float* px, float y, long exp);
```

### <a name="parameters"></a>매개 변수

*y*<br/>
부동 소수점 함수 인수입니다.

*px*<br/>
부동 소수점 인수에 대 한 포인터입니다.

*exp*<br/>
정수 계열 형식으로는 지 수입니다.

### <a name="remarks"></a>설명

가 가리키는 위치에 부동 소수점 값을 생성 하는 부동 소수점 이러한 기본형 *px* 같음 *y* * 2<sup>*exp*</sup>합니다. 반환 된 값의 결과인 **fpclassify** 입력된 값에 따라 *y* 무한대 또는 NaN 인 경우 및 출력 값에 따라 *px* 그렇지 않은 경우. 이식성을 선호 합니다 [ldexp, ldexpf, 및 ldexpl](ldexp.md) 함수입니다.

## <a name="dnorm-fdnorm"></a>_dnorm, _fdnorm

### <a name="syntax"></a>구문

```C
short __cdecl _dnorm(unsigned short* ps);
short __cdecl _fdnorm(unsigned short* ps);
```

### <a name="parameters"></a>매개 변수

*ps*<br/>
포인터의 배열로 표시 되는 부동 소수점 값의 비트 표현과 **부호 없는** **짧은**합니다.

### <a name="remarks"></a>설명

부동 소수점 이러한 기본형 underflowed 부동 소수점 값의 소수 부분을 정규화 하 고 조정 합니다 *특징*, 또는 맞게 편향된 지 수. 값의 배열로 변환할 부동 소수점 형식의 비트 표현으로 전달 됩니다 **부호 없는** **짧은** 를 통해 합니다 `_double_val`를 `_ldouble_val`, 또는 `_float_val` 형식 math.h에 punning 공용 구조체 선언 합니다. 반환 값의 결과인 **fpclassify** 무한대 또는 NaN 인 경우 입력된 부동 소수점 값에 출력 값이 고 그렇지 합니다.

## <a name="dpoly-ldpoly-fdpoly"></a>_dpoly, _ldpoly, _fdpoly

### <a name="syntax"></a>구문

```C
double __cdecl _dpoly(double x, double const* table, int n);
long double __cdecl _ldpoly(long double x, long double const* table, int n);
float __cdecl _fdpoly(float x, _float const* table, int n);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
부동 소수점 함수 인수입니다.

*table*<br/>
다항식 차수는에 대 한 상수 계수 테이블에 대 한 포인터입니다.

*n*<br/>
평가할 다항식의 순서입니다.

### <a name="remarks"></a>설명

계산을 반환 하는 부동 소수점 이러한 기본형 *x* 주문의 다항식의 *n* 계수가 있는 해당 상수 값을 기준으로 표현 됩니다 *테이블*. 예를 들어 경우 *테이블*\[0] = 3.0 *테이블*\[1] 4.0 = *테이블*\[2] 5.0 = 및 *n* = 2, 다항식 5.0 x 나타냅니다<sup>2</sup> 4.0 + x + 3.0. 에 대 한 평가 되 면이 다항식 *x* 2.0의 결과 31.0 합니다. 이러한 함수는 내부적으로 사용 되지 않습니다.

## <a name="dlog-dlog-dlog"></a>_dlog, _dlog, _dlog

### <a name="syntax"></a>구문

```C
double __cdecl _dlog(double x, int base_flag);
long double __cdecl _ldlog(long double x, int base_flag);
float __cdecl _fdlog(float x, int base_flag);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
부동 소수점 함수 인수입니다.

*base_flag*<br/>
기본에 대해 0을 사용 하려면 기본 제어 하는 플래그 *e* 및 0이 아닌 밑수 10에 대 한 합니다.

### <a name="remarks"></a>설명

자연 로그를 반환 하는 부동 소수점 이러한 기본형 *x*, ln (*x*) 또는 로그<sub>*e*</sub>(*x*), 때 *base_flag* 은 0입니다. 로그의 밑수 10 반환 *x*, 또는 로그<sub>10</sub>(*x*), *base_flag* 0이 아닌 합니다. 이러한 함수는 내부적으로 사용 되지 않습니다. 이식성에 대 한 함수를 선호 [log, logf, logl, log10, log10f, 및 log10l](log-logf-log10-log10f.md)합니다.

## <a name="dsin-ldsin-fdsin"></a>_dsin, _ldsin, _fdsin

### <a name="syntax"></a>구문

```C
double __cdecl _dsin(double x, unsigned int quadrant);
long double __cdecl _ldsin(long double x, unsigned int quadrant);
float __cdecl _fdsin(float x, unsigned int quadrant);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
부동 소수점 함수 인수입니다.

*quadrant*<br/>
사분면 오프셋 0, 1, 2 또는 3을 생성 하는 데 `sin`, `cos`를 `-sin`, 및 `-cos` 결과입니다.

### <a name="remarks"></a>설명

사인을 반환 하는 부동 소수점 이러한 기본형 *x* 에서 오프셋 합니다 *사분면* 모듈로 4. 사인을 반환 되는 효과적으로 코사인,-사인 및-코사인 *x* 때 *사분면* 모듈로 4는 0, 1, 2 또는 3, 각각. 이러한 함수는 내부적으로 사용 되지 않습니다. 이식성을 선호 합니다 [sin, sinf, sinl](sin-sinf-sinl.md)를 [cos, cosf, cosl 및](cos-cosf-cosl.md) 함수입니다.

## <a name="requirements"></a>요구 사항

헤더: \<math.h >

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[frexp, frexpf, frexpl](frexp.md)<br/>
[ldexp, ldexpf, and ldexpl](ldexp.md)<br/>
[log, logf, logl, log10, log10f, log10l](log-logf-log10-log10f.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
