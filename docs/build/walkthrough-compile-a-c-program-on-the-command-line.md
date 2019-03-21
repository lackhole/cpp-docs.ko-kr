---
title: '연습: 명령줄에서 C 프로그램 컴파일'
ms.custom: conceptual
ms.date: 09/24/2018
helpviewer_keywords:
- command-line applications [C++], C programs
- Visual C, compiling
- compiling programs [C++]
- C program compiling [C++]
ms.assetid: 7e74cc2d-54b1-49de-b7ad-d3ae6b39ab8d
ms.openlocfilehash: 54f5810e60cdaada6a99651a732570c88ea883ce
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822225"
---
# <a name="walkthrough-compile-a-c-program-on-the-command-line"></a>연습: 명령줄에서 C 프로그램 컴파일

Visual C++에는 전체 Windows 데스크톱 응용 프로그램, 모바일 앱 등 기본적인 콘솔 프로그램에서 모든이 만드는 데 사용할 수 있는 C 컴파일러가 포함 됩니다.

이 연습에서는 basic, "Hello, World"를 만드는 방법을 보여 줍니다.-C 프로그램 텍스트를 사용 하 여 편집기에서 스타일 및 다음 명령줄에서 컴파일합니다. 대신 명령줄에서 c + +에서 작동 됩니다, 참조 [연습: 명령줄에서 네이티브 C++ 프로그램 컴파일](walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)을 참조하세요. 명령줄을 사용 하는 대신 Visual Studio IDE를 시도 하세요. 참조 하려는 경우 [연습: 프로젝트 및 솔루션 (c + +)를 작업할](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) 또는 [c + + 데스크톱 개발에 Visual Studio IDE를 사용 하 여](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)합니다.

## <a name="prerequisites"></a>전제 조건

이 연습을 완료 하려면 설치 해야 Visual Studio 및 선택적 Visual C++ 구성 요소 또는 Build Tools for Visual Studio입니다.

Visual Studio에는 다양 한 언어 및 플랫폼에 대 한 완전 한 편집기, 리소스 관리자, 디버거 및 컴파일러를 지 원하는 강력한 통합된 개발 환경입니다. 이러한 기능 및 다운로드 하 고 무료 Visual Studio Community edition을 비롯해 Visual Studio를 설치 하는 방법에 대 한 내용은 [Visual Studio 설치](/visualstudio/install/install-visual-studio)합니다.

명령줄 도구 집합, 컴파일러, 도구,만 C 및 C++ 프로그램을 작성 하는 데 필요한 라이브러리가 Visual Studio 버전의 Visual Studio Build Tools를 설치 합니다. 빌드 랩에 안성맞춤입니다 또는 클래스 룸 연습 하 고 비교적 빠르게 설치 합니다. 명령줄 도구 집합을 설치 하려면 다운로드 [for Visual Studio Build Tools](https://go.microsoft.com/fwlink/p/?linkid=875721) 설치 관리자를 실행 합니다.

명령줄에서 C 또는 C++ 프로그램을 빌드할 수 있습니다, 전에 명령줄에서 액세스할 수 있습니다 및 도구가 설치 되어 있는지 확인 해야 합니다. Visual C++에는 도구, 헤더 및 라이브러리를 사용 하 여 찾으려는 명령줄 환경에 대 한 복잡 한 요구 사항이 있습니다. **일반 명령 프롬프트 창에서 Visual C++를 사용할 수 없습니다** 몇 가지 준비 없이 합니다. 필요는 *개발자 명령 프롬프트* 창 일반 명령 프롬프트 창에 설정 된 모든 필수 환경 변수입니다. 다행히 Visual C++ 명령줄 빌드에 대 한 설정 환경을 설정 하는 개발자 명령 프롬프트를 시작할 수에 대 한 바로 가기 키를 설치 합니다. 그러나 개발자 명령 프롬프트 바로 가기 및를 위치 이름은 거의 모든 버전의 Visual C++ 및 다른 버전의 Windows에서 서로 다릅니다. 첫 번째 연습에서는 작업의 오른쪽 바로 가기를 사용 하 여 찾는 것입니다.

> [!NOTE]
> 개발자 명령 프롬프트 바로 가기를 컴파일러 및 도구에 대 한 및 모든 필수 헤더 및 라이브러리에 대 한 올바른 경로 자동으로 설정합니다. 각 빌드 구성에 대 한 이러한 값 중 일부 다릅니다. 값을 설정 해야 이러한 환경을 직접 바로 가기 중 하나를 사용 하지 않는 경우. 자세한 내용은 [명령줄 빌드에 맞는 경로 및 환경 변수 설정](setting-the-path-and-environment-variables-for-command-line-builds.md)합니다. 복잡 한 빌드 환경 이기 때문에 개발자 명령 프롬프트 바로 가기를 사용 하 여 직접 작성 하는 대신 것이 좋습니다.

## <a name="open-a-developer-command-prompt"></a>개발자 명령 프롬프트를 열으십시오

1. Windows 10에서 Visual Studio 2017을 설치한 경우 시작 메뉴를 연 다음 아래쪽으로 스크롤하여 및 엽니다는 **Visual Studio 2017** 폴더 (Visual Studio 2017 앱 제외). 선택할 **VS 2017 용 개발자 명령 프롬프트** 명령 프롬프트 창을 엽니다.

   Windows 10에서 Microsoft Visual C++ Build Tools 2015를 설치한 경우 엽니다는 **시작** 메뉴에서 다음 아래로 스크롤하여 및 열기를 **Visual C++ Build Tools** 폴더. 선택할 **Visual C++ 2015 x86 Native Tools 명령 프롬프트** 명령 프롬프트 창을 엽니다.

   Visual Studio의 다른 버전을 사용 하거나 다른 버전의 Windows 실행 하는 경우 시작 메뉴에서 확인 하거나 개발자 명령 프롬프트 바로 가기를 포함 하는 Visual Studio tools 폴더에 대 한 페이지를 시작 합니다. 또한 "개발자 명령 프롬프트"를 검색 하 고 Visual Studio의 설치 된 버전과 일치 하는 하나를 선택 하려면 Windows 검색 기능을 사용할 수 있습니다. 바로 가기를 사용 하 여 명령 프롬프트 창을 엽니다.

1. 다음으로, Visual C++ 개발자 명령 프롬프트를 올바르게 설정 되어 있는지 확인 합니다. 명령 프롬프트 창에서 입력 `cl` 및 다음과 같은 출력이 표시 되는지 확인 합니다.

   ```Output
   C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>cl
   Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
   Copyright (C) Microsoft Corporation.  All rights reserved.

   usage: cl [ option... ] filename... [ /link linkoption... ]
   ```

   현재 디렉터리 또는 Visual C++ 및 설치 된 업데이트의 버전에 따라 버전 번호가 차이점이 있을 수 있습니다. 위의 출력은 표시 되는 항목을 다음 경우 명령줄에서 C 또는 C++ 프로그램을 빌드할 준비가 됩니다.

   > [!NOTE]
   > "'C l' is not recognized as는 내부 또는 외부 명령, 실행할 수 있는 프로그램 또는 배치 파일"와 같은 오류가 발생할 경우 오류 C1034 또는 오류 LNK1104 실행할 때 합니다 **cl** 하거나 개발자 명령 프롬프트를 사용 하지 않는 명령을 또는 Visual C++ 설치를 사용 하 여 문제가 발생 했습니다. 계속 하기 전에이 문제를 수정 해야 합니다.

   개발자 명령 프롬프트 바로 가기를 찾을 수 없으면 또는 입력 하면 오류 메시지를 받게 되 면 `cl`, 다음 Visual C++ 설치에 문제가 있을 수 있습니다. Visual Studio 2017을 사용 하는 경우 다시 설치 합니다 **C++를 사용한 데스크톱 개발** Visual Studio 설치 관리자에서 작업 합니다. 자세한 내용은 참조 하세요 [Visual Studio에서 C++ 설치 지원](vscpp-step-0-installation.md)합니다. 또는 다시 설치 합니다 [for Visual Studio Build Tools](https://go.microsoft.com/fwlink/p/?linkid=875721)합니다. 작동 될 때까지 다음 섹션으로 하지 마십시오. 설치 및 Visual Studio 문제 해결에 대 한 자세한 내용은 참조 하세요. [Visual Studio 설치](/visualstudio/install/install-visual-studio)합니다.

   > [!NOTE]
   > 개발자 명령 프롬프트 바로 가기에 대 한 바로 가기 메뉴를 열고 선택한 후 마우스 오른쪽 단추로 클릭 해야 컴퓨터 시스템 보안 구성에서 Windows의 버전에 따라 **관리자 권한으로 실행** 를 성공적으로 작성 하 고이 연습을 수행 하 여 만든 프로그램을 실행 합니다.

## <a name="create-a-c-source-file-and-compile-it-on-the-command-line"></a>C 소스 파일을 만들고 명령줄에서 컴파일하십시오.

1. 개발자 명령 프롬프트 창에서 입력 `cd c:\` c: 드라이브의 루트에는 현재 작업 디렉터리를 변경 합니다. 그런 다음, 입력 `md c:\simple` 디렉터리를 만들고 enter `cd c:\simple` 해당 디렉터리로 변경 합니다. 이 디렉터리는 컴파일된 프로그램과 소스 파일에 저장 됩니다.

1. 입력 `notepad simple.c` 개발자 명령 프롬프트에서. 표시 되는 메모장 경고 대화 상자에서 선택 **예** 작업 디렉터리에 새 simple.c 파일을 만들려고 합니다.

1. 메모장에서 다음 코드 줄을 입력 합니다.

    ```C
    #include <stdio.h>

    int main()
    {
        printf("Hello, World! This is a native C program compiled on the command line.\n");
        return 0;
    }
    ```

1. 메모장의 메뉴 모음에서 선택 **파일** > **저장** simple.c 작업 디렉터리에 저장 합니다.

1. 개발자 명령 프롬프트 창으로 전환 합니다. 입력 `dir` c:\simple 디렉터리의 내용을 나열 하려면 명령 프롬프트에서. 원본 파일 simple.c 디렉터리 나열 다음과 비슷하게 표시 됩니다.

    ```Output
    C:\simple>dir
     Volume in drive C has no label.
     Volume Serial Number is CC62-6545

     Directory of C:\simple

    10/02/2017  03:46 PM    <DIR>          .
    10/02/2017  03:46 PM    <DIR>          ..
    10/02/2017  03:36 PM               143 simple.c
                   1 File(s)            143 bytes
                   2 Dir(s)  514,900,566,016 bytes free

    ```

   날짜 및 기타 세부 정보는 컴퓨터에 달라 집니다. 소스 코드 파일이 보이지 않으면 simple.c, 만든 c:\simple 디렉터리로 변경한 있는지 확인 및 메모장에서이 디렉터리에 소스 파일을 저장 했는지 확인 합니다. 또한.c 파일 이름 확장명을.txt 확장명이 아닌을 사용 하 여 소스 코드를 저장 해야 합니다.

1. 프로그램을 컴파일하려면 입력 `cl simple.c` 개발자 명령 프롬프트에서.

   컴파일러에서 표시 하는 출력 정보 줄에 simple.exe 실행 프로그램 이름을 확인할 수 있습니다.

    ```Output
    c:\simple>cl simple.c
    Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
    Copyright (C) Microsoft Corporation.  All rights reserved.

    simple.c
    Microsoft (R) Incremental Linker Version 14.10.25017.0
    Copyright (C) Microsoft Corporation.  All rights reserved.

    /out:simple.exe
    simple.obj
    ```

   > [!NOTE]
   > "'C l' is not recognized as는 내부 또는 외부 명령, 실행할 수 있는 프로그램 또는 배치 파일"와 같은 오류가 발생할 경우 오류 C1034 또는 오류 LNK1104가 개발자 명령 프롬프트에 올바르게 설정 되지 않았습니다. 이 문제를 해결 하는 방법에 대 한 내용은 돌아가서 합니다 **개발자 명령 프롬프트를 열고** 섹션입니다.

   > [!NOTE]
   > 다른 컴파일러 또는 링커 오류 또는 경고를 받게 되 면 오류를 수정, 그런 다음 저장 하 고 컴파일러를 다시 실행 하도록 소스 코드를 검토 합니다. 특정 오류에 대 한 자세한 오류 번호를 확인 하려면이 페이지의 맨 위에 있는 검색 상자를 사용 합니다.

1. 프로그램을 실행 하려면 입력 `simple` 명령 프롬프트에서.

   프로그램이 다음 텍스트를 표시하고 종료됩니다.

    ```Output
    Hello, World! This is a native C program compiled on the command line.
    ```

   축, 컴파일 및 명령줄을 사용 하 여 C 프로그램을 실행 했습니다.

## <a name="next-steps"></a>다음 단계

이 "Hello, World" 예제는 간단 C 프로그램을 가져올 수 있습니다. 실제 프로그램에는 헤더 파일 및 자세한 원본 파일을 라이브러리에 연결 하 고 유용한 작업을 수행 합니다.

표시 된 예제 코드를 입력 하는 대신 사용자 고유의 C 코드를 빌드하려면이 연습의 단계를 사용할 수 있습니다. 다른 곳에서 검색 하는 많은 C 코드 샘플 프로그램을 빌드할 수 있습니다. 추가 소스 코드 파일에는 프로그램을 컴파일하려면 입력에서 명령 줄에 모두 같은:

`cl file1.c file2.c file3.c`

컴파일러는 file1.exe 라는 프로그램을 출력 합니다. 추가 program1.exe를 이름으로 변경 하는 [/출력](reference/out-output-file-name.md) 링커 옵션:

`cl file1.c file2.c file3.c /link /out:program1.exe`

자세한 프로그래밍 실수를 자동으로 catch 하려면 하나를 사용 하 여 컴파일하는 권장 합니다 [/w3](reference/compiler-option-warning-level.md) 하거나 [/w4](reference/compiler-option-warning-level.md) 경고 수준 옵션:

`cl /W4 file1.c file2.c file3.c /link /out:program1.exe`

컴파일러에서 cl.exe에 더 많은 옵션을 빌드, 최적화, 디버그, 적용 하 고 코드를 분석할 수 있습니다. 빠른 목록을 입력 `cl /?` 개발자 명령 프롬프트에서. 또한 컴파일 및 연결할 수 별도로 있으며 더 복잡 한 빌드 시나리오에서 링커 옵션을 적용 합니다. 컴파일러 및 링커 옵션 및 사용에 대 한 자세한 내용은 참조 하세요. [C/C++ 빌드 참조](reference/c-cpp-building-reference.md)합니다.

구성 하 고 명령줄에서 보다 복잡 한 프로젝트를 빌드할 NMAKE 메이크파일, 있고 MSBuild 및 프로젝트 파일을 사용할 수 있습니다. 이러한 도구 사용에 대 한 자세한 내용은 참조 하세요. [NMAKE 참조](reference/nmake-reference.md) 하 고 [MSBuild](msbuild-visual-cpp.md)합니다.

C 및 C++ 언어는 유사 하지만 동일 하지는 않습니다. MSVC 컴파일러 코드를 컴파일할 때 사용할 언어를 결정 하는 간단한 규칙을 사용 합니다. 기본적으로 MSVC 컴파일러는 C 소스 코드로.c로 끝나는 모든 파일 및 c + + 소스 코드로.cpp으로 끝나는 모든 파일을 처리 합니다. 모든 파일 C 종속 되지 않는 파일 이름 확장명으로 취급 하도록 컴파일러를 강제 적용 하려면 사용 합니다 [/Tc](reference/tc-tp-tc-tp-specify-source-file-type.md) 컴파일러 옵션입니다.

Visual C++ C 컴파일러는 ISO C99 표준을 호환 되지만 엄격 하 게 준수 하지 않는 경우 대부분의 경우에서 이식 가능한 C 코드 컴파일 및 예상 대로 실행 합니다. Visual C++ ISO C11의 변경 사항 중 대부분을 지원 하지 않습니다. 특정 라이브러리 함수 및 POSIX 함수 이름을 MSVC 컴파일러에서 사용 되지 않습니다. 함수는 지원 되지만 기본 이름이 변경 되었습니다. 자세한 내용은 [CRT의 보안 기능](../c-runtime-library/security-features-in-the-crt.md) 하 고 [컴파일러 경고 (수준 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)합니다.

## <a name="see-also"></a>참고자료

[연습: 표준 C++ 프로그램 만들기(C++)](../windows/walkthrough-creating-a-standard-cpp-program-cpp.md)<br/>
[C# 언어 참조](../c-language/c-language-reference.md)<br/>
[프로젝트 및 빌드 시스템](projects-and-build-systems-cpp.md)<br/>
[호환성](../c-runtime-library/compatibility.md)
