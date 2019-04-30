---
title: ilogb, ilogbf, ilogbl2
ms.date: 04/05/2018
apiname:
- ilogb
- ilogbf
- ilogbl
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
- ilogb
- ilogbf
- ilogbl
- math/ilogb
- math/ilogbf
- math/ilogbl
helpviewer_keywords:
- ilogb function
- ilogbf function
- ilogbl function
ms.assetid: 9ef19d57-1caa-41d5-8233-2faad3562fcb
ms.openlocfilehash: 272544124dd8a8a666fc434516d3c45c73b1d011
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331679"
---
# <a name="ilogb-ilogbf-ilogbl"></a>ilogb, ilogbf, ilogbl

지정된 값의 밑이 2인 비편향 지수를 나타내는 정수를 검색합니다.

## <a name="syntax"></a>구문

```C
int ilogb(
   double x
);

int ilogb(
   float x
); //C++ only

int ilogb(
   long double x
); //C++ only

int ilogbf(
   float x
);

int ilogbl(
   long double x
);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
지정된 값입니다.

## <a name="return-value"></a>반환 값

성공한 경우의 밑이 2 인 지 수를 반환 *x* 로그인으로 **int** 값입니다.

그렇지 않으면 \<math.h>에 정의된 다음 값 중 하나를 반환합니다.

|입력|결과|
|-----------|------------|
|±0|FP_ILOGB0|
|±inf, ±nan, 무한|FP_ILOGBNAN|

오류는 [_matherr](matherr.md)에 지정된 대로 보고됩니다.

## <a name="remarks"></a>설명

때문에 C++ 오버 로드를 사용 하면 오버 로드를 호출할 수 있습니다 **ilogb** 및 반환 하는 **float** 및 **긴** **double** 형식입니다. C 프로그램에서 **ilogb** 항상 받아서 반환 된 **double**합니다.

이 함수를 호출 하는 것은 해당 호출 비슷합니다 **logb** 함수를 다음 반환 값을 캐스팅 **int**합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|C 헤더|C++ 헤더|
|-------------|--------------|------------------|
|**ilogb**, **ilogbf**, **ilogbl**|\<math.h>|\<cmath>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[frexp](frexp.md)<br/>
[logb, logbf, logbl, _logb, _logbf](logb-logbf-logbl-logb-logbf.md)<br/>
