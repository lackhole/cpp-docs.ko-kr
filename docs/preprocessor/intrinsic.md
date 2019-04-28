---
title: intrinsic
ms.date: 04/11/2018
f1_keywords:
- intrinsic_CPP
- vc-pragma.intrinsic
helpviewer_keywords:
- intrinsic pragma
- pragmas, intrinsic
ms.assetid: 25c86ac7-ef40-47b7-a2c0-fada9c5dc3c5
ms.openlocfilehash: 393a73fcf31c7c00b2057862792ff0536cc98ad8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62212381"
---
# <a name="intrinsic"></a>intrinsic

pragma의 인수 목록에 지정된 함수에 대한 호출을 내장 함수로 지정합니다.

## <a name="syntax"></a>구문

```cpp
#pragma intrinsic( function1 [, function2, ...] )
```

## <a name="remarks"></a>설명

합니다 **내장** pragma는 함수에 알려진 동작이 컴파일러 지시 합니다.  컴파일러는 함수를 호출할 수 있으며 성능을 개선할 수 있는 경우 함수 호출을 인라인 명령으로 바꾸지 않을 수 있습니다.

아래에 내장 형식의 라이브러리 함수가 나와 있습니다. 한 번을 **내장** pragma 표시 되 면, 지정 된 내장 함수를 포함 하는 첫 번째 함수 정의에 적용 됩니다. 효과의 모양에 또는 소스 파일의 끝에 계속를 `function` pragma 동일한 내장 함수를 지정 합니다. 합니다 **내장** pragma는 함수 정의 외부에 사용할 수-전역 수준입니다.

다음 함수는 내장 형식이 며, 내장 형식은 지정할 때 사용 됩니다 [/Oi](../build/reference/oi-generate-intrinsic-functions.md):

|||||
|-|-|-|-|
|[_disable](../intrinsics/disable.md)|[_outp](../c-runtime-library/outp-outpw-outpd.md)|[fabs](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|[strcmp](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)|
|[_enable](../intrinsics/enable.md)|[_outpw](../c-runtime-library/outp-outpw-outpd.md)|[labs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|[strcpy](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)|
|[_inp](../c-runtime-library/inp-inpw-inpd.md)|[_rotl](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|[memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)|[strlen](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|
|[_inpw](../c-runtime-library/inp-inpw-inpd.md)|[_rotr](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|[memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)||
|[_lrotl](../c-runtime-library/reference/lrotl-lrotr.md)|[_strset](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)|[memset](../c-runtime-library/reference/memset-wmemset.md)||
|[_lrotr](../c-runtime-library/reference/lrotl-lrotr.md)|[abs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|[strcat](../c-runtime-library/reference/strcat-wcscat-mbscat.md)||

내장 함수를 사용하는 프로그램은 함수 호출의 오버헤드가 없기 때문에 빠르게 실행되지만 추가 코드가 생성되므로 프로그램이 커질 수 있습니다.

**x86 특정**

합니다 `_disable` 고 `_enable` 내장 함수를 비활성화/활성화 인터럽트 커널 모드 명령을 생성 하 고 커널 모드 드라이버에서 유용할 수 있습니다.

### <a name="example"></a>예제

사용 하 여 명령줄에서 다음 코드를 컴파일합니다 `cl -c -FAs sample.c` 는 바뀌기 x86을 보려면 다음 CLI 및 STI 지침:

```cpp
// pragma_directive_intrinsic.cpp
// processor: x86
#include <dos.h>   // definitions for _disable, _enable
#pragma intrinsic(_disable)
#pragma intrinsic(_enable)
void f1(void) {
   _disable();
   // do some work here that should not be interrupted
   _enable();
}
int main() {
}
```

**X86 전용 종료**

아래에 나와 있는 부동 소수점 함수는 실제 내장 형식을 포함하지 않습니다. 대신 인수를 프로그램 스택으로 푸시하지 않고 부동 소수점 칩으로 직접 전달하는 버전이 있습니다.

|||||
|-|-|-|-|
|[acos](../c-runtime-library/reference/acos-acosf-acosl.md)|[cosh](../c-runtime-library/reference/cosh-coshf-coshl.md)|[pow](../c-runtime-library/reference/pow-powf-powl.md)|[tanh](../c-runtime-library/reference/tanh-tanhf-tanhl.md)|
|[asin](../c-runtime-library/reference/asin-asinf-asinl.md)|[fmod](../c-runtime-library/reference/fmod-fmodf.md)|[sinh](../c-runtime-library/reference/sinh-sinhf-sinhl.md)||

아래 나열 된 부동 소수점 함수를 지정 하는 경우 실제 내장 형식을 포함 [/Oi](../build/reference/oi-generate-intrinsic-functions.md)하십시오 [/Og](../build/reference/og-global-optimizations.md), 및 [/fp:fast](../build/reference/fp-specify-floating-point-behavior.md) (또는 /Og을 포함 하는 모든 옵션: [/ Ox](../build/reference/ox-full-optimization.md)하십시오 [/o1](../build/reference/o1-o2-minimize-size-maximize-speed.md), 및/o2):

|||||
|-|-|-|-|
|[atan](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[exp](../c-runtime-library/reference/exp-expf.md)|[log10](../c-runtime-library/reference/log-logf-log10-log10f.md)|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|
|[atan2](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[log](../c-runtime-library/reference/log-logf-log10-log10f.md)|[sin](../c-runtime-library/reference/sin-sinf-sinl.md)|[tan](../c-runtime-library/reference/tan-tanf-tanl.md)|
|[cos](../c-runtime-library/reference/cos-cosf-cosl.md)||||

사용할 수 있습니다 [/fp: strict](../build/reference/fp-specify-floating-point-behavior.md) 또는 [/Za](../build/reference/za-ze-disable-language-extensions.md) 실제 내장 부동 소수점 옵션 생성을 재정의할 수 있습니다. 이 경우에는 함수가 인수를 프로그램 스택으로 푸시하는 대신 부동 소수점 칩으로 직접 전달하는 라이브러리 루틴으로 생성됩니다.

참조 [#pragma 함수](../preprocessor/function-c-cpp.md) 정보 및 소스 텍스트 블록에 대 한 내장 함수에 대 한 활성화/비활성화 하는 방법의 예제입니다.

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)<br/>
[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)