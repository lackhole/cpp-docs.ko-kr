---
title: /GL(전체 프로그램 최적화)
ms.date: 11/04/2016
f1_keywords:
- /gl
- VC.Project.VCCLWCECompilerTool.WholeProgramOptimization
helpviewer_keywords:
- /GL compiler option [C++]
- whole program optimizations and C++ compiler
- -GL compiler option [C++]
- GL compiler option [C++]
ms.assetid: 09d51e2d-9728-4bd0-b5dc-3b8284aca1d1
ms.openlocfilehash: 6251209dac74a504bb0635f0c544c39935090a42
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62292135"
---
# <a name="gl-whole-program-optimization"></a>/GL(전체 프로그램 최적화)

전체 프로그램 최적화를 사용합니다.

## <a name="syntax"></a>구문

```
/GL[-]
```

## <a name="remarks"></a>설명

전체 프로그램 최적화는 컴파일러가 프로그램 내의 모든 모듈에 대한 정보를 사용하여 최적화를 수행할 수 있게 합니다. 전체 프로그램 최적화가 없으면 모듈(컴파일 대상)별로 수행됩니다.

전체 프로그램 최적화는 기본적으로 꺼져 있고 명시적으로 설정해야 합니다. 그러나 명시적으로 **/GL-**를 사용하여 비활성화할 수도 있습니다.

모든 모듈 정보를 사용하여 컴파일러는 다음을 수행할 수 있습니다.

- 함수 경계를 넘어 레지스터의 사용을 최적화 합니다.

- 전역 데이터에 대한 수정 내용을 추적하여 로드 및 저장 횟수를 줄여 더 효율적으로 작업을 수행합니다.

- 포인터 역 참조로 수정된 가능한 항목 집합을 추적하여 로드 및 저장 횟수를 줄여 더 효율적으로 작업을 수행합니다.

- 함수가 다른 모듈에 정의된 경우에도 모듈의 함수를 인라인합니다.

**/GL**로 생성된 .obj 파일은 [EDITBIN](editbin-reference.md) 및 [DUMPBIN](dumpbin-reference.md) 같은 링커 유틸리티에서 사용할 수 없습니다.

**/GL** 및 [/c](c-compile-without-linking.md)를 사용하여 프로그램을 컴파일하는 경우 /LTCG 링커 옵션을 사용하여 출력 파일을 만들어야 합니다.

[/ZI](z7-zi-zi-debug-information-format.md)는 **/GL**과 함께 사용할 수 없습니다.

현재 버전에서 **/GL**로 생성된 파일 형식은 이후 버전의 Visual C++에서 읽을 수 없습니다. 현재 및 미래에 사용자가 사용할 것으로 예상되는 모든 버전의 Visual C++에 대한 .lib 파일의 복사본을 제공하려는 경우가 아니면 **/GL**로 생성된 .obj 파일로 구성된 .lib 파일을 제공하지 않아야 합니다.

**/GL**로 생성된 .obj 파일과 미리 컴파일된 헤더 파일은 .lib 파일이 **/GL** .obj 파일을 생성한 동일한 컴퓨터에 연결되지 않으면 .lib 파일을 작성하는데 사용하지 않아야 합니다. .obj 파일의 미리 컴파일된 헤더 파일의 정보는 링크할 때 필요합니다.

사용 가능한 최적화 및 전체 프로그램 최적화의 제한 사항에 대한 자세한 내용은 [/LTCG](ltcg-link-time-code-generation.md)를 참조합니다. 또한 **/GL**은 프로필로 가이드되는 최적화를 사용할 수 있게 합니다. /LTCG를 참조합니다. 프로필로 가이드되는 최적화를 반영한 컴파일 시 프로필로 가이드되는 최적화로부터 함수 순서를 지정하려면 [/Gy](gy-enable-function-level-linking.md) 또는 컴파일러 옵션 /Gy를 암시하는 컴파일을 해야 합니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. **/GL**을 개발 환경에서 지정하는 방법은 [/LTCG(링크 타임 코드 생성)](ltcg-link-time-code-generation.md)을 참조하세요.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

1. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WholeProgramOptimization%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
