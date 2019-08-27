---
title: /GA(Windows 애플리케이션 최적화)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.OptimizeForWindowsApplication
- /ga
helpviewer_keywords:
- /GA compiler option [C++]
- GA compiler option [C++]
- -GA compiler option [C++]
- Optimize for Windows compiler options
ms.assetid: be97323e-15a0-4836-862c-95980b51926a
ms.openlocfilehash: 85efa03a3f3d267580cbb0442839afb18ac6c313
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492860"
---
# <a name="ga-optimize-for-windows-application"></a>/GA(Windows 애플리케이션 최적화)

스레드 로컬 저장소(TLS) 변수에 액세스하는 효율적인 코드의 .exe 파일이 생성됩니다.

## <a name="syntax"></a>구문

```
/GA
```

## <a name="remarks"></a>설명

**/GA**는 Windows 기반 프로그램에서 [__declspec(thread)](../../cpp/declspec.md)로 선언된 데이터의 액세스 속도를 향상시킵니다. 이 옵션을 설정하면 [__tls_index](/windows/win32/ProcThread/thread-local-storage) 매크로는 0으로 간주됩니다.

DLL에 **/GA**를 사용할 경우 잘못된 코드가 생성될 수 있습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **C/C++** 폴더를 클릭합니다.

1. **명령줄** 속성 페이지를 클릭합니다.

1. **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
