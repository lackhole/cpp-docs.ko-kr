---
title: _controlfp_s
ms.date: 04/05/2018
apiname:
- _controlfp_s
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
- controlfp_s
- _controlfp_s
helpviewer_keywords:
- floating-point numbers, control word
- controlfp_s function
- floating-point functions, setting control word
- EM_AMBIGUOUS
- _controlfp_s function
ms.assetid: a51fc3f6-ab13-41f0-b227-6bf02d98e987
ms.openlocfilehash: 0624cbfb4870ca87efebac01a8de682b588a4ca3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62335385"
---
# <a name="controlfps"></a>_controlfp_s

부동 소수점 제어 단어를 가져와서 설정합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 [_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md)의 이 버전에는 보안 향상 기능이 있습니다.

## <a name="syntax"></a>구문

```C
errno_t _controlfp_s(
    unsigned int *currentControl,
    unsigned int newControl,
    unsigned int mask
);
```

### <a name="parameters"></a>매개 변수

*currentControl*<br/>
현재 제어 단어 비트 값입니다.

*newControl*<br/>
새 제어 단어 비트 값입니다.

*mask*<br/>
설정할 새 제어 단어 비트의 마스크입니다.

## <a name="return-value"></a>반환 값

성공 하면 또는 zero **errno** 오류 코드 값입니다.

## <a name="remarks"></a>설명

합니다 **_controlfp_s** 함수는 플랫폼 독립적인 더 안전한 버전의 **_control87**에 저장 되어 있는 주소로 부동 소수점 제어 단어를 가져오는  *currentControl* 를 사용 하 여 설정 합니다 *newControl*합니다. 값의 비트는 부동 소수점 제어 상태를 나타냅니다. 부동 소수점 제어 상태를 사용하면 프로그램이 플랫폼에 따라 부동 소수점 연산 패키지에서 정밀도, 반올림 및 무한대 모드를 변경할 수 있습니다. 사용할 수도 있습니다 **_controlfp_s** 마스크 또는 부동 소수점 예외를 마스크 해제 합니다.

경우에 대 한 값 *마스크* 는 0과 같지 **_controlfp_s** 부동 소수점 제어 단어를 가져와에서 검색된 된 값 *currentControl*합니다.

하는 경우 *마스크* 는 0이 아닌 경우 새 제어 단어 값 설정 됩니다. 모든 비트는 설정 됩니다 (즉, 1과 같음)에서 *마스크*에서의 해당 비트가 *새* 제어 단어를 업데이트 하는 데 사용 됩니다. 다시 말해 *fpcntrl* = ((*fpcntrl* & ~*마스크*) &#124; (*newControl* & *마스크* )) 여기서 *fpcntrl* 부동 소수점 제어 단어입니다. 이 시나리오에서는 *currentControl* 후 값으로 설정 된 경우 변경이 완료 된; 이전 제어 단어 비트 값이 아닙니다.

> [!NOTE]
> 기본적으로 런타임 라이브러리는 모든 부동 소수점 예외를 마스킹합니다.

**_controlfp_s** 거의 동일 합니다 **_control87** (x86), x64 및 ARM 플랫폼 Intel에서 작동 합니다. X86, x64 또는 ARM 플랫폼에 대상으로 하는 경우 사용할 수 있습니다 **_control87** 하거나 **_controlfp_s**합니다.

차이점 **_control87** 하 고 **_controlfp_s** denormal 처리 하는 방법에 값입니다. X64 및 ARM 플랫폼 (x86)에서 intel **_control87** 집합과 DENORMAL OPERAND 예외 마스크를 지울 수 있습니다. **_controlfp_s** DENORMAL OPERAND 예외 마스크를 수정 하지는 않습니다. 이 예제에서는 다음과 같은 차이를 보여 줍니다.

```C
_control87( _EM_INVALID, _MCW_EM );
// DENORMAL is unmasked by this call.
unsigned int current_word = 0;
_controlfp_s( &current_word, _EM_INVALID, _MCW_EM );
// DENORMAL exception mask remains unchanged.
```

마스크 상수에 대 한 가능한 값 (*마스크*) 및 새 제어 값 (*newControl*) 16 진수 값 표에 표시 됩니다. 아래에 나열 된 이식 가능 상수를 사용 하 여 (**_MCW_EM**를 **_EM_INVALID**등) 이러한 함수를 인수로 16 진수를 제공 하는 대신 값을 명시적으로 합니다.

Intel(x86) 파생 플랫폼에서는 하드웨어의 DENORMAL 입력 및 출력 값을 지원합니다. x86 동작은 DENORMAL 값을 유지하는 것입니다. ARM 플랫폼을 x64 플랫폼을 SSE2 지원 통해 DENORMAL 피연산자 및 결과가 플러시 되거나 0으로 강제를 사용 하도록 설정 합니다. 합니다 **_controlfp_s**를 **_controlfp**, 및 **_control87** 함수는이 동작을 변경 하는 마스크를 제공 합니다. 다음 예제에서는 이 마스크의 사용을 보여 줍니다.

```C
unsigned int current_word = 0;
_controlfp_s(&current_word, _DN_SAVE, _MCW_DN);
// Denormal values preserved on ARM platforms and on x64 processors with
// SSE2 support. NOP on x86 platforms.
_controlfp_s(&current_word, _DN_FLUSH, _MCW_DN);
// Denormal values flushed to zero by hardware on ARM platforms
// and x64 processors with SSE2 support. Ignored on other x86 platforms.
```

ARM 플랫폼에서의 **_controlfp_s** 함수는 FPSCR 레지스터에 적용 됩니다. X64 아키텍처에 저장 되어 있는 SSE2 제어 단어만 MXCSR 레지스터 달라 집니다. Intel (x86) 플랫폼 **_controlfp_s** 있으면는 x87 및 SSE2를 둘 다에 대 한 제어 단어에 영향을 줍니다. 두 개의 제어 단어가 서로 일관 되지 않을 수 있기 (이전 호출으로 인해 [__control87_2](control87-controlfp-control87-2.md)예를 들어)는 두 개의 제어 단어 간의 일관성이 없을 경우 **_controlfp_s** 설정 합니다 **EM_AMBIGUOUS** 플래그 *currentControl*합니다. 이는 반환된 제어 단어가 두 부동 소수점 제어 단어 모두의 상태를 정확히 나타내지 않을 수 있다는 경고입니다.

ARM 및 x64 아키텍처 변경 무한대 모드 또는 부동 소수점 정밀도만 지원 되지 않습니다. 정밀도 제어 마스크가 x64에 사용 되는 경우 플랫폼에는 어설션을 발생 시키고에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다.

마스크가 올바르게 설정되지 않은 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 이 함수에서 잘못된 매개 변수 예외를 생성합니다. 실행을 계속 하도록 허용 된 경우이 함수를 반환 합니다 **EINVAL** 집합과 **errno** 하 **EINVAL**합니다.

사용 하는 경우이 함수는 무시 됩니다 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 는 CLR (공용 언어 런타임) 기본 부동 소수점 정밀도만 지원 하기 때문에 컴파일할 수 있습니다.

### <a name="mask-constants-and-values"></a>마스크 상수 및 값

에 대 한 합니다 **_MCW_EM** 하드웨어 예외가 허용 하는 예외를 설정 하는 선택을 마스크; 예외가 숨겨집니다. 경우는 **_EM_UNDERFLOW** 하거나 **_EM_OVERFLOW** 발생 하면 다음 부동 소수점 명령이 실행 될 때까지 하드웨어 예외가 throw 됩니다. 하드웨어 예외를 생성 하려면 직후 **_EM_UNDERFLOW** 하거나 **_EM_OVERFLOW**, FWAIT MASM 명령을 호출 합니다.

|마스크|16진수 값|상수|16진수 값|
|----------|---------------|--------------|---------------|
|**_MCW_DN** (비정상 제어)|0x03000000|**_DN_SAVE**<br /><br /> **_DN_FLUSH**|0x00000000<br /><br /> 0x01000000|
|**_MCW_EM** (인터럽트 예외 마스크)|0x0008001F|**_EM_INVALID**<br /><br /> **_EM_DENORMAL**<br /><br /> **_EM_ZERODIVIDE**<br /><br /> **_EM_OVERFLOW**<br /><br /> **_EM_UNDERFLOW**<br /><br /> **_EM_INEXACT**|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|
|**_MCW_IC** (무한대 제어)<br /><br /> (지원 되지 않음 ARM 또는 x64 플랫폼입니다.)|0x00040000|**_IC_AFFINE**<br /><br /> **_IC_PROJECTIVE**|0x00040000<br /><br /> 0x00000000|
|**_MCW_RC** (반올림 제어)|0x00000300|**_RC_CHOP**<br /><br /> **_RC_UP**<br /><br /> **_RC_DOWN**<br /><br /> **_RC_NEAR**|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|
|**_MCW_PC** (정밀도 제어)<br /><br /> (지원 되지 않음 ARM 또는 x64 플랫폼입니다.)|0x00030000|**_PC_24** (24 비트)<br /><br /> **_PC_53** (53 비트)<br /><br /> **_PC_64** (64 비트)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_controlfp_s**|\<float.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_contrlfp_s.c
// processor: x86
// This program uses _controlfp_s to output the FP control
// word, set the precision to 24 bits, and reset the status to
// the default.

#include <stdio.h>
#include <float.h>
#pragma fenv_access (on)

int main( void )
{
    double a = 0.1;
    unsigned int control_word;
    int err;

    // Show original FP control word and do calculation.
    err = _controlfp_s(&control_word, 0, 0);
    if ( err ) /* handle error here */;

    printf( "Original: 0x%.4x\n", control_word );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Set precision to 24 bits and recalculate.
    err = _controlfp_s(&control_word, _PC_24, MCW_PC);
    if ( err ) /* handle error here */;

    printf( "24-bit:   0x%.4x\n", control_word );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Restore default precision-control bits and recalculate.
    err = _controlfp_s(&control_word, _CW_DEFAULT, MCW_PC);
    if ( err ) /* handle error here */;

    printf( "Default:  0x%.4x\n", control_word );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );
}
```

```Output
Original: 0x9001f
0.1 * 0.1 = 1.000000000000000e-002
24-bit:   0xa001f
0.1 * 0.1 = 9.999999776482582e-003
Default:  0x9001f
0.1 * 0.1 = 1.000000000000000e-002
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87, _clearfp](clear87-clearfp.md)<br/>
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)<br/>
[_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md)<br/>
