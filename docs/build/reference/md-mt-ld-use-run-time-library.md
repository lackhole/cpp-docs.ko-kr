---
title: /MD,-MT,-LD (런타임 라이브러리 사용)
ms.date: 07/17/2019
f1_keywords:
- /ld
- /mt
- VC.Project.VCCLWCECompilerTool.RuntimeLibrary
- VC.Project.VCCLCompilerTool.RuntimeLibrary
- /md
- /ml
helpviewer_keywords:
- /MT compiler option [C++]
- -MD compiler option [C++]
- threading [C++], multithread compiler option
- MSVCRTD.lib
- MSVCRT.lib
- LIBCMT.lib
- MD compiler option [C++]
- /MD compiler option [C++]
- MT compiler option [C++]
- LD compiler option [C++]
- MDd compiler option [C++]
- -MDd compiler option [C++]
- LIBCD.lib
- -MTd compiler option [C++]
- MTd compiler option [C++]
- /MTd compiler option [C++]
- -LD compiler option [C++]
- /MDd compiler option [C++]
- multithread compiler option
- _STATIC_CPPLIB symbol
- LIBC.lib
- /LD compiler option [C++]
- DLLs [C++], compiler options
- LIBCMTD.lib
- -MT compiler option [C++]
ms.assetid: cf7ed652-dc3a-49b3-aab9-ad60e5395579
ms.openlocfilehash: 4e734233d94bf57d6838bd4d37c023d55f1d5f6b
ms.sourcegitcommit: 7f5b29e24e1be9b5985044a030977485fea0b50c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/17/2019
ms.locfileid: "68299752"
---
# <a name="md-mt-ld-use-run-time-library"></a>/MD, /MT, /LD(런타임 라이브러리 사용)

다중 스레드 모듈이 DLL인지 나타내고 런타임 라이브러리의 출시용 또는 디버그용 버전을 지정합니다.

## <a name="syntax"></a>구문

```
/MD[d]
/MT[d]
/LD[d]
```

## <a name="remarks"></a>설명

|옵션|설명|
|------------|-----------------|
|**/MD**|애플리케이션에서 런타임 라이브러리의 다중 스레드별 및 DLL별 버전을 사용하게 됩니다. `_MT` 및 `_DLL`을 정의하고 컴파일러가 라이브러리 이름 MSVCRT.lib를 .obj 파일에 배치하게 만듭니다.<br /><br /> 이 옵션을 사용하여 컴파일한 애플리케이션은 MSVCRT.lib에 정적으로 연결됩니다. 이 라이브러리는 링커가 외부 참조를 확인할 수 있는 코드의 계층을 제공합니다. 실제 작업 코드는 MSVCRT.lib와 링크된 애플리케이션이 런타임 시에 사용하는 MSVCR*versionnumber*.DLL에 포함되어 있습니다.|
|**/MDd**|`_DEBUG`, `_MT` 및 `_DLL`을 정의하고 애플리케이션에서 런타임 라이브러리의 디버그 다중 스레드 DLL별 버전을 사용하게 됩니다. 또한 컴파일러가 라이브러리 이름 MSVCRTD.lib를 .obj 파일에 배치하게 만듭니다.|
|**/MT**|애플리케이션에서 런타임 라이브러리의 다중 스레드 정적 버전을 사용하게 됩니다. `_MT`를 정의하며, 링커가 LIBCMT.lib를 사용하여 외부 기호를 확인하도록 컴파일러가 라이브러리 이름인 LIBCMT.lib를 .obj 파일에 추가합니다.|
|**/MTd**|`_DEBUG` 및 `_MT`를 정의합니다. 또한, 이 옵션은 컴파일러가 .obj 파일에 라이브러리 이름 LIBCMTD.lib를 배치하여 링커가 LIBCMTD.lib를 사용하여 외부 기호를 확인하도록 만듭니다.|
|**/LD**|DLL을 만듭니다.<br /><br /> 전달된 **/DLL** 옵션을 링커로 합니다. 링커는 `DllMain` 함수를 찾지만 이 함수가 꼭 있어야 하는 것은 아닙니다. `DllMain` 함수를 작성하지 않으면 링커는 TRUE를 반환하는 `DllMain` 함수를 삽입합니다.<br /><br /> DLL 시작 코드를 링크합니다.<br /><br /> 내보내기(.exp) 파일이 명령줄에 지정되지 않은 경우 가져오기 라이브러리(.lib)를 만듭니다. DLL을 호출하는 애플리케이션에 가져오기 라이브러리를 연결합니다.<br /><br /> [/Fe (EXE 파일 이름)](fe-name-exe-file.md)는 .exe 파일 대신 DLL 명명으로 해석됩니다. 기본적으로 프로그램 이름은 *basename*.exe 대신 *basename*.dll이 됩니다.<br /><br /> **/MD**를 명시적으로 지정하지 않으면 **/MT**를 의미합니다.|
|**/LDd**|디버그 DLL을 만듭니다. `_MT` 및 `_DEBUG`를 정의합니다.|

C 런타임 라이브러리 및 [/clr(공용 언어 런타임 컴파일)](clr-common-language-runtime-compilation.md)를 사용하여 컴파일할 때 사용되는 라이브러리에 대한 자세한 내용은 [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md)을 참조합니다.

링커의 지정된 호출에 전달되는 모든 모듈은 동일한 런타임 라이브러리 컴파일러 옵션(**/MD**, **/MT**, **/LD**)을 사용하여 컴파일되어야 합니다.

런타임 라이브러리의 디버그 버전을 사용하는 방법에 대한 자세한 내용은 [C 런타임 라이브러리 참조](../../c-runtime-library/c-run-time-library-reference.md)를 확인합니다.

Dll에 대한 자세한 내용은 [Visual Studio에서 C/C++ DLL 만들기](../dlls-in-visual-cpp.md)를 참조합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++**  > **명령줄** 속성 페이지를 선택합니다.

1. **코드 생성** 속성 페이지를 선택합니다.

1. **런타임 라이브러리** 속성을 수정합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeLibrary%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
