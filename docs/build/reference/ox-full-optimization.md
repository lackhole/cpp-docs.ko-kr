---
title: /Ox (대부분의 속도 최적화 사용)
ms.date: 10/18/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.ToolOptimization
- /Ox
- /Oxs
helpviewer_keywords:
- Ox compiler option [C++]
- fast code [C++]
- /Ox compiler option [C++]
- -Ox compiler option [C++]
ms.assetid: 3ad7c30b-c615-428c-b1d0-2e024f81c760
ms.openlocfilehash: e39905608087425fe5a445f4ef88434d73bb2ded
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320099"
---
# <a name="ox-enable-most-speed-optimizations"></a>/Ox (대부분의 속도 최적화 사용)

**/Ox** 컴파일러 옵션은 속도를 우선 시하는 최적화 조합입니다. 일부 버전의 Visual Studio IDE 및 컴파일러 도움말 메시지에서는 이를 *전체 최적화*라고 부르지만 **/Ox** 컴파일러 옵션은 **/O2**를 사용한 속도 최적화 옵션의 하위 집합만 가능합니다.

## <a name="syntax"></a>구문

> **/Ox**

## <a name="remarks"></a>설명

**/Ox** 컴파일러 옵션이 사용 하도록 설정 합니다 **/O** 컴파일러 옵션는 속도입니다. 합니다 **/Ox** 컴파일러 옵션이 추가 포함 되지 않습니다 [/GF (중복 문자열 제거)](gf-eliminate-duplicate-strings.md) 하 고 [/Gy (함수 수준 링크 사용)](gy-enable-function-level-linking.md) 로사용하도록설정하는옵션[/O1 또는/o2 (크기 최소화, 속도 최대화)](o1-o2-minimize-size-maximize-speed.md)합니다. 적용 하 여 추가 옵션 **/o1** 하 고 **/o2** 문자열 또는 디버깅에 영향을 줄 수 있는 대상 주소 및 엄격한 언어 규칙을 공유 하는 함수에 대 한 포인터를 발생할 수 있습니다. 합니다 **/Ox** 옵션은 포함 하지 않고 대부분의 최적화를 사용 하는 쉬운 방법을 **/GF** 하 고 **/Gy**합니다. 자세한 설명은 참조 하세요. 합니다 [/GF](gf-eliminate-duplicate-strings.md) 하 고 [/Gy](gy-enable-function-level-linking.md) 옵션입니다.

**/Ox** 컴파일러 옵션은 다음 옵션을 조합하여 사용하는 것과 같습니다.

- [/Ob (인라인 함수 확장)](ob-inline-function-expansion.md)option 매개 변수 2는 위치 ( **/ob2**)

- [/Og(전역 최적화)](og-global-optimizations.md)

- [/Oi(내장 함수 만들기)](oi-generate-intrinsic-functions.md)

- [/Ot (속도 우선 코드)](os-ot-favor-small-code-favor-fast-code.md)

- [/Oy (프레임 포인터 생략)](oy-frame-pointer-omission.md)

**/Ox** 다음과 상호 배타적입니다.

- [/O1(크기 최소화)](o1-o2-minimize-size-maximize-speed.md)

- [/O2(속도 최대화)](o1-o2-minimize-size-maximize-speed.md)

- [/Od(디버그 사용 안 함)](od-disable-debug.md)

**/Ox** 컴파일러 옵션을 [/Os(작은 코드 선호)](os-ot-favor-small-code-favor-fast-code.md)와 결합한 **/Oxs**를 지정하면 **/Ox** 컴파일러 옵션의 속도에 대한 치우침을 없앨 수 있습니다. 결합된 옵션은 더 작은 코드 크기를 선호합니다.  **/Oxs** 옵션은 **/Ox** **/Os**가 순서대로 나타날 때와 완전히 동일합니다.

릴리스 빌드에 대한 모든 사용 가능한 파일 수준 최적화를 적용하려면 **/Ox**대신 [/O2(속도 최대화)](o1-o2-minimize-size-maximize-speed.md)를, **/Oxs** 대신 [/O1(크기 최소화)](o1-o2-minimize-size-maximize-speed.md)를 지정하는것이 좋습니다. 릴리스에서 더 많은 최적화를 적용하려면 [/GL(전체 프로그램 최적화)](gl-whole-program-optimization.md) 컴파일러 옵션과 [/LTCG(링크 타임 코드 생성)](ltcg-link-time-code-generation.md) 링커 옵션을 고려합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 아래 **구성 속성**오픈 **C /C++**  를 선택한 후는 **최적화** 속성 페이지.

1. **최적화** 속성을 수정합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[/O 옵션(코드 최적화)](o-options-optimize-code.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
