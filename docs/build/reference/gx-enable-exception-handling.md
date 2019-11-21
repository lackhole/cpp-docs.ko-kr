---
title: /GX(예외 처리 사용)
ms.date: 11/19/2019
f1_keywords:
- /gx
helpviewer_keywords:
- exception handling, enabling
- /GX compiler option [C++]
- -GX compiler option [C++]
- cl.exe compiler, exception handling
- enable exception handling compiler option [C++]
- GX compiler option [C++]
ms.assetid: 933b43ba-de77-4ff8-a48b-7074de90bc1c
ms.openlocfilehash: 171ff0d0dfb1dec41bae5f6be63c941802c402a4
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245084"
---
# <a name="gx-enable-exception-handling"></a>/GX(예외 처리 사용)

더 이상 사용되지 않습니다. Enables synchronous exception handling using the assumption that functions declared by using `extern "C"` never throw an exception.

## <a name="syntax"></a>구문

```
/GX
```

## <a name="remarks"></a>주의

**/GX** is deprecated. Use the equivalent [/EHsc](eh-exception-handling-model.md) option instead. For a list of deprecated compiler options, see the **Deprecated and Removed Compiler Options** section in [Compiler Options Listed by Category](compiler-options-listed-by-category.md).

By default, **/EHsc**, the equivalent of **/GX**, is in effect when you compile by using the Visual Studio development environment. When using the command line tools, no exception handling is specified. This is the equivalent of **/GX-** .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. In the navigation pane, choose **Configuration Properties**, **C/C++** , **Command Line**.

1. **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하세요.

## <a name="see-also"></a>참조

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[/EH(예외 처리 모델)](eh-exception-handling-model.md)
