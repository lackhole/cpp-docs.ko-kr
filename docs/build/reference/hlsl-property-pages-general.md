---
title: 'HLSL 속성 페이지: 일반'
ms.date: 11/04/2016
f1_keywords:
- VC.Project.FXCompilerTool.ShaderModel
- VC.Project.FXCompilerTool.PreprocessorDefinitions
- VC.Project.FXCompilerTool.ShaderType
- VC.Project.FXCompilerTool.EnableDebuggingInformation
- VC.Project.FXCompilerTool.AdditionalIncludeDirectories
- VC.Project.FXCompilerTool.DisableOptimizations
- VC.Project.FXCompilerTool.EntryPointName
ms.assetid: 0e02f2a6-f123-43da-b04b-a0719a7c2b03
ms.openlocfilehash: 0fce8a3b2a43cf05024a028a9e3325a929922abb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291472"
---
# <a name="hlsl-property-pages-general"></a>HLSL 속성 페이지: 일반

HLSL 컴파일러(fxc.exe)의 다음 속성을 구성하려면 해당 **일반** 속성 페이지를 사용합니다. 액세스 하는 방법에 대 한 자세한 합니다 **일반적인** HLSL 폴더 속성 페이지를에서 참조 하세요 [설정 C++ Visual Studio에서 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

## <a name="uielement-list"></a>UI 요소 목록

- **추가 포함 디렉터리**

   포함 경로에 하나 이상의 디렉터리를 추가합니다. 디렉터리 구분하려면 세미콜론을 사용합니다.

이 속성은 **/I[path]** 명령줄 인수에 해당합니다.

- **진입점 이름**

   셰이더에 대한 진입점을 지정합니다. 기본적으로 이 값은 **main**입니다.

이 속성은 **/E[name]** 명령줄 인수에 해당합니다.

- **최적화 비활성화**

   최적화를 사용하지 않도록 설정하려면 **예(/Od)** 이고, 사용하도록 설정하려면 **아니요**입니다. 기본적으로 **디버그** 구성에 대한 값은 **예(/Od)** 이고 **릴리스** 구성에 대한 값은 **아니요**입니다.

HLSL 컴파일러에 대한 **/Od** 명령줄 인수가 암시적으로 **/Gfp** 명령줄 인수에 적용되지만 출력은 **/Od** 및 **/Gfp** 명령줄 인수 둘 다 명시적으로 전달하여 생성된 출력과 동일하지 않을 수 있습니다.

- **디버깅 정보 사용**

   디버깅 정보를 사용하도록 설정 하려면 **예(/Zi)** 이고 사용하지 않도록 설정하려면 **아니요**입니다. 기본적으로 **디버그** 구성에 대한 값은 **예(/Zi)** 이고 **릴리스** 구성에 대한 값은 **아니요**입니다.

- **셰이더 형식**

   셰이더 종류를 지정합니다. 다양한 종류의 셰이더는 그래픽 파이프라인의 다른 파트를 구현합니다. 특정 종류의 셰이더는 **Shader Model** 속성에서 지정하는 최신 셰이더 모델에서만 사용할 수 있습니다(예: 셰이더 모델 5에 컴퓨팅 셰이더가 도입됐습니다).

   이 속성은 HLSL 컴파일러에 대한 **/T \[type]_\[model]** 명령줄 인수의 **\[type]** 부분에 해당합니다. **셰이더 모델** 속성은 인수의 **[model]** 부분을 지정합니다.

- **셰이더 모델**

   셰이더 모델을 지정합니다. 다양한 셰이더 모델은 기능이 다양합니다. 일반적으로 최신 셰이더 모델은 기능을 확장했지만 셰이더 코드를 실행하려면 최신 그래픽 하드웨어를 필요로 합니다. **셰이더 형식** 속성에서 지정하는 특정 종류의 셰이더는 최신 셰이더 모델에서만 사용할 수 있습니다(예: 셰이더 모델 5에 계산 셰이더가 도입됐습니다).

   이 속성은 HLSL 컴파일러에 대한 **/T \[type]_\[model]** 명령줄 인수의 **\[model]** 부분에 해당합니다. **셰이더 형식** 속성은 인수의 **[type]** 부분을 지정합니다.

- **전처리기 정의**

   HLSL 소스 코드 파일에 적용할 하나 이상의 전처리기 기호 정의를 추가합니다. 기호 정의를 구분하려면 세미콜론을 사용합니다.

   이 속성은 HLSL 컴파일러에 대한 **/D \[definitions]** 명령줄 인수에 해당합니다.

## <a name="see-also"></a>참고자료

[HLSL 속성 페이지](hlsl-property-pages.md)<br>
[HLSL 속성 페이지: 고급](hlsl-property-pages-advanced.md)<br>
[HLSL 속성 페이지: 출력 파일](hlsl-property-pages-output-files.md)
