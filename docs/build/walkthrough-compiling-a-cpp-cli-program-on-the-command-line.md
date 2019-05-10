---
title: '연습: 컴파일하는 C++on the Command Line /CLI 프로그램'
ms.date: 04/23/2019
ms.assetid: cef41c88-faf9-439d-8423-25aa3f5674dd
ms.openlocfilehash: 8a5c5659367350a80725b365ef9c431bbec209d1
ms.sourcegitcommit: 18d3b1e9cdb4fc3a76f7a650c31994bdbd2bde64
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2019
ms.locfileid: "64877449"
---
# <a name="walkthrough-compiling-a-ccli-program-on-the-command-line"></a>연습: 컴파일하는 C++on the Command Line /CLI 프로그램

CLR(공용 언어 런타임)을 대상으로 하는 Visual C++ 프로그램을 만들어 .NET Framework를 사용하여 명령줄에서 빌드할 수 있습니다. Visual C++은 .NET 프로그래밍 모델을 대상으로 하는 추가 형식 및 연산자가 있는 C++/CLI 프로그래밍 언어를 지원합니다. C +에 대 한 일반 정보에 대 한 + CLI 언어 참조 [.NET 프로그래밍을 사용 하 여 C++ /cli (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

이 연습에서는 텍스트 편집기를 사용하여 기본적인 C++/CLI 프로그램을 만든 다음 명령줄에서 컴파일합니다. 여기에 나와 있는 내용을 입력하는 대신 C++/CLI 프로그램을 직접 사용할 수도 있고 다른 도움말 문서의 C++/CLI 코드 샘플을 사용할 수도 있습니다. 이 방법은 구축 하 고 UI 요소가 없는 소형 모듈을 테스트 하는 데 유용 합니다.)

## <a name="prerequisites"></a>전제 조건

C++ 언어의 기본적인 사항을 알고 있습니다.

## <a name="compiling-a-ccli-program"></a>C++/CLI 프로그램 컴파일

다음 단계는 .NET Framework 클래스를 사용하는 C++/CLI 콘솔 응용 프로그램을 컴파일하는 방법을 보여줍니다.

컴파일하려면 C++ /cli를 사용 해야 CLI를 [/clr](reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션입니다. MSVC 컴파일러는 MSIL 코드를 포함 하는.exe 파일을 생성-MSIL과 네이티브 코드를 혼합 하거나-필요한.NET Framework 라이브러리에 연결 합니다.

### <a name="to-compile-a-ccli-application-on-the-command-line"></a>명령줄에서 C++/CLI 응용 프로그램을 컴파일하려면

1. 엽니다는 **개발자 명령 프롬프트** 창입니다. 특정 지침은 [개발자 명령 프롬프트 창을 열려면](building-on-the-command-line.md#developer_command_prompt)합니다.

   컴퓨터 운영 체제 및 구성에 따라 코드를 정상적으로 컴파일하려면 관리자 자격 증명이 필요할 수 있습니다. 명령 프롬프트 창을 관리자 권한으로을 실행 하려면 명령 프롬프트에 대 한 바로 가기 메뉴를 열고 선택한 단추로 **자세한** > **관리자 권한으로 실행**합니다.

1. 명령 프롬프트에 `notepad basicclr.cpp`를 입력합니다.

   선택할 **예** 묻는 파일을 만듭니다.

1. 메모장에 다음 줄을 입력합니다.

   ```cpp
   int main()
   {
       System::Console::WriteLine("This is a C++/CLI program.");
   }
   ```

1. 메뉴 모음에서 선택 **파일** > **저장**합니다.

   .NET Framework 클래스를 사용 하는 Visual C++ 소스 파일을 만들었습니다 (<xref:System.Console>)에 <xref:System> 네임 스페이스입니다.

1. 명령 프롬프트에 `cl /clr basicclr.cpp`를 입력합니다. cl.exe 컴파일러는 이 소스 파일을 MSIL이 포함된 .obj 파일로 컴파일한 다음 링커를 실행하여 실행 프로그램인 basicclr.exe를 생성합니다.

1. basicclr.exe 프로그램을 실행하려면 명령 프롬프트에 `basicclr`을 입력합니다.

   프로그램이 다음 텍스트를 표시하고 종료됩니다.

   ```Output
   This is a C++/CLI program.
   ```

## <a name="see-also"></a>참고자료

[C++ 언어 참조](../cpp/cpp-language-reference.md)<br/>
[프로젝트 및 빌드 시스템](projects-and-build-systems-cpp.md)<br/>
[MSVC 컴파일러 옵션](reference/compiler-options.md)
