---
title: asin, asinf, asinl
ms.date: 04/05/2018
apiname:
- asinf
- asinl
- asin
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
- asin
- asinl
- asinf
helpviewer_keywords:
- asin function
- asinl function
- asinf function
- trigonometric functions
- arcsine function
ms.assetid: ca05f9ea-b711-49f6-9f32-2f4019abfd69
ms.openlocfilehash: 20a2ffc37ea666207b9558cb5c282c414cfd4838
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62347966"
---
# <a name="asin-asinf-asinl"></a>asin, asinf, asinl

아크사인을 계산합니다.

## <a name="syntax"></a>구문

```C
double asin( double x );
float asinf ( float x );
long double asinl( long double x );
```

```cpp
float asin( float x );  // C++ only
long double asin( long double x );  // C++ only
```

### <a name="parameters"></a>매개 변수

*x*<br/>
아크사인을 계산해야 하는 값입니다.

## <a name="return-value"></a>반환 값

합니다 **asin** 의 아크사인 (역 사인 함수)를 반환 *x* 는 범위-π/2 ~ π/2 라디안에서에서.

기본적으로 하는 경우 *x* -1 보다 작거나 1 보다 크면 **asin** 는 무한 한 값을 반환 합니다.

|입력|SEH 예외|Matherr 예외|
|-----------|-------------------|-----------------------|
|± ∞|**INVALID**|**_DOMAIN**|
|± **QNAN**, **IND**|없음|**_DOMAIN**|
|&#124;x&#124;>1|**INVALID**|**_DOMAIN**|

## <a name="remarks"></a>설명

때문에 C++ 오버 로드를 사용 하면 오버 로드를 호출할 수 있습니다 **asin** 사용 하 여 **float** 및 **긴** **double** 값입니다. C 프로그램에서 **asin** 항상 받아서 반환 된 **double**합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더(C)|필수 헤더(C++)|
|-------------|---------------------|-|
|**asin**, **asinf**, **asinl**|\<math.h>|\<cmath> 또는 \<math.h>|

## <a name="example"></a>예제

자세한 내용은 [acos, acosf, acosl](acos-acosf-acosl.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[acos, acosf, acosl](acos-acosf-acosl.md)<br/>
[atan, atanf, atanl, atan2, atan2f, atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[_matherr](matherr.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
[tan, tanf, tanl](tan-tanf-tanl.md)<br/>
