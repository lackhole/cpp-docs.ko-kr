---
title: /Oi(내장 함수 만들기)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableIntrinsicFunctions
- /oi
- VC.Project.VCCLWCECompilerTool.EnableIntrinsicFunctions
helpviewer_keywords:
- Oi compiler option [C++]
- intrinsic functions, generate
- /Oi compiler option [C++]
- -Oi compiler option [C++]
- generate intrinsic functions compiler option [C++]
ms.assetid: fa4a3bf6-0ed8-481b-91c0-add7636132b4
ms.openlocfilehash: f3afedade6f99129c21069e5117daa4ceb616cc2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320346"
---
# <a name="oi-generate-intrinsic-functions"></a>/Oi(내장 함수 만들기)

일부 함수 호출을 내장 함수나 특정 형태의 함수로 바꾸어 응용 프로그램을 더 빠르게 실행하도록 합니다.

## <a name="syntax"></a>구문

```
/Oi[-]
```

## <a name="remarks"></a>설명

내장 함수를 사용하는 프로그램은 함수 호출의 오버헤드가 없기 때문에 더 빠르지만 만들어진 추가 코드만큼 크기가 커질 수 있습니다.

내장 함수 형식을 가지고 있는 함수에 대한 자세한 내용은 [intrinsic](../../preprocessor/intrinsic.md)을 참조합니다.

**/Oi**는 일부 함수 호출을 내장 함수로 대체하라는 컴파일러에 대한 요청일 뿐입니다. 컴파일러는 더 좋은 성능을 얻기 위해 함수를 호출하고 함수 호출을 내장함수로 대체하지 않을 수 있습니다.

**x86 특정**

내장 부동 소수점 함수는 입력값에 대한 특수한 검사를 수행하지 않으므로 제한된 입력 범위에서 작동하고, 같은 이름을 가진 라이브러리 루틴과는 다른 예외 처리 및 경계 조건을 갖습니다. 진정한 내장형을 사용하면 IEEE 예외 처리가 손실되고 `_matherr` 및 `errno` 기능이 손실될 수 있습니다. 후자는 ANSI 규칙의 손실을 의미합니다. 그러나 내장 형식은 부동 소수점 집약적인 프로그램을 상당히 빠르게 할 수 있으며, 많은 프로그램에서 적합성 문제는 실용적인 가치가 거의 없습니다.

[Za](za-ze-disable-language-extensions.md) 컴파일러 옵션을 사용하여 실제 내장 부동 소수점 옵션 생성을 무시할 수 있습니다. 이 경우에는 함수가 인수를 프로그램 스택으로 푸시하는 대신 부동 소수점 칩으로 직접 전달하는 라이브러리 루틴으로 생성됩니다.

**END x86 특정**

[intrinsic](../../preprocessor/intrinsic.md)을 사용하여 내장 함수를 만들거나 [함수(C/C++)](../../preprocessor/function-c-cpp.md)를 사용하여 함수 호출을 명시적으로 수행할 수 있습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **C/C++** 폴더를 클릭합니다.

1. **최적화** 속성 페이지를 클릭합니다.

1. **내장 함수를 사용하도록 설정** 속성을 수정합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableIntrinsicFunctions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[/O 옵션(코드 최적화)](o-options-optimize-code.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[컴파일러 내장 함수](../../intrinsics/compiler-intrinsics.md)
