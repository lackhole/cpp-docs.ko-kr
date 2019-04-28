---
title: _clear87, _clearfp
ms.date: 04/05/2018
apiname:
- _clearfp
- _clear87
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- clearfp
- _clearfp
- _clear87
- clear87
helpviewer_keywords:
- clearing floating point status word
- clearfp function
- _clear87 function
- _clearfp function
- clear87 function
ms.assetid: 72d24a70-7688-4793-ae09-c96d33fcca52
ms.openlocfilehash: 4148f85d82a4210033686455c73046081832e3c4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62340555"
---
# <a name="clear87-clearfp"></a>_clear87, _clearfp

부동 소수점 상태 단어를 가져오고 지웁니다.

## <a name="syntax"></a>구문

```C
unsigned int _clear87( void );
unsigned int _clearfp( void );
```

## <a name="return-value"></a>반환 값

반환 된 값의 비트에 대 한 호출 전의 부동 소수점 상태를 나타냅니다 **_clear87** 하거나 **_clearfp**합니다. 반환 된 비트의 전체 정의 **_clear87**를 보려면 Float.h를 참조 합니다. 많은 수학 라이브러리 함수는 예기치 않은 결과를 포함하여 8087/80287 상태 단어를 수정합니다. 값 반환 **_clear87** 하 고 **_status87** 신뢰성이 높아집니다 부동 소수점 상태 단어의 알려진된 상태 간에 더 적은 부동 소수점 작업이 수행 됩니다.

## <a name="remarks"></a>설명

합니다 **_clear87** 함수는 부동 소수점 상태 단어의 예외 플래그를 지우고, 사용 중인 비트를 0으로 설정 및 상태 단어를 반환 합니다. 부동 소수점 상태 단어는 8087/80287 상태 단어와 8087/80287 예외 처리기에서 검색한 기타 조건(예: 부동 소수점 스택 오버플로 및 언더플로)의 조합입니다.

**_clearfp** 버전이 플랫폼 독립적 이며 휴대용 합니다 **_clear87** 루틴입니다. 동일 **_clear87** (x86) Intel 플랫폼에서 x64 및 ARM 플랫폼에서 지원 됩니다. 부동 소수점 코드를 x64 및 ARM에 이식 하려면 사용 하 여 **_clearfp**합니다. X86만 대상으로 하는 경우 플랫폼에서 사용할 수 있습니다 **_clear87** 하거나 **_clearfp**합니다.

로 컴파일하는 경우 이러한 함수는 사용 되지 않습니다 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 공용 언어 런타임은 기본 부동 소수점 정밀도만 지원 하기 때문입니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_clear87**|\<float.h>|
|**_clearfp**|\<float.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_clear87.c
// compile with: /Od

// This program creates various floating-point
// problems, then uses _clear87 to report on these problems.
// Compile this program with Optimizations disabled (/Od).
// Otherwise the optimizer will remove the code associated with
// the unused floating-point values.
//

#include <stdio.h>
#include <float.h>

int main( void )
{
   double a = 1e-40, b;
   float x, y;

   printf( "Status: %.4x - clear\n", _clear87()  );

   // Store into y is inexact and underflows:
   y = a;
   printf( "Status: %.4x - inexact, underflow\n", _clear87() );

   // y is denormal:
   b = y;
   printf( "Status: %.4x - denormal\n", _clear87() );
}
```

```Output
Status: 0000 - clear
Status: 0003 - inexact, underflow
Status: 80000 - denormal
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md)<br/>
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)<br/>
