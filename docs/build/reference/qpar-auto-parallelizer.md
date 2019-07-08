---
title: /Qpar(자동 병렬화 도우미)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableParallelCodeGeneration
ms.assetid: 33ecf49d-c0d5-4f34-bce3-84ff03f38918
ms.openlocfilehash: c1ddea73c5aa8d3e7e70b45834cb04154bf3b4bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319228"
---
# <a name="qpar-auto-parallelizer"></a>/Qpar(자동 병렬화 도우미)

자동으로 코드에서 루프를 병렬화하는 컴파일러의 [자동 병렬화](../../parallel/auto-parallelization-and-auto-vectorization.md) 기능을 사용하도록 설정합니다.

## <a name="syntax"></a>구문

```
/Qpar
```

## <a name="remarks"></a>설명

컴파일러가 코드에서 루프를 자동으로 병렬화하면 계산이 여러 프로세서 코어로 분산됩니다. 컴파일러에서 병렬화가 적절하고 병렬화를 통해 성능이 향상될 것으로 확인되는 경우에만 루프가 병렬화됩니다.

`#pragma loop()` 지시문을 사용하여 최적화 프로그램이 특정 루프를 병렬화하도록 할 수 있습니다. 자세한 내용은 [루프](../../preprocessor/loop.md)를 참조합니다.

자동 병렬화기에 대한 출력 메시지에 대한 활성화 방법은 [/Qpar-report(자동 병렬화기 도우미 보고 수준)](qpar-report-auto-parallelizer-reporting-level.md)을 참조합니다.

### <a name="to-set-the-qpar-compiler-option-in-visual-studio"></a>Visual Studio에서 /Qpar 컴파일러 옵션을 설정하려면

1. **솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **속성**을 선택합니다.

1. 에 **속성 페이지** 대화 상자의 **C /C++** 선택 **명령줄**.

1. **추가 옵션** 대화 상자에 `/Qpar`을 입력합니다.

### <a name="to-set-the-qpar-compiler-option-programmatically"></a>프로그래밍 방식으로 /Qpar 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>에 있는 코드 예제를 사용합니다.

## <a name="see-also"></a>참고자료

[/Q 옵션(하위 수준 작업)](q-options-low-level-operations.md)<br/>
[/Qpar-report(자동 평행화 도우미 보고 수준)](qpar-report-auto-parallelizer-reporting-level.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[#pragma loop()](../../preprocessor/loop.md)<br/>
[네이티브 코드의 병렬 프로그래밍](https://blogs.msdn.microsoft.com/nativeconcurrency/2012/04/12/auto-vectorizer-in-visual-studio-2012-overview/)
