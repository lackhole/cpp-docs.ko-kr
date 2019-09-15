---
title: _cabs
ms.date: 11/04/2016
api_name:
- _cabs
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
- cabsl
- _cabs
- _cabsl
helpviewer_keywords:
- cabs function
- cabsl function
- absolute values
- _cabsl function
- _cabs function
- calculating absolute values
ms.assetid: fea292ee-1a39-4a0a-b416-4a189346ff26
ms.openlocfilehash: 5e2536fbeed2f466d3795e2ed26e643279e8bc67
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70943420"
---
# <a name="_cabs"></a>_cabs

복소수의 절대값을 계산합니다.

## <a name="syntax"></a>구문

```C
double _cabs(
   struct _complex z
);
```

### <a name="parameters"></a>매개 변수

*z*<br/>
복소수입니다.

## <a name="return-value"></a>반환 값

**_wfa** 는 성공 하는 경우 인수의 절대값을 반환 합니다. 오버플로가 발생 하면 **errno** 는 **HUGE_VAL** **를 반환** 하 고 **ERANGE**로 설정 합니다. [_matherr](matherr.md)을 사용하여 오류 처리를 변경할 수 있습니다.

## <a name="remarks"></a>설명

**_Cinta** 함수는 복합 형식의 절대값을 계산 합니다 .이 값은 [_cabs](../../c-runtime-library/standard-types.md)형식의 구조체 여야 합니다. 구조체 *z* 는 실제 구성 요소 *x* 및 허수 구성 요소 *y*로 구성 됩니다. **_Ba** 를 호출 하면 식 `sqrt( z.x * z.x + z.y * z.y )`의 값과 동일한 값이 생성 됩니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_cabs**|\<math.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_cabs.c
// Using _cabs, this program calculates
// the absolute value of a complex number.

#include <math.h>
#include <stdio.h>

int main( void )
{
   struct _complex number = { 3.0, 4.0 };
   double d;

   d = _cabs( number );
   printf( "The absolute value of %f + %fi is %f\n",
           number.x, number.y, d );
}
```

```Output
The absolute value of 3.000000 + 4.000000i is 5.000000
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[abs, labs, llabs, _abs64](abs-labs-llabs-abs64.md)<br/>
[fabs, fabsf, fabsl](fabs-fabsf-fabsl.md)