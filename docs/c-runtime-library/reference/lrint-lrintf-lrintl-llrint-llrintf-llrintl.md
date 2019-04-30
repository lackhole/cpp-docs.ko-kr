---
title: lrint, lrintf, lrintl, llrint, llrintf, llrintl
ms.date: 04/05/2018
apiname:
- lrint
- lrintl
- lrintf
- llrint
- llrintf
- llrintl
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
- lrint
- lrintf
- lrintl
- llrint
- llrintf
- llrintl
- math/lrint
- math/lrintf
- math/lrintl
- math/llrint
- math/llrintf
- math/llrintl
helpviewer_keywords:
- lrint function
- lrintf function
- lrintl function
- llrint function
- llrintf function
- llrintl function
ms.assetid: 28ccd5b3-5e6f-434f-997d-a21d51b8ce7f
ms.openlocfilehash: 01680a62e654112475a55bd8eac0cc14d254e2a2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62285774"
---
# <a name="lrint-lrintf-lrintl-llrint-llrintf-llrintl"></a>lrint, lrintf, lrintl, llrint, llrintf, llrintl

현재 반올림 모드 및 방향을 사용하여 지정된 부동 소수점 값을 가장 가까운 정수 값으로 반올림합니다.

## <a name="syntax"></a>구문

```C
long int lrint(
   double x
);

long int lrint(
   float x
); //C++ only

long int lrint(
   long double x
); //C++ only

long int lrintf(
   float x
);

long int lrintl(
   long double x
);

long long int llrint(
   double x
);

long long int llrint(
   float x
); //C++ only

long long int llrint(
   long double x
); //C++ only

long long int llrintf(
   float x
);

long long int llrintl(
   long double x
);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
반올림할 값입니다.

## <a name="return-value"></a>반환 값

성공 하면의 반올림 된 정수 값을 반환 *x*합니다.

|문제|반환|
|-----------|------------|
|*x* 반환 형식의 범위를 벗어났습니다<br /><br /> *x* = ±∞<br /><br /> *x* = NaN|발생 시킵니다 **FE_INVALID** 영 (0)를 반환 합니다.|

## <a name="remarks"></a>설명

때문에 C++ 오버 로드를 허용 오버 로드를 호출할 수 있습니다 **lrint** 하 고 **llrint** 사용 하는 **float** 하 고 **긴** **이중** 형식입니다. C 프로그램에서 **lrint** 하 고 **llrint** 항상를 **double**합니다.

하는 경우 *x* 정수 값, 이러한 함수 생성에 해당 하는 부동 소수점을 나타내지 않습니다 **FE_INEXACT**합니다.

**Microsoft 전용**: 결과 반환 형식의 범위를 벗어날 때 또는 매개 변수가 NaN 또는 무한 인 경우 반환 값은 정의 된 구현입니다. Microsoft 컴파일러는 0 값을 반환합니다.

## <a name="requirements"></a>요구 사항

|기능|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**lrint**, **lrintf**, **lrintl**, **llrint**, **llrintf**, **llrintl**|\<math.h>|\<cmath>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
