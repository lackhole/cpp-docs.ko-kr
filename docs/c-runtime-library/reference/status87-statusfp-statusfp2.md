---
title: _status87, _statusfp, _statusfp2
ms.date: 04/05/2018
apiname:
- _statusfp2
- _statusfp
- _status87
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
- _statusfp2
- _statusfp
- statusfp2
- _status87
- status87
- statusfp
helpviewer_keywords:
- floating-point functions, getting status word
- floating-point numbers, status word
- status87 function
- status word, getting floating point
- statusfp function
- _statusfp function
- _statusfp2 function
- statusfp2 function
- _status87 function
- floating-point functions
- status word
ms.assetid: 7ef963fa-b1fb-429d-94d6-fbf282ab7432
ms.openlocfilehash: 271c28dd4e267e5b3b702858cc398689e3e35d6f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62354433"
---
# <a name="status87-statusfp-statusfp2"></a>_status87, _statusfp, _statusfp2

부동 소수점 상태 단어를 가져옵니다.

## <a name="syntax"></a>구문

```C
unsigned int _status87( void );
unsigned int _statusfp( void );
void _statusfp2(unsigned int *px86, unsigned int *pSSE2)
```

### <a name="parameters"></a>매개 변수

*px86*<br/>
이 주소에는 x87 부동 소수점 단위의 상태 단어가 채워집니다.

*pSSE2*<br/>
이 주소에는 SSE2 부동 소수점 단위의 상태 단어가 채워집니다.

## <a name="return-value"></a>반환 값

에 대 한 **_status87** 하 고 **_statusfp**, 반환 되는 값의 비트는 부동 소수점 상태를 나타냅니다. 부동 소수점을 참조 하세요. 반환 되는 비트의 정의 대 한 파일을 포함 하는 H **_statusfp**합니다. 대부분의 수학 라이브러리 함수는 부동 소수점 상태 단어를 수정하는데, 이 경우 예기치 않은 결과가 발생합니다. 최적화 수 다시 정렬, 결합 및 부동 소수점 연산에 대 한 호출을 제거 **_status87**를 **_statusfp**, 및 관련 함수입니다. 부동 소수점 연산을 다시 정렬하는 최적화가 수행되지 않도록 하려면 [/Od (Disable (Debug))](../../build/reference/od-disable-debug.md) 컴파일러 옵션 또는 [fenv_access](../../preprocessor/fenv-access.md) pragma 지시문을 사용합니다. 값이 반환 **_clearfp** 및 **_statusfp**, 및의 반환 매개 변수 또한 **_statusfp2**, 더 적은 부동 소수점 작업을 수행 하는 경우 신뢰할 수 사이의 부동 소수점 상태 단어의 알려진된 상태입니다.

## <a name="remarks"></a>설명

합니다 **_statusfp** 함수는 부동 소수점 상태 단어를 가져옵니다. 상태 단어는 부동 소수점 프로세서 상태와 부동 소수점 예외 처리기에서 검색한 기타 조건(예: 부동 소수점 스택 오버플로 및 언더플로)의 조합입니다. 상태 단어의 내용을 반환하기 전에 마스킹되지 않은 예외를 확인합니다. 즉, 호출자에게 보류 중인 예외를 알립니다. X86 플랫폼 **_statusfp** 는 x87 및 SSE2 부동 소수점 상태의 조합을 반환 합니다. x64 플랫폼에서 반환되는 상태는 SSE의 MXCSR 상태를 기준으로 합니다. ARM 플랫폼에서는 **_statusfp** 는 FPSCR 레지스터에서 상태를 반환 합니다.

**_statusfp** 버전이 플랫폼 독립적 이며 휴대용 **_status87**합니다. 동일 **_status87** (x86) Intel 플랫폼에서 x64 및 ARM 플랫폼에서 지원 됩니다. 사용 하 여 부동 소수점 코드를 모든 아키텍처로 이식할 수 있도록 **_statusfp**합니다. X86만 대상으로 하는 경우 플랫폼에서 사용할 수 있습니다 **_status87** 하거나 **_statusfp**합니다.

것이 좋습니다 **_statusfp2** 는 x87 및 SSE2 부동 소수점 프로세서를 모두 있는 (예: Pentium IV) 칩에 대 한 합니다. 에 대 한 **_statusfp2**, 주소는 x87 또는 SSE2 부동 소수점 프로세서 둘 다에 대 한 부동 소수점 상태 단어를 사용 하 여 채워집니다. X87 및 SSE2 부동 소수점 프로세서를 지 원하는 칩을 EM_AMBIGUOUS 경우 1로 설정 됩니다 **_statusfp** 하거나 **_controlfp** 는 x87 또는 SSE2를 참조할 수 있으므로 작업이 모호 하 고 부동 소수점 상태 단어입니다. 합니다 **_statusfp2** 함수는 x86만 지원 플랫폼입니다.

이러한 함수에 대 한 유용 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 는 CLR (공용 언어 런타임)은 기본 부동 소수점 정밀도만 지원 하기 때문입니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_status87**, **_statusfp**, **_statusfp2**|\<float.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_statusfp.c
// Build by using: cl /W4 /Ox /nologo crt_statusfp.c
// This program creates various floating-point errors and
// then uses _statusfp to display messages that indicate these problems.

#include <stdio.h>
#include <float.h>
#pragma fenv_access(on)

double test( void )
{
   double a = 1e-40;
   float b;
   double c;

   printf("Status = 0x%.8x - clear\n", _statusfp());

   // Assignment into b is inexact & underflows:
   b = (float)(a + 1e-40);
   printf("Status = 0x%.8x - inexact, underflow\n", _statusfp());

   // c is denormal:
   c = b / 2.0;
   printf("Status = 0x%.8x - inexact, underflow, denormal\n",
            _statusfp());

   // Clear floating point status:
   _clearfp();
   return c;
}

int main(void)
{
   return (int)test();
}
```

```Output
Status = 0x00000000 - clear
Status = 0x00000003 - inexact, underflow
Status = 0x00080003 - inexact, underflow, denormal
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87, _clearfp](clear87-clearfp.md)<br/>
[_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md)<br/>
