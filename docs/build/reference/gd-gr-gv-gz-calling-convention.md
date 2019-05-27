---
title: /Gd, /Gr, /Gv, /Gz(호출 규칙)
ms.date: 09/05/2018
f1_keywords:
- /gr
- /Gv
- /gz
- /Gd
- VC.Project.VCCLCompilerTool.CallingConvention
helpviewer_keywords:
- -Gd compiler option [C++]
- -Gv compiler option [C++]
- /Gv compiler option [C++]
- -Gr compiler option [C++]
- Gd compiler option [C++]
- Gr compiler option [C++]
- /Gz compiler option [C++]
- -Gz compiler option [C++]
- /Gd compiler option [C++]
- Gz compiler option [C++]
- Gv compiler option [C++]
- /Gr compiler option [C++]
ms.assetid: fd3110cb-2d77-49f2-99cf-a03f9ead00a3
ms.openlocfilehash: 4e3da750b174fa92e28c1d0d5a8cbc035738ee51
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837286"
---
# <a name="gd-gr-gv-gz-calling-convention"></a>/Gd, /Gr, /Gv, /Gz(호출 규칙)

이러한 옵션은 함수 인수가 스택으로 푸시되는 순서, 호출이 끝나면 호출자 함수 또는 호출된 함수가 스택에서 인수를 제거하는지 여부, 컴파일러가 개별 함수를 식별하는 데 사용하는 이름 데코레이팅 규칙을 결정합니다.

## <a name="syntax"></a>구문

> **/Gd**<br/>
> **/Gr**<br/>
> **/Gv**<br/>
> **/Gz**<br/>

## <a name="remarks"></a>주의

기본 설정은 **/Gd**는 C++ 멤버 함수와 [__stdcall](../../cpp/stdcall.md), [__fastcall](../../cpp/fastcall.md) 또는 [__vectorcall](../../cpp/vectorcall.md)로 표시되는 함수를 제외한 모든 함수의 [__cdecl](../../cpp/cdecl.md) 호출 규칙을 지정합니다.

**/Gr**은 C++ 멤버 함수, `main` 함수 그리고 `__cdecl`, `__stdcall` 또는 `__vectorcall`로 표시되는 함수를 제외한 모든 함수의 `__fastcall` 호출 규칙을 지정합니다. 모든 `__fastcall` 함수는 프로토타입이 있어야 합니다. 이 호출 규칙은 x86을 대상으로 하는 컴파일러에서만 사용할 수 있으며, 다른 아키텍처를 대상으로 하는 컴파일러에서는 무시됩니다.

**/Gz**는 C++ 멤버 함수, `main` 함수 그리고 `__cdecl`, `__fastcall` 또는 `__vectorcall`로 표시되는 함수를 제외한 모든 함수의 `__stdcall` 호출 규칙을 지정합니다. 모든 `__stdcall` 함수는 프로토타입이 있어야 합니다. 이 호출 규칙은 x86을 대상으로 하는 컴파일러에서만 사용할 수 있으며, 다른 아키텍처를 대상으로 하는 컴파일러에서는 무시됩니다.

**/Gv**는 C++ 멤버 함수, main 함수, `vararg` 가변 인수 목록이 있는 함수 또는 충돌하는 `__cdecl`, `__stdcall` 또는 `__fastcall` 특성으로 표시되는 함수를 제외한 모든 함수의 `__vectorcall` 호출 규칙을 지정합니다. 이 호출 규칙은 /arch:SSE2 이상을 지원하는 x86 및 x64 아키텍처에서만 사용할 수 있으며, ARM 아키텍처를 대상으로 하는 컴파일러에서는 무시됩니다.

가변 인수 개수를 사용하는 함수는 `__cdecl`로 표시해야 합니다.

**/Gd**, **/Gr**, **/Gv** 및 **/Gz**는 [/clr:safe](clr-common-language-runtime-compilation.md) 또는 **/clr:pure**와 호환되지 않습니다. **/clr:pure** 및 **/clr:safe** 컴파일러 옵션은 Visual Studio 2015에서는 더 이상 사용되지 않으며 Visual Studio 2017 이상에서는 지원되지 않습니다.

> [!NOTE]
> 기본적으로 x86 프로세서의 경우 C++ 멤버 함수는 [__thiscall](../../cpp/thiscall.md)을 사용합니다.

모든 프로세서의 경우 명시적으로 `__cdecl`, `__fastcall`, `__vectorcall` 또는 `__stdcall`로 표시되는 멤버 함수는 해당 아키텍처에서 무시되지 않으면 지정된 호출 규칙을 사용합니다. 가변 인수 개수를 사용하는 멤버 함수는 항상 `__cdecl` 호출 규칙을 사용합니다.

이러한 컴파일러 옵션은 C++ 메서드 및 함수의 이름 데코레이션에 영향을 주지 않습니다. `extern "C"`로 선언되지 않는 이상, C++ 메서드 및 함수는 다른 이름 데코레이션 체계를 사용합니다. 자세한 내용은 [데코레이팅된 이름](decorated-names.md)을 참조하세요.

호출 규칙에 대한 자세한 내용은 [호출 규칙](../../cpp/calling-conventions.md)을 참조하세요.

## <a name="cdecl-specifics"></a>__cdecl 특성

x86 프로세서에서는 모든 함수 인수가 스택에 오른쪽에서 왼쪽으로 전달됩니다. ARM 및 x64 아키텍처에서는 일부 인수가 레지스터를 통해 전달되고 나머지는 스택에 오른쪽에서 왼쪽으로 전달됩니다. 호출 루틴은 스택에서 인수를 꺼냅니다.

C의 경우 `__cdecl` 명명 규칙은 앞에 밑줄(`_`)을 붙이는 함수 이름을 사용하며, 대/소문자 변환은 수행되지 않습니다. `extern "C"`로 선언되지 않는 이상, C++ 함수는 다른 이름 데코레이션 체계를 사용합니다. 자세한 내용은 [데코레이팅된 이름](decorated-names.md)을 참조하세요.

## <a name="fastcall-specifics"></a>__fastcall 특성

`__fastcall` 함수의 일부 인수는 레지스터에 전달되고(x86 프로세서의 경우 ECX 및 EDX), 나머지는 오른쪽에서 왼쪽으로 스택에 푸시됩니다. 호출 루틴은 스택에서 이러한 인수를 꺼낸 후 반환합니다. 일반적으로 **/Gr**은 실행 시간을 줄입니다.

> [!NOTE]
> 인라인 어셈블리 언어로 작성된 함수에 `__fastcall` 호출 규칙을 사용할 때 주의를 기울여야 합니다. 레지스터를 사용하면 컴파일러 사용과 충돌할 수 있습니다.

C의 경우 `__fastcall` 명명 규칙은 앞에 at 기호( **\@** )를 붙이고 그 뒤에 함수의 인수 크기를 바이트 단위로 표시하는 함수 이름을 사용합니다. 대/소문자 변환은 수행되지 않습니다. 컴파일러는 이 템플릿을 명명 규칙에 사용합니다.

`@function_name@number`

`__fastcall` 명명 규칙을 사용할 때 표준 포함 파일을 사용하세요. 그렇지 않으면 외부 참조를 확인할 수 없게 됩니다.

## <a name="stdcall-specifics"></a>__stdcall 특성

`__stdcall` 함수의 인수는 오른쪽에서 왼쪽으로 스택에 푸시되며, 호출된 함수는 스택에서 이러한 함수를 꺼낸 후 반환합니다.

C의 경우 `__stdcall` 명명 규칙은 앞에 밑줄( **\_** )을 붙이고 그 뒤에 at 기호( **\@** )와 함수의 인수 크기를 바이트 단위로 표시하는 함수 이름을 사용합니다. 대/소문자 변환은 수행되지 않습니다. 컴파일러는 이 템플릿을 명명 규칙에 사용합니다.

`_functionname@number`

## <a name="vectorcall-specifics"></a>__vectorcall 특성

`__vectorcall` 함수의 정수 인수는 최대 2개(x86) 또는 4개(x64)의 정수 레지스터와 최대 6개의 부동 소수점 및 벡터 값에 대한 XMM 레지스터를 사용하여 값으로 전달되고, 나머지는 오른쪽에서 왼쪽으로 스택에 전달됩니다. 호출된 함수는 스택을 정리한 후 반환합니다. 벡터 및 부동 소수점 반환 값은 XMM0에 반환됩니다.

C의 경우 `__vectorcall` 명명 규칙은 앞에 at 기호 2개( **\@\@** )를 붙이고 그 뒤에 함수의 인수 크기를 바이트 단위로 표시하는 함수 이름을 사용합니다. 대/소문자 변환은 수행되지 않습니다. 컴파일러는 이 템플릿을 명명 규칙에 사용합니다.

`functionname@@number`

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조하세요.

1. **C/C++** > **고급** 속성 페이지를 클릭합니다.

1. **호출 규칙** 속성을 수정합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CallingConvention%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

- [MSVC 컴파일러 옵션](compiler-options.md)
- [MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
