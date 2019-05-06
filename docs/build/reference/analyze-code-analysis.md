---
title: /analyze(코드 분석)
ms.date: 04/26/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.EnablePREfast
- /analyze
- VC.Project.VCCLCompilerTool.PREfastAdditionalOptions
- VC.Project.VCCLCompilerTool.PREfastAdditionalPlugins
helpviewer_keywords:
- /analyze compiler option [C++]
- -analyze compiler option [C++]
- analyze compiler option [C++]
ms.assetid: 81da536a-e030-4bd4-be18-383927597d08
ms.openlocfilehash: 63cfd2bd206a361301c75110a684e1d2c642a1f2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273159"
---
# <a name="analyze-code-analysis"></a>/analyze(코드 분석)

코드 분석 및 제어 옵션을 사용합니다.

## <a name="syntax"></a>구문

```cmd
/analyze[-][:WX-][:log filename][:quiet][:stacksize number][:max_paths number][:only][:ruleset]
```

## <a name="arguments"></a>인수

/analyze 기본 모드에서 분석을 시작합니다. 분석 출력은 다른 오류 메시지와 마찬가지로 **출력** 창에 나타납니다. 분석을 명시적으로 끄려면 **/analyze-** 를 사용하세요.

/analyze: WX- **/analyze: WX-** 지정은 **/ WX**를 사용하여 컴파일할 때 코드 분석 경고가 오류로 처리되지 않음을 의미합니다. 자세한 내용은 [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX(경고 수준)](compiler-option-warning-level.md)를 참조하세요.

/analyze: log `filename` 자세한 분석기 결과 지정 된 파일에 XML로 작성 된 `filename`합니다.

/analyze: 분석기 출력을 해제 Turns quiet 합니다 **출력** 창입니다.

/analyze: stacksize `number`  이 옵션과 함께 사용되는 `number` 매개 변수는 경고 [C6262](/visualstudio/code-quality/c6262)가 생성되는 스택 프레임의 크기(바이트)를 지정합니다. 이 매개 변수를 지정하지 않으면 스택 프레임 크기는 기본적으로 16KB입니다.

/analyze: max_paths `number` 이 옵션과 함께 사용되는 `number` 매개 변수는 분석할 코드 경로의 최대 수를 지정합니다. 이 매개 변수가 지정되지 않은 경우 숫자는 기본적으로 256입니다. 값이 클수록 더욱 철저한 검사를 수행하지만 분석 시간이 길어질 수 있습니다.

/analyze: 컴파일러가 코드를 생성 하 고 추가 구문 분석기를 실행 한 후 검사는 일반적으로 합니다. 합니다 **/analyze:만** 옵션은이 코드 생성 통과 해제 하지만 이렇게 하면 분석이 빨라지지만 컴파일러의 코드 생성 통과 하 여 검색 된는 컴파일 오류 및 경고를 내보냅니다. 프로그램에 코드 생성 오류가 있는 경우 분석 결과가 안정적이지 않을 수 있습니다. 따라서 코드가 이미 오류 없이 코드 생성 구문 검사를 통과하는 경우에만 이 옵션을 사용하는 것이 좋습니다.

/analyze: ruleset `<file_path>.ruleset` 에서는 직접 만들 수 있습니다 하는 사용자 지정 규칙 집합을 포함 하 여를 분석 하는 규칙 집합을 지정할 수 있습니다. 이 스위치를 설정 하면 규칙 엔진의 지정 된 규칙 집합 실행 하기 전에 아닌 멤버를 제외 하기 때문에 더 효율적입니다. 스위치를 설정 하지 않은 경우 엔진은 모든 규칙을 확인 합니다.

Visual Studio와 함께 제공 되는 규칙 집합에 포함 됩니다 **%VSINSTALLDIR%\Team Tools\Static Analysis Tools\Rule 집합입니다.**

다음 샘플 사용자 지정 규칙 집합 C6001 및 C26494 확인 하는 규칙 엔진을 알려 줍니다. 어디서 나으로이 파일을 추가할 수는 `.ruleset` 확장 하는 인수에 전체 경로 제공 합니다.

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description=" " ToolsVersion="15.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```

/analyze: 플러그 인 부분에서는 코드 분석 실행 될 때 지정 된 PREfast 플러그 인을 사용 하도록 설정 합니다.
LocalEspC.dll 범위의 C261XX 경고에서 동시성 관련 코드 분석을 구현 하는 플러그 인 검사입니다. 예를 들어 [C26100](/visualstudio/code-quality/c26100)하십시오 [C26101](/visualstudio/code-quality/c26101),..., [C26167](/visualstudio/code-quality/c26167)합니다.

LocalEspC.dll을 실행하려면 다음 컴파일러 옵션을 사용합니다: **/analyze:plugin LocalEspC.dll**

CppCoreCheck.dll를 실행 하려면 먼저 개발자 명령 프롬프트에서이 명령을 실행 합니다.

```cmd
set Esp.Extensions=CppCoreCheck.dll
```

그런 다음 다음 컴파일러 옵션을 사용합니다: **/analyze:plugin EspXEngine.dll**

## <a name="remarks"></a>설명

자세한 내용은 [C/C++ 개요에 대한 코드 분석](/visualstudio/code-quality/code-analysis-for-c-cpp-overview)과 [C/C++ 경고에 대한 코드 분석](/visualstudio/code-quality/code-analysis-for-c-cpp-warnings)을 참조합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** 노드를 확장합니다.

1. 확장 된 **코드 분석** 노드.

1. **일반** 속성 페이지를 클릭합니다.

1. 하나 또는 두 개를 수정 합니다 **코드 분석** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

1. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

- [MSVC 컴파일러 옵션](compiler-options.md)
- [MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
