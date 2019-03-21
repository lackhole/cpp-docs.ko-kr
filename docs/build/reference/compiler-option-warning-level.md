---
title: /w, / w0, / w1, / w2, / w3, / w4, / w1, / w2, / w3, / w4, /Wall, /wd, / we, /wo, /Wv, /WX (경고 수준)
ms.date: 01/31/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.DisableSpecificWarnings
- VC.Project.VCCLCompilerTool.WarningLevel
- VC.Project.VCCLWCECompilerTool.DisableSpecificWarnings
- VC.Project.VCCLCompilerTool.WarnAsError
- VC.Project.VCCLWCECompilerTool.WarnAsError
- /wx
- VC.Project.VCCLWCECompilerTool.WarningLevel
- /wall
- VC.Project.VCCLCompilerTool.TreatSpecificWarningsAsErrors
- /Wv
- /w0
- /w1
- /w2
- /w3
- /w4
- /wd
- /we
- /wo
helpviewer_keywords:
- /W1 compiler option [C++]
- w compiler option [C++]
- -wo compiler option [C++]
- Warning Level compiler option
- W1 compiler option [C++]
- -we compiler option [C++]
- /WX compiler option [C++]
- -wd compiler option [C++]
- WX compiler option [C++]
- wo compiler option [C++]
- Wall compiler option [C++]
- /w compiler option
- W2 compiler option [C++]
- -W2 compiler option [C++]
- wd compiler option [C++]
- /we compiler option [C++]
- we compiler option [C++]
- -W1 compiler option [C++]
- -W4 compiler option [C++]
- -Wall compiler option [C++]
- /Wall compiler option [C++]
- -W0 compiler option [C++]
- W0 compiler option [C++]
- -WX compiler option [C++]
- /wo compiler option [C++]
- W4 compiler option [C++]
- W3 compiler option [C++]
- /wd compiler option [C++]
- warnings, as errors compiler option
- /W3 compiler option [C++]
- /W0 compiler option [C++]
- /W4 compiler option [C++]
- -W3 compiler option [C++]
- -w compiler option [C++]
- /W2 compiler option [C++]
- /Wv compiler option [C++]
ms.openlocfilehash: 997a73541ab95a393bda4ebf5412c11f025b03a3
ms.sourcegitcommit: faa42c8a051e746d99dcebe70fd4bbaf3b023ace
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2019
ms.locfileid: "57820691"
---
# <a name="w-w0-w1-w2-w3-w4-w1-w2-w3-w4-wall-wd-we-wo-wv-wx-warning-level"></a>/w, / w0, / w1, / w2, / w3, / w4, / w1, / w2, / w3, / w4, /Wall, /wd, / we, /wo, /Wv, /WX (경고 수준)

컴파일러가 지정된 컴파일에 대해 경고를 생성하는 방법을 지정합니다.

## <a name="syntax"></a>구문

> **/w**
>  **/w0**
>  **/w1**
>  **/w2**
>  **/w3** 
>  **/W4**
>  **/wall**
>  **/Wv**\[**:**_버전 _] **/WX**
>  **/w1**_경고_
>  **/w2** _ 경고_
>  **/w3**_경고_
>  **/w4**_경고_ 
>  **/wd**_경고_
>  **/we**_경고_ 
>  **/wo**_경고_

## <a name="remarks"></a>설명

경고 옵션에는 컴파일러 경고를 표시 하 고 전체를 컴파일하기 위한 경고 동작을 지정합니다.

경고 옵션 및 관련된 인수는 다음 표에 설명 되어 있습니다.

|옵션|설명|
------------|-----------------|
|**/w**|모든 컴파일러 경고를 표시 하지 않습니다.|
|**/W0**<br /><br /> **/W1**<br /><br /> **/W2**<br /><br /> **/W3**<br /><br /> **/W4**|컴파일러에서 생성할 경고 수준을 지정 합니다. 올바른 경고 수준 0에서 4 까지입니다.<br />**/ W0** 모든 경고를 표시 하지 않습니다. 이 설정은 **/w**합니다.<br />**/ W1** 수준 1 (심각한) 경고를 표시 합니다. **/ W1** 명령줄 컴파일러에서 기본 설정입니다.<br />**/ W2** 수준 1 및 수준 2 (중요) 경고를 표시 합니다.<br />**/ W3** 수준 1, 수준 2 및 3 (프로덕션 품질) 경고 수준 표시 됩니다. **/ W3** IDE의 기본 설정입니다.<br />**/ W4** 표시 수준 1, 2, 수준 3 경고 수준 및 모든 수준 4 (정보) 경고를 기본적으로 해제 되지 않습니다. 사소한 경고를 제공 하려면이 옵션을 사용 하는 것이 좋습니다. 새 프로젝트를 사용 하 여 수 있습니다 **/w4** 모든 컴파일에서; 가장 적은 수 찾기 어려운 코드 오류 이렇게 하면 합니다.|
|**/Wall**|으로 표시 하는 모든 경고를 표시 **/w4** 와 다른 모든 경고는 **/w4** 포함 되지 않습니다-예를 들어, 기본적으로 해제 되어 있는 경고 합니다. 자세한 내용은 [컴파일러 경고 하는 Off By Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)합니다.|
|**/Wv**\[**:**_version_]|컴파일러 버전에 도입 된 경고만 표시 *버전* 및 이전 버전입니다. 최신 버전의 컴파일러에서로 마이그레이션하는 경우 코드에서 새 경고를 표시 하지 않으려면 및 수정 하는 동안 기존 빌드 프로세스를 유지 하기 위해이 옵션을 사용할 수 있습니다. 선택적 매개 변수 *버전* 형식을 취합니다 *nn*[. *mm*[. *bbbbb*]] 여기서 *nn* 는 주 버전 번호 이며 *mm* 선택적 부 버전 번호 및 *bbbbb* 는의 선택적 빌드 번호 컴파일러입니다. 사용 예를 들어 */Wv:17* Visual Studio 2012 (즉, 17의 주 버전 번호에는 컴파일러의 모든 버전) 또는 이전에 도입 된 경고를 표시 하지만 Visual Studio 2013 (주 버전에에서 도입 된 경고 표시 안 함 18) 이상. 기본적으로 **/Wv** 사용 하 여 현재 컴파일러 버전 번호 및 경고가 표시 되지 않습니다. 컴파일러 버전에 의해 표시 되지 경고에 대 한 내용은 [컴파일러 버전별 컴파일러 경고](../../error-messages/compiler-warnings/compiler-warnings-by-compiler-version.md)합니다.|
|**/WX**|모든 컴파일러 경고를 오류로 처리합니다. 새 프로젝트를 사용 하 여 수 있습니다 **/WX** 모든 컴파일에서; 가장 적은 수 찾기 어려운 코드 오류를 통해 모든 경고를 해결 합니다.<br /><br /> 링커에 **/WX** 옵션입니다. 자세한 내용은 [/WX(링커 경고를 오류로 처리)](wx-treat-linker-warnings-as-errors.md)를 참조하세요.|
|**/w1**_nnnn_<br /><br /> **/w2**_nnnn_<br /><br /> **/w3**_nnnn_<br /><br /> **/w4**_nnnn_|지정 된 경고 수에 대 한 경고 수준을 설정 _nnnn_합니다. 이 특정 경고 수준이 설정 된 경우 해당 경고에 대 한 컴파일러 동작을 변경할 수 있습니다. 기본 Visual Studio에서 제공 되는 것 보다는 경고에 대 한 고유한 코딩 표준 적용을 조합 하 여 다른 경고 옵션을 사용 하 여 이러한 옵션을 사용할 수 있습니다.<br /><br /> 예를 들어 **/w34326** 4326 수준 1 대신 수준 3 경고로 생성 되도록 합니다. 모두 사용 하 여 컴파일하는 경우는 **/w34326** 옵션 및 **/w2** 옵션을 경고 C4326 생성 되지 않습니다.|
|**/wd**_nnnn_|지정 된 컴파일러 경고를 억제 _nnnn_합니다.<br /><br /> 예를 들어 **/wd4326은** 컴파일러 C4326 경고를 표시 하지 않습니다.|
|**/we**_nnnn_|지정 된 컴파일러 경고 처리 _nnnn_ 오류로 발생 합니다.<br /><br /> 예를 들어 **/we4326** 경고 번호 C4326 컴파일러에서 오류로 처리 하도록 하면 됩니다.|
|**/wo**_nnnn_|보고서에서 지정 된 컴파일러 경고 _nnnn_ 한 번만 합니다.<br /><br /> 예를 들어 **/wo4326** 경고 C4326이 한 번만 보고 됩니다 원인 처음 발견 된 컴파일러에서.|

사용 하는 경우 경고 옵션 중 하나를 사용 하 여 미리 컴파일된 헤더를 만들면 합니다 [/Yc](yc-create-precompiled-header-file.md) 옵션을 사용 하 여 미리 컴파일된 헤더를 사용 합니다 [/Yu](yu-use-precompiled-header-file.md) 옵션을 적용 하려면 이러한 동일한 경고 옵션을 사용 하면 다시 실행 합니다. 명령줄에서 다른 경고 옵션을 사용 하 여 미리 컴파일된 헤더에 설정 된 경고 옵션을 재정의할 수 있습니다.

사용할 수는 [#pragma 경고](../../preprocessor/warning.md) 특정 소스 파일에서 컴파일 타임 지시문 즉 경고 수준을 제어할 수를 보고 합니다.

Warning pragma 지시문 소스 코드에 영향을 받지 않습니다.는 **/w** 옵션입니다.

합니다 [빌드 오류 설명서](../../error-messages/compiler-errors-1/c-cpp-build-errors.md) 경고 및 경고 수준을 설명 하 고 의도 한 대로 특정 문은 컴파일되지 않을 수 이유를 나타냅니다.

### <a name="to-set-the-compiler-options-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 컴파일러 옵션을 설정 하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 설정 하는 **/w0**, **/w1**, **/w2**, **/w3**를 **/w4**를 **/wall**m **/Wv**를 **/WX** 하거나 **/WX-** 옵션을 선택 합니다 **구성 속성** > **C / C + +** > **일반** 속성 페이지.

   - 설정 하는 **/w0**, **/w1**를 **/w2**, **/w3**를 **/w4**, 또는 **/wall** 옵션을 수정 합니다 **경고 수준** 속성입니다.

   - 설정 하는 **/WX** 또는 **/WX-** 옵션을 수정 합니다 **경고를 오류로 처리** 속성입니다.

   - 에 대 한 버전을 설정 하는 **/Wv** 옵션을 컴파일러 버전 번호를 입력 합니다 **경고 버전** 속성입니다.

1. 설정 하는 **/wd** 하거나 **/we** 옵션을 선택 합니다 **구성 속성** > **C/c + +**  >   **고급** 속성 페이지.

   - 설정 하는 **/wd** 옵션을 선택 합니다 **특정 경고 사용 안 함** 속성 드롭다운 컨트롤 및 선택한 **편집**합니다. 편집 상자에는 **특정 경고 사용 안 함** 대화 상자에서 경고 번호를 입력 합니다. 둘 이상의 경고를 입력 하려면 세미콜론을 사용 하 여 값을 구분 (**;**). 예를 들어 입력 C4001 및 C4010을 사용 하지 않으려면 **4001; 4010**합니다. 선택할 **확인** 변경 내용을 저장 하 고 반환 하는 **속성 페이지** 대화 합니다.

   - 설정 하는 **/we** 옵션을 선택 합니다 **특정 경고를 오류로 처리** 속성 드롭다운 컨트롤 및 선택한 **편집**합니다. 편집 상자에는 **특정 경고를 오류로 처리** 대화 상자에서 경고 번호를 입력 합니다. 둘 이상의 경고를 입력 하려면 세미콜론을 사용 하 여 값을 구분 (**;**). 예를 들어 오류로 C4001 및 C4010, 입력 **4001; 4010**합니다. 선택할 **확인** 변경 내용을 저장 하 고 반환 하는 **속성 페이지** 대화 합니다.

1. 설정 하는 **/wo** 옵션을 선택 합니다 **구성 속성** > **C/c + +** > **명령줄** 속성 페이지입니다. 컴파일러 옵션을 입력 합니다 **추가 옵션** 상자입니다.

1. **확인**을 선택하여 변경 내용을 저장합니다.

### <a name="to-set-the-compiler-option-programmatically"></a>프로그래밍 방식으로 컴파일러 옵션을 설정하려면

- 
  <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarningLevel%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarnAsError%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableSpecificWarnings%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하십시오.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
