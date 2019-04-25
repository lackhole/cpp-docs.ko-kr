---
title: /LN(MSIL 모듈 만들기)
ms.date: 11/04/2016
f1_keywords:
- /LN
helpviewer_keywords:
- -LN compiler option [C++]
- /LN compiler option [C++]
ms.assetid: 4f38f4f4-3176-4caf-8200-5c7585dc1ed3
ms.openlocfilehash: 18b0e72d50f328afc1f2856f833cec1aa7d46f30
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62176218"
---
# <a name="ln-create-msil-module"></a>/LN(MSIL 모듈 만들기)

어셈블리 매니페스트를 출력 파일에 삽입하지 않도록 지정합니다.

## <a name="syntax"></a>구문

```
/LN
```

## <a name="remarks"></a>설명

기본적으로 **/LN** (어셈블리 매니페스트가 출력 파일에 삽입 됩니다.)는 적용 되지 않습니다.

때 **/LN** 를 사용 중 하나는 [/clr (공용 언어 런타임 컴파일)](clr-common-language-runtime-compilation.md) 옵션 사용 해야 합니다.

매니페스트에 어셈블리 메타 데이터가 없는 관리 되는 프로그램 모듈을 이라고 합니다. 로 컴파일하는 경우 [(컴파일 없이 링크 사용)는 /c](c-compile-without-linking.md) 및 **/LN**를 지정 [/NOASSEMBLY (MSIL 모듈 만들기)](noassembly-create-a-msil-module.md) 링커 단계 출력 파일을 만듭니다.

어셈블리를 작성 하는 구성 요소 기반 접근 방식을 사용 하려는 경우 모듈을 만들 수도 있습니다.  즉, 형식을 작성 하 고 모듈을 컴파일할 수 있습니다.  그런 다음 하나 이상의 모듈에서 어셈블리를 생성할 수 있습니다.  모듈에서 어셈블리를 만드는 방법에 대 한 자세한 내용은 참조 하세요. [링커 입력으로.netmodule 파일](netmodule-files-as-linker-input.md) 하거나 [Al.exe (어셈블리 링커)](/dotnet/framework/tools/al-exe-assembly-linker)합니다.

모듈의 기본 파일 확장명은 .netmodule입니다.

시각적 개체의 C++ Visual 이전의 릴리스 C++ 2005 모듈을 사용 하 여 만든 **/clr:noAssembly**합니다.

MSVC 링커는.netmodule 파일 입력을 및 어셈블리 또는.netmodule를 링커에 입력 된.netmodules에 런타임에 종속 되지 않음 출력 파일을 링커에 의해 생성 됩니다.  자세한 내용은 [링커 입력 파일로 사용하는 .netmodule 파일](netmodule-files-as-linker-input.md)을 참조하세요.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

- 지정할 [/NOASSEMBLY (MSIL 모듈 만들기)](noassembly-create-a-msil-module.md) 링커 단계 출력 파일을 만듭니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- 이 컴파일러 옵션을 프로그래밍 방식으로 변경할 수 없습니다.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
