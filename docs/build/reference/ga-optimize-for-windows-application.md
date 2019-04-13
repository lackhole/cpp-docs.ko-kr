---
title: /GA(Windows 응용 프로그램 최적화)
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
ms.openlocfilehash: a5eb6a10f3c4833ecc3e9d9c8451894788ebd938
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57817386"
---
# <a name="ga-optimize-for-windows-application"></a>/GA(Windows 응용 프로그램 최적화)

스레드 로컬 저장소 (TLS) 변수에 액세스 하는 것에 대한.exe 파일에 대한 보다 효율적인 코드의 결과입니다.

## <a name="syntax"></a>구문

```
/GA
```

## <a name="remarks"></a>설명

**/GA** 로 선언 된 데이터에 대한 액세스 속도 [__declspec (thread)](../../cpp/declspec.md) Windows 기반 프로그램에서입니다. 이 옵션을 설정 합니다 [__tls_index](/windows/desktop/ProcThread/thread-local-storage) 매크로 0으로 간주 됩니다.

DLL에 **/GA**를 사용할 경우 잘못된 코드가 생성 될 수 있습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 C++ 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. **C/C++** 폴더를 클릭합니다.

1. **명령줄** 속성 페이지를 클릭합니다.

1. **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
