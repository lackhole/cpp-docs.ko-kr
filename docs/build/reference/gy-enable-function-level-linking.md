---
title: /Gy(함수 수준 링크 사용)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFunctionLevelLinking
- /gy
- VC.Project.VCCLWCECompilerTool.EnableFunctionLevelLinking
helpviewer_keywords:
- enable function-level linking compiler option [C++]
- COMDAT function
- Gy compiler option [C++]
- -Gy compiler option [C++]
- /Gy compiler option [C++]
- packaged functions
ms.assetid: 0d3cf14c-ed7d-4ad3-b4b6-104e56f61046
ms.openlocfilehash: 9643b8b4b4b26b3f7a8a59ed0085601b1a53094d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62270726"
---
# <a name="gy-enable-function-level-linking"></a>/Gy(함수 수준 링크 사용)

컴파일러가 개별 함수를 패키지된 함수(COMDAT)의 형태로 패키지할 수 있게 합니다.

## <a name="syntax"></a>구문

```
/Gy[-]
```

## <a name="remarks"></a>설명

링커에서는 함수를 COMDAT로 별도로 패키지화하여 DLL 또는 .exe 파일의 개별 함수를 제외하거나 순서를 지정해야합니다.

링커 옵션 [/OPT (최적화)](opt-optimizations.md)를 사용하여 .exe 파일에서 참조되지 않은 패키지에 포함된 함수를 제외할 수 있습니다.

링커 옵션 [/ORDER (순서대로 함수 넣기)](order-put-functions-in-order.md)를 사용하여 패키지된 함수를 .exe 파일에 지정된 순서로 포함할 수 있습니다.

인라인 함수는 호출으로 인스턴스화되는 경우 항상 패키지됩니다. (예를 들어, 인라인 off 되어 있거나 함수 주소를 사용하는 경우). 또한 C++ 클래스 선언에 정의된 멤버 함수는 자동으로 패키지 됩니다. 다른 함수는 그렇지 않으며 패키지 함수로 컴파일하기 위해 반드시 이 옵션을 선택해야 합니다.

> [!NOTE]
> 편집과 계속에 사용되는 [/ZI](z7-zi-zi-debug-information-format.md) 옵션은 자동으로 **/Gy** 옵션을 설정합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **C/C++** 폴더를 클릭합니다.

1. **코드 생성** 속성 페이지를 클릭합니다.

1. **함수 수준 링크 사용** 속성을 수정합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFunctionLevelLinking%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
