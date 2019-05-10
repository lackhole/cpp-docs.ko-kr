---
title: log1p, log1pf, log1pl2
ms.date: 04/05/2018
apiname:
- log1p
- log1pf
- log1pl
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
- log1p
- log1pf
- log1pl
- math/log1p
- math/log1pf
- math/log1pl
helpviewer_keywords:
- log1p function
- log1pf function
- log1pl function
ms.assetid: a40d965d-b4f6-42f4-ba27-2395546f7c12
ms.openlocfilehash: 2ac864d7e28823c95b0202c0a8f2454d03c64aff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62285988"
---
# <a name="log1p-log1pf-log1pl"></a>log1p, log1pf, log1pl

1을 더한 지정된 값의 자연 로그를 계산합니다.

## <a name="syntax"></a>구문

```C
double log1p(
   double x
);

float log1p(
   float x
); //C++ only

long double log1p(
   long double x
); //C++ only

float log1pf(
   float x
);

long double log1pl(
   long double x
);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
부동 소수점 인수입니다.

## <a name="return-value"></a>반환 값

성공 하면 반환의 자연 (밑*e*)의 로그 (*x* + 1).

그렇지 않으면 다음 값 중 하나를 반환할 수 있습니다.

|입력|결과|SEH 예외|errno|
|-----------|------------|-------------------|-----------|
|+inf|+inf|||
|Denormals|입력과 동일함|UNDERFLOW||
|±0|입력과 동일함|||
|-1|-inf|DIVBYZERO|ERANGE|
|< -1|nan|INVALID|EDOM|
|-inf|nan|INVALID|EDOM|
|±SNaN|입력과 동일함|INVALID||
|±QNaN, 무한|입력과 동일함|||

합니다 **errno** 값은 ERANGE로 설정 하는 경우 *x* =-1입니다. 합니다 **errno** 값으로 설정 됩니다 **EDOM** 하는 경우 *x* <-1입니다.

## <a name="remarks"></a>설명

합니다 **log1p** 함수를 사용 하 여 보다 더 정확할 수 있습니다 `log(x + 1)` 때 *x* 0에 가까우면 됩니다.

때문에 C++ 오버 로드를 사용 하면 오버 로드를 호출할 수 있습니다 **log1p** 및 반환 하는 **float** 및 **긴** **double** 형식입니다. C 프로그램에서 **log1p** 항상 받아서 반환 된 **double**합니다.

하는 경우 *x* 가 자연 수 인의 계승의 로그를 반환 하는이 함수 (*x* -1).

## <a name="requirements"></a>요구 사항

|기능|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**log1p**, **log1pf**, **log1pl**|\<math.h>|\<cmath>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[log2, log2f, log2l](log2-log2f-log2l.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
