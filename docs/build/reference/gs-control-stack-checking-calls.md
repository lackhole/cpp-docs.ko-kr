---
title: /Gs(스택 검사 호출 제어)
ms.date: 10/25/2018
f1_keywords:
- /GS
helpviewer_keywords:
- disabling stack probes
- GS compiler option [C++]
- /GS compiler option [C++]
- stack, stack probes
- stack probes
- -GS compiler option [C++]
- stack checking calls
ms.assetid: 40daed7c-f942-4085-b872-01e12b37729e
ms.openlocfilehash: e31b42c1d9422d44c5f106f40c4a60a38f23425b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62270850"
---
# <a name="gs-control-stack-checking-calls"></a>/Gs(스택 검사 호출 제어)

스택 프로브에 대 한 임계값을 제어합니다.

## <a name="syntax"></a>구문

> **/Gs**[*size*]

## <a name="arguments"></a>인수

*size*<br/>
(옵션) 스택 프로브가 초기화되기 전에 지역 변수가 차지할 수 있는 바이트 수 입니다. 사이의 공백이 있으면 안 **/Gs** 하 고 *크기*합니다.

## <a name="remarks"></a>설명

A *스택 프로브가* 시퀀스 컴파일러가 함수 호출의 시작 부분에 삽입 하는 코드입니다. 초기화되면 스택 프로브는 함수의 지역 변수를 저장하는 데 필요한 메모리 공간에 원활하게 도달합니다. 이렇게 하면 운영 체제를 투명 하 게 함수의 나머지를 실행 하기 전에 필요한 경우 추가 스택 메모리의 페이지입니다.

기본적으로 컴파일러에서는 함수에 스택 공간이 2페이지 이상 필요한 경우 스택 프로브를 초기화하는 코드를 생성합니다. 컴파일러 옵션과 같습니다 **/Gs4096** x86, x64, ARM, ARM64 플랫폼 및 합니다. 이 값은 응용 프로그램 및 Windows 메모리 관리자가 런타임 시 프로그램 스택으로 동적으로 커밋되는 메모리 양을 늘리도록 합니다.

> [!NOTE]
> 기본값인 **/Gs4096** 프로그램 스택이 런타임 시 올바르게 증가 하도록 Windows 용 응용 프로그램입니다. 변경해야 할 확실한 이유가 없는 경우에는 이 기본값을 변경하지 마세요.

가상 장치 드라이버와 같은 일부 프로그램에는 이러한 기본 스택 증가 메커니즘이 필요하지 않습니다. 이러한 경우 스택 프로브는 필요 하 고 컴파일러에서 생성 하는 설정 하 여 중지할 수 있습니다 *크기* 로컬 변수 저장소에 대 한 모든 함수에서 필요로 하는 보다 큰 값으로.

**/Gs0** 시작 스택 프로브를 지역 변수에 대 한 저장소를 필요로 하는 모든 함수 호출에 대 한 합니다. 이는 성능을 저하시킬 수 있습니다.

X64를 대상으로 하는 경우는 **/Gs** 옵션 없이 지정 된을 *크기* 인수를 것 같습니다 **/Gs0**합니다. 경우는 *크기* 인수는 1 ~ 9, 경고 D9014 내보내진 및 효과 지정 하는 것 같습니다 **/Gs0**합니다.

X86, ARM, ARM64 대상 및를 **/Gs** 없이 옵션을 *크기* 인수는 동일 **/Gs4096**. 경우는 *크기* 인수는 1 ~ 9, 경고 D9014 내보내진 및 효과 지정 하는 것 같습니다 **/Gs4096**합니다.

모든 대상에 대해를 *크기* 10 사이의 2147485647 인수가 지정된 된 값에서 임계값을 설정 합니다. A *크기* 2147485648 이상 원인 심각한 오류 C1049입니다.

사용 하 여 스택 프로브 또는 해제를 설정할 수 있습니다 합니다 [check_stack](../../preprocessor/check-stack.md) 지시문입니다. **/Gs** 하며 `check_stack` pragma는 표준 C 라이브러리 루틴에 영향을 주지 않으면 컴파일한 함수에만 영향을 줍니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++** > **명령줄** 속성 페이지를 선택합니다.

1. 입력 된 **/Gs** 컴파일러 옵션 및의 경우 선택적으로 크기 **추가 옵션**합니다. 선택 **확인** 하거나 **적용** 변경 내용을 저장 합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
