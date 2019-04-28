---
title: _control87, _controlfp, __control87_2
ms.date: 04/05/2018
apiname:
- _control87
- _controlfp
- __control87_2
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
- _control87
- __control87_2
- control87
- _controlfp
- controlfp
- control87_2
- _control87_2
helpviewer_keywords:
- floating-point numbers, control word
- _control87 function
- control87 function
- controlfp function
- _controlfp function
- __control87_2 function
- floating-point functions, setting control word
- floating-point functions
- EM_AMBIGUOUS
- control87_2 function
ms.assetid: 0d09729d-d9a0-43d6-864c-43ff25e7e0c5
ms.openlocfilehash: e2ebfdc80a451ebf02563f78a62dd08618f92bcd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62340419"
---
# <a name="control87-controlfp-control872"></a>_control87, _controlfp, __control87_2

부동 소수점 제어 단어를 가져와서 설정합니다. 더 안전한 버전 **_controlfp** 참조를 사용할 수 있습니다 [_controlfp_s](controlfp-s.md)합니다.

## <a name="syntax"></a>구문

```C
unsigned int _control87(
   unsigned int new,
   unsigned int mask
);
unsigned int _controlfp(
   unsigned int new,
   unsigned int mask
);
int __control87_2(
   unsigned int new,
   unsigned int mask,
   unsigned int* x86_cw,
   unsigned int* sse2_cw
);
```

### <a name="parameters"></a>매개 변수

*new*<br/>
새 제어 단어 비트 값입니다.

*mask*<br/>
설정할 새 제어 단어 비트의 마스크입니다.

*x86_cw*<br/>
x87 부동 소수점 유닛에 대한 제어 단어로 채워집니다. 0을 전달 (**NULL**) SSE2 제어 단어만 설정할 수 있습니다.

*sse2_cw*<br/>
SSE 부동 소수점 유닛에 대한 제어 단어입니다. 0을 전달 (**NULL**)만 x87을 설정 하려면 제어 단어입니다.

## <a name="return-value"></a>반환 값

에 대 한 **_control87** 하 고 **_controlfp**, 값의 비트 부동 소수점 제어 상태를 나타내는 반환 합니다. 반환 되는 비트의 전체 정의 **_control87**, FLOAT를 참조 하세요. 8.

에 대 한 **__control87_2**, 반환 값은 성공을 나타내는 1입니다.

## <a name="remarks"></a>설명

합니다 **_control87** 함수를 가져오고 부동 소수점 제어 단어를 설정 합니다. 부동 소수점 제어 단어를 사용하면 프로그램이 플랫폼에 따라 부동 소수점 연산 패키지에서 정밀도, 반올림 및 무한대 모드를 변경할 수 있습니다. 사용할 수도 있습니다 **_control87** 마스크 또는 부동 소수점 예외를 마스크 해제 합니다. 경우에 대 한 값 *마스크* 는 0과 같지 **_control87** 부동 소수점 제어 단어를 가져옵니다. 하는 경우 *마스크* 는 0이 아닌 경우 새 제어 단어 값 설정 됩니다. 모든 비트에 (즉, 1과 같음)의 *마스크*에서 해당 비트가 *새* 제어 단어를 업데이트 하는 데 사용 됩니다. 다시 말해 **fpcntrl** = ((**fpcntrl** & ~*마스크*) &#124; (*새* & *마스크*)) 여기서 **fpcntrl** 부동 소수점 제어 단어입니다.

> [!NOTE]
> 기본적으로 런타임 라이브러리는 모든 부동 소수점 예외를 마스킹합니다.

**_controlfp** 버전이 플랫폼 독립적 이며 휴대용 **_control87**합니다. 거의 동일 합니다 **_control87** x86, x64 및 ARM 플랫폼에는 함수입니다. X86, x64 또는 ARM 플랫폼에 대상으로 하는 경우 사용 하 여 **_control87** 하거나 **_controlfp**합니다.

차이점 **_control87** 하 고 **_controlfp** DENORMAL 값을 처리 하는 방법에 있습니다. X86, x64 및 ARM 플랫폼에 대 한 **_control87** 집합과 DENORMAL OPERAND 예외 마스크를 지울 수 있습니다. **_controlfp** DENORMAL OPERAND 예외 마스크를 수정 하지는 않습니다. 이 예제에서는 다음과 같은 차이를 보여 줍니다.

```C
_control87( _EM_INVALID, _MCW_EM );
// DENORMAL is unmasked by this call
_controlfp( _EM_INVALID, _MCW_EM );
// DENORMAL exception mask remains unchanged
```

마스크 상수에 대 한 가능한 값 (*마스크*) 및 새 제어 값 (*새*) 16 진수 값 표에 표시 됩니다. 아래에 나열 된 이식 가능 상수를 사용 하 여 (**_MCW_EM**하십시오 **_EM_INVALID**등) 이러한 함수를 인수로 16 진수를 제공 하는 대신 값을 명시적으로 합니다.

Intel x86 파생 DENORMAL 입력을 지 원하는 플랫폼과 하드웨어에서 값을 출력 합니다. x86 동작은 DENORMAL 값을 유지하는 것입니다. ARM 플랫폼을 x64 플랫폼을 SSE2 지원 통해 DENORMAL 피연산자 및 결과가 플러시 되거나 0으로 강제를 사용 하도록 설정 합니다. 합니다 **_controlfp** 하 고 **_control87** 함수는이 동작을 변경 하는 마스크를 제공 합니다. 다음 예제에서는 이 마스크의 사용을 보여 줍니다.

```C
_controlfp(_DN_SAVE, _MCW_DN);
// Denormal values preserved on ARM platforms and on x64 processors with
// SSE2 support. NOP on x86 platforms.
_controlfp(_DN_FLUSH, _MCW_DN);
// Denormal values flushed to zero by hardware on ARM platforms
// and x64 processors with SSE2 support. Ignored on other x86 platforms.
```

ARM 플랫폼에서의 **_control87** 하 고 **_controlfp** 함수는 FPSCR 레지스터에 적용 합니다. X64 아키텍처에 저장 되어 있는 SSE2 제어 단어만 MXCSR 레지스터 달라 집니다. X86 플랫폼 **_control87** 및 **_controlfp** 있으면는 x87 및 SSE2를 둘 다에 대 한 제어 단어에 영향을 줍니다. 함수 **__control87_2** x87 및 SSE2 부동 소수점 유닛을 함께 또는 별도로 제어할 수 있습니다. 두 장치 모두에 영향을 하려는 경우 두 정수의 주소에 전달 **x86_cw** 하 고 **sse2_cw**합니다. 하나의 단위에 영향을 하려는 경우 해당 매개 변수에 대 한 주소를 전달 하지만 0 전달 (**NULL**) 다른 합니다. 이러한 매개 변수 중 하나에 대해 0을 전달하면 함수가 부동 소수점 유닛에는 영향을 주지 않습니다. 이 기능은 코드의 일부에서 x87 부동 소수점 유닛을 사용하고 유닛의 다른 부분에서는 SSE2 부동 소수점 유닛을 사용하는 경우에 유용할 수 있습니다. 사용 하는 경우 **__control87_2** 프로그램의 한 부분에서 및 부동 소수점 제어 단어를 서로 다른 값을 설정 하 고 사용 하 여 **_control87** 하거나 **_controlfp** 자세히 그런 다음 제어 단어를 조작 **_control87** 하 고 **_controlfp** 모두 부동 소수점 단위의 상태를 나타내는 단일 제어 단어를 반환 하는 일을 할 수 있습니다. 이러한 경우 이러한 함수는 다음과 같이 설정 됩니다.는 **EM_AMBIGUOUS** 두 제어 단어 간의 불일치가 있음을 나타내기에 반환 된 정수 값을 플래그 합니다. 이는 반환된 제어 단어가 두 부동 소수점 제어 단어 모두의 상태를 정확히 나타내지 않을 수 있다는 경고입니다.

ARM 및 x64 아키텍처 변경 무한대 모드 또는 부동 소수점 정밀도만 지원 되지 않습니다. 정밀도 제어 마스크가 x64에 사용 되는 경우 플랫폼에는 어설션을 발생 시키고에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다.

> [!NOTE]
> **__control87_2** 은 ARM 또는 x64에서 지원 되지 않습니다 아키텍처입니다. 사용 하는 경우 **__control87_2** 은 ARM 또는 x64 용 프로그램을 컴파일 및 아키텍처, 컴파일러가 오류를 생성 합니다.

사용 하는 경우 이러한 함수가 무시 됩니다 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 는 CLR (공용 언어 런타임) 기본 부동 소수점 정밀도만 지원 하기 때문에 컴파일할 수 있습니다.

**16진수 값**

에 대 한 합니다 **_MCW_EM** 하드웨어 예외가 허용 하는 예외를 설정 하는 마스크를 지우면 마스크; 하면 예외가 숨겨집니다 마스크를 설정 합니다. 경우는 **_EM_UNDERFLOW** 하거나 **_EM_OVERFLOW** 발생 하면 다음 부동 소수점 명령이 실행 될 때까지 하드웨어 예외가 throw 됩니다. 하드웨어 예외를 생성 하려면 직후 **_EM_UNDERFLOW** 또는 **_EM_OVERFLOW**를 호출 합니다 **FWAIT** MASM 명령을 합니다.

|마스크|16진수 값|상수|16진수 값|
|----------|---------------|--------------|---------------|
|**_MCW_DN** (비정상 제어)|0x03000000|**_DN_SAVE**<br /><br /> **_DN_FLUSH**|0x00000000<br /><br /> 0x01000000|
|**_MCW_EM** (인터럽트 예외 마스크)|0x0008001F|**_EM_INVALID**<br /><br /> **_EM_DENORMAL**<br /><br /> **_EM_ZERODIVIDE**<br /><br /> **_EM_OVERFLOW**<br /><br /> **_EM_UNDERFLOW**<br /><br /> **_EM_INEXACT**|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|
|**_MCW_IC** (무한대 제어)<br /><br /> (ARM 또는 x64에서 지원 되지 않음] 플랫폼입니다.)|0x00040000|**_IC_AFFINE**<br /><br /> **_IC_PROJECTIVE**|0x00040000<br /><br /> 0x00000000|
|**_MCW_RC** (반올림 제어)|0x00000300|**_RC_CHOP**<br /><br /> **_RC_UP**<br /><br /> **_RC_DOWN**<br /><br /> **_RC_NEAR**|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|
|**_MCW_PC** (정밀도 제어)<br /><br /> (지원 되지 않음 ARM 또는 x64 플랫폼입니다.)|0x00030000|**_PC_24** (24 비트)<br /><br /> **_PC_53** (53 비트)<br /><br /> **_PC_64** (64 비트)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_control87**, **_controlfp**, **_control87_2**|\<float.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_cntrl87.c
// processor: x86
// This program uses __control87_2 to output the x87 control
// word, set the precision to 24 bits, and reset the status to
// the default.

#include <stdio.h>
#include <float.h>
#pragma fenv_access (on)

int main( void )
{
    double a = 0.1;
    unsigned int control_word_x87;

    // Show original x87 control word and do calculation.
    control_word_x87 = __control87_2(0, 0,
                                     &control_word_x87, 0);
    printf( "Original: 0x%.4x\n", control_word_x87 );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Set precision to 24 bits and recalculate.
    control_word_x87 = __control87_2(_PC_24, MCW_PC,
                                     &control_word_x87, 0);
    printf( "24-bit:   0x%.4x\n", control_word_x87 );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Restore default precision-control bits and recalculate.
    control_word_x87 = __control87_2( _CW_DEFAULT, MCW_PC,
                                     &control_word_x87, 0 );
    printf( "Default:  0x%.4x\n", control_word_x87 );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );
}
```

```Output
Original: 0x0001
0.1 * 0.1 = 1.000000000000000e-002
24-bit:   0x0001
0.1 * 0.1 = 9.999999776482582e-003
Default:  0x0001
0.1 * 0.1 = 1.000000000000000e-002
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87, _clearfp](clear87-clearfp.md)<br/>
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)<br/>
[_controlfp_s](controlfp-s.md)<br/>
