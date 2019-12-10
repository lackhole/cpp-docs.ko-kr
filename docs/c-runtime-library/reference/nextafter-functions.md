---
title: nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl
ms.date: 04/05/2018
api_name:
- nextafterf
- _nextafterf
- nextafter
- nextafterl
- _nextafter
- nexttoward
- nexttowardf
- nexttowardl
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
ms.openlocfilehash: c6b100fb24d879a16780650d8a374ec26f28c048
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857725"
---
# <a name="nextafter-nextafterf-nextafterl-_nextafter-_nextafterf-nexttoward-nexttowardf-nexttowardl"></a>nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl

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

*Y*방향으로 *x* 이후 반환 형식에 대 한 표현 가능한 다음 부동 소수점 값을 반환 합니다. *X* 와 *y* 가 같으면 함수는 반환 형식으로 변환 된 *y*를 반환 하며 예외는 트리거되지 않습니다. *X* 가 *y*와 같지 않고 결과가 denormal 이거나 0 이면 **FE_UNDERFLOW** 및 **FE_INEXACT** 부동 소수점 예외 상태가 설정 되 고 올바른 결과가 반환 됩니다. *X* 또는 *y* 중 하나가 NAN 이면 반환 값은 입력 nan 중 하나입니다. *X* 가 유한 하 고 결과가 무한 이거나 형식에서 표현할 수 없는 경우에는 올바르게 서명 된 INFINITY 또는 NAN이 반환 되 고, **FE_OVERFLOW** 및 **FE_INEXACT** 부동 소수점 예외 상태가 설정 되며, **errno** 가 **ERANGE**로 설정 됩니다.

## <a name="remarks"></a>주의

*Y*의 매개 변수 형식을 제외한 **nextafter** 및 **nextafter** 패밀리는 동일 합니다. *X* 와 *y* 가 같으면 반환 되는 값은 *y* 반환 형식으로 변환 됩니다.

는 C++ 오버 로드를 허용 하므로 cmath > \<포함 하는 경우 **float** 및 **long** **double** 형식을 반환 하는 **nextafter 및** **nextafter** 의 오버 로드를 호출할 수 있습니다. C 프로그램에서 및 **nextafter** 및 **nextafter** 항상 **double**을 반환 합니다.

**_Nextafter** 및 **_Nextafterf** 함수는 Microsoft 전용입니다. **_Nextafterf** 함수는 x 64 용으로 컴파일하는 경우에만 사용할 수 있습니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더(C)|필수 헤더(C++)|
|-------------|---------------------------|-------------------------------|
|**nextafter**, **nextafterf**, **nextafterl**, **_nextafterf**, **nexttoward**, **nexttowardf**, **nexttowardl**|\<math.h>|\<math.h> 또는 \<cmath>|
|**_nextafter**|\<float.h>|\<float.h> 또는 \<cfloat>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참조

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
