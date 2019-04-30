---
title: nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl
ms.date: 04/05/2018
apiname:
- nextafterf
- _nextafterf
- nextafter
- nextafterl
- _nextafter
- nexttoward
- nexttowardf
- nexttowardl
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
- nextafter
- _nextafter
- nextafterf
- nextafterl
- _nextafterf
- math/nextafter
- math/nextafterf
- math/nextafterl
- nexttoward
- nexttowardf
- nexttowardl
- math/nexttoward
- math/nexttowardf
- math/nexttowardl
helpviewer_keywords:
- _nextafter function
- nextafter function
- _nextafterf function
- nextafterf function
- nextafterl function
- nexttoward function
- nexttowardf function
- nexttowardl function
ms.assetid: 9785bfb9-de53-4bd0-9637-f05fa0c1f6ab
ms.openlocfilehash: 0e0a60dc9f7c068d8c18c10f3c6b819b9e06d3b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156189"
---
# <a name="nextafter-nextafterf-nextafterl-nextafter-nextafterf-nexttoward-nexttowardf-nexttowardl"></a>nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl

표현 가능한 다음 부동 소수점 값을 반환합니다.

## <a name="syntax"></a>구문

```C
double nextafter( double x, double y );
float nextafterf( float x, float y );
long double nextafterl( long double x, long double y );

double _nextafter( double x, double y );
float _nextafterf( float x, float y ); /* x64 only */

double nexttoward( double x, long double y );
float nexttowardf( float x, long double y );
long double nexttowardl( long double x, long double y );
```

```cpp
float nextafter( float x, float y ); /* C++ only, requires <cmath> */
long double nextafter( long double x, long double y ); /* C++ only, requires <cmath> */

float nexttoward( float x, long double y ); /* C++ only, requires <cmath> */
long double nexttoward( long double x, long double y ); /* C++ only, requires <cmath> */
```

### <a name="parameters"></a>매개 변수

*x*<br/>
시작할 부동 소수점 값입니다.

*y*<br/>
종료할 부동 소수점 값입니다.

## <a name="return-value"></a>반환 값

후 반환 형식의 다음 표현 가능한 부동 소수점 값을 반환 합니다 *x* 방향의 *y*합니다. 하는 경우 *x* 하 고 *y* 같으면 반환 *y*트리거된 예외가 없는 반환 형식으로 변환 합니다. 하는 경우 *x* 같지 *y*, 비정상적인 값 이거나 0 이면 결과 합니다 **FE_UNDERFLOW** 및 **FE_INEXACT** 부동 소수점 예외 상태 설정 되 고 올바른 결과 반환 됩니다. 이면 *x* 또는 *y* NAN 이면 반환 값은 입력된 Nan 중 하나입니다. 하는 경우 *x* 한정 되어 있으므로 결과 무한 또는 형식으로 표현할 수 없습니다, 제대로 서명 된 무한대 또는 NAN 인 반환 됩니다, **FE_OVERFLOW** 하 고 **FE_INEXACT** 부동 소수점 예외 상태가 설정 되며, 및 **errno** 로 설정 된 **ERANGE**합니다.

## <a name="remarks"></a>설명

합니다 **nextafter** 하 고 **nexttoward** 함수 패밀리는 매개 변수 형식 제외 하면 동일 *y*합니다. 하는 경우 *x* 하 고 *y* 는 같음, 값이 반환 됩니다 *y* 반환 형식으로 변환 합니다.

때문에 C++ 오버 로드를 포함 하는 경우 허용 \<cmath > 오버 로드를 호출할 수 있습니다 **nextafter** 하 고 **nexttoward** 반환 하는 **float** 및 **긴** **double** 형식입니다. C 프로그램에서 **nextafter** 하 고 **nexttoward** 항상 반환 **double**합니다.

합니다 **_nextafter** 하 고 **_nextafterf** 함수는 Microsoft 전용입니다. 합니다 **_nextafterf** x64 용으로 컴파일할 때 함수를 사용할 수만 있습니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더(C)|필수 헤더(C++)|
|-------------|---------------------------|-------------------------------|
|**nextafter**, **nextafterf**, **nextafterl**, **_nextafterf**, **nexttoward**, **nexttowardf**, **nexttowardl**|\<math.h>|\<math.h> 또는 \<cmath>|
|**_nextafter**|\<float.h>|\<float.h> 또는 \<cfloat>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
