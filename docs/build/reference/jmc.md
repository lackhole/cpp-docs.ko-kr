---
title: / JMC (내 코드만 디버깅)
ms.date: 08/20/2018
f1_keywords:
- /JMC
helpviewer_keywords:
- /JMC compiler option [C++]
- Just my code [C++]
- -JMC compiler option [C++]
- User code, debugging
- JMC compiler option [C++]
ms.openlocfilehash: c107ad7107d2a65ed19719933aa127c0557916ce
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291641"
---
# <a name="jmc-just-my-code-debugging"></a>/ JMC (내 코드만 디버깅)

네이티브에 대 한 컴파일러 지원을 지정 *Just My Code* Visual Studio 디버거에서 디버깅 합니다. 이 옵션은 시스템, 프레임 워크, 라이브러리 및 기타 비 사용자 호출을 건너뛰므로 및 호출 스택 창에서 해당 호출을 축소 하려면 Visual Studio를 사용할 수 있는 사용자 설정을 지원 합니다. 합니다 **/JMC** 컴파일러 옵션은 Visual Studio 2017 버전 15.8부터 사용할 수 있습니다.

## <a name="syntax"></a>구문

> **/JMC**\[**-**]

## <a name="remarks"></a>설명

Visual Studio [Just My Code](/visualstudio/debugger/just-my-code) 설정은 시스템, 프레임 워크, 라이브러리 및 기타 비 사용자 호출을 통해 Visual Studio 디버거 단계 여부를 지정 합니다. 합니다 **/JMC** 컴파일러 옵션은 네이티브 코드만 디버깅에 대 한 지원 C++ 코드입니다. 때 **/JMC** 는 컴파일러 삽입 설정 도우미 함수를 호출 하 `__CheckForDebuggerJustMyCode`를 함수 프롤로그에서. 도우미 함수는 Visual Studio 디버거 내 코드만 단계 작업을 지 원하는 후크를 제공 합니다. 메뉴 모음에서 Visual Studio 디버거, 내 코드만 사용 하도록 설정 하려면 선택 **도구** > **옵션**를 다음에서 옵션을 설정 하 고 **디버깅**  >  **일반** > **내 코드만 사용**합니다.

**/JMC** 옵션을 사용 하려면 코드에는 C 런타임 라이브러리 (CRT)를 제공 하는 링크는 여 `__CheckForDebuggerJustMyCode` 도우미 함수입니다. 프로젝트에 CRT에 링크 하지 않는 경우 링커 오류가 표시 될 수 있습니다 **LNK2019: 외부 기호 __CheckForDebuggerJustMyCode 확인 되지 않은**합니다. 이 오류를 해결 하려면 CRT에 연결 또는 사용 하지 않도록 설정 합니다 **/JMC** 옵션입니다.

기본적으로 **/JMC** 컴파일러 옵션이 해제 됩니다. 그러나이 옵션을 Visual Studio 2017 버전 15.8 시작한 대부분의 Visual Studio 프로젝트 템플릿 사용 됩니다. 명시적으로이 옵션을 사용 하지 않으려면 사용 합니다 **/JMC-** 명령줄에서 옵션입니다. Visual Studio에서 프로젝트 속성 페이지 대화 상자를 열고 변경 합니다 **방금 내 코드 디버깅을 지원** 속성에는 **구성 속성** > **C /C++**   >  **일반** 속성 페이지 **아니요**합니다.

자세한 내용은 [ C++ 내 코드만](/visualstudio/debugger/just-my-code#BKMK_C___Just_My_Code) 에서 [Just My Code를 사용 하 여 Visual Studio에서 사용자 코드에만 디버그를 사용할지](/visualstudio/debugger/just-my-code), 및 시각적 개체 C++ 팀 블로그 게시물 [알림 C++ Visual Studio에서 단계별 실행 내 코드만](https://blogs.msdn.microsoft.com/vcblog/2018/06/29/announcing-jmc-stepping-in-visual-studio/)합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 선택 된 **구성 속성** > **C/C++** > **일반** 속성 페이지.

1. 수정 된 **방금 내 코드 디버깅을 지원** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
