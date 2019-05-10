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

전체 프로그램 최적화는 컴파일러가 정보를 사용하여 해당 프로그램의 모든 모듈에서 최적화를 수행할 수 있게 합니다. 전체 프로그램 최적화가 없으면 모듈(컴파일) 별로 수행됩니다.

전체 프로그램 최적화는 기본적으로 꺼져 있고 명시적으로 설정해야 합니다. 그러나 명시적으로 **/GL-** 을 사용하여 비활성화할 수도 있습니다.

모든 모듈에 대한 정보를 사용하여 컴파일러는 다음을 수행할 수 있습니다.

- 함수 경계를 넘어 레지스터의 사용을 최적화 합니다.

- 추적 전역 데이터를 로드 및 저장소 수를 줄일 수를 수정 하는 더 나은 작업을 수행 합니다.

- 추적 가능한 포인터에 의해 수정 된 항목 집합 역참조, 로드 및 저장소 수를 줄이면 더 나은 작업을 수행 합니다.

- 인라인 함수는 다른 모듈에 정의 된 경우에 모듈의 함수입니다.

**/GL**로 생성된 .obj 파일은 [EDITBIN](editbin-reference.md) 및 [DUMPBIN](dumpbin-reference.md) 같은 링커 유틸리티에서 사용할 수 없습니다.

**/GL** 및 [/c](c-compile-without-linking.md)를 사용하여 프로그램을 컴파일하는 경우 /LTCG 링커 옵션을 사용하여 출력 파일을 만들어야 합니다.

[/ZI](z7-zi-zi-debug-information-format.md) 와 함께 사용할 수 **/GL**

현재 버전에서 **/GL**로 생성된 파일 형식은 이후 버전의 Visual C++에서 읽을 수 없습니다. 현재 및 미래에 사용자가 사용할 것으로 예상되는 모든 버전의 Visual C++에 대한 .lib 파일의 복사본을 제공하려는 경우가 아니면 **/GL**로 생성된 .obj 파일로 구성된 .lib 파일을 제공하지 않아야 합니다.

.obj 파일에서 생성 된 **/GL** .lib 파일이 생성 되는 동일한 컴퓨터에 연결 하지 않는 한.lib 파일을 빌드하려면 미리 컴파일된 헤더 파일을 사용할 수 해야 합니다 **/GL** .obj 파일입니다. .Obj 파일의 미리 컴파일된 헤더 파일의 정보 링크 타임에 필요 합니다.

사용 가능한 최적화 및 전체 프로그램 최적화의 제한 사항에 대 한 자세한 내용은 참조 하세요. [/LTCG](ltcg-link-time-code-generation.md)합니다.  **/GL** 또한는 프로필 기반된 최적화를 사용할 수 있는 /LTCG을 참조 하십시오.  프로필 기반 최적화 및 함수에 프로필 기반 최적화에서 정렬 하려는 경우에 대 한를 컴파일할 때 컴파일하여 [/Gy](gy-enable-function-level-linking.md) 또는 컴파일러 옵션 /Gy를 암시 하는 합니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 참조 [/LTCG (링크 타임 코드 생성)](ltcg-link-time-code-generation.md) 지정 하는 방법에 대 한 내용은 **/GL** 개발 환경에서.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

1. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WholeProgramOptimization%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
