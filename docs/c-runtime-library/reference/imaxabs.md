---
title: imaxabs
ms.date: 04/05/2018
apiname:
- imaxabs
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- imaxabs
helpviewer_keywords:
- imaxabs function
ms.assetid: de2566a3-1415-4e9a-91b5-7ac3a49ebf5e
ms.openlocfilehash: a7492e08c3a078698292923ce395524ab5327ecf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157502"
---
# <a name="imaxabs"></a>imaxabs

크기에 관계없이 정수의 절대값을 계산합니다.

## <a name="syntax"></a>구문

```C
intmax_t imaxabs(
   intmax_t n
);
```

### <a name="parameters"></a>매개 변수

*n*<br/>
정수 값입니다.

## <a name="return-value"></a>반환 값

합니다 **imaxabs** 함수 인수의 절대값을 반환 합니다. 반환되는 오류가 없습니다.

> [!NOTE]
> 때문에 사용 하 여 나타낼 수 있는 음의 정수 범위의 **intmax_t** 범위 보다 큰 나타낼 수 있는 양의 정수 인수를 제공할 수 있기 **imaxabs** 변환할 수 없습니다. 인수의 절대값을 반환 하 여 표현할 수 없는 경우 입력, 동작 **imaxabs** 정의 되지 않습니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**imaxabs**|\<inttypes.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

```C
// crt_imaxabs.c
// Build using: cl /W3 /Tc crt_imaxabs.c
// This example calls imaxabs to compute an
// absolute value, then displays the results.

#include <stdio.h>
#include <stdlib.h>
#include <inttypes.h>

int main(int argc, char *argv[])
{
   intmax_t x = LLONG_MIN + 2;

   printf("The absolute value of %lld is %lld\n", x, imaxabs(x));
}
```

```Output
The absolute value of -9223372036854775806 is 9223372036854775806
```

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[abs, labs, llabs, _abs64](abs-labs-llabs-abs64.md)<br/>
[_cabs](cabs.md)<br/>
[fabs, fabsf, fabsl](fabs-fabsf-fabsl.md)<br/>
