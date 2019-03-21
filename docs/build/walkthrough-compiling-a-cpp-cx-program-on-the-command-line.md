---
title: '연습: 컴파일 C + + /CX 프로그램 명령줄에서'
ms.date: 09/24/2018
ms.assetid: 626f5544-69ed-4736-83a9-f11389b371b2
ms.openlocfilehash: ad718a2eb876430d7721d0cd20cfd5b952750f8b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809511"
---
# <a name="walkthrough-compiling-a-ccx-program-on-the-command-line"></a>연습: 컴파일 C + + /CX 프로그램 명령줄에서

Windows 런타임을 대상으로 하는 Visual C++ 프로그램을 만들어 명령줄에서 빌드할 수 있습니다. Visual C++는 Windows 런타임 프로그래밍 모델을 대상으로 하는 추가 형식 및 연산자가 있는 Visual C++ 구성 요소 확장명(C++/CX)을 지원합니다. 에서는 C++ 유니버설 Windows 플랫폼 (UWP), Windows Phone 8.1 및 Windows 데스크톱 앱을 빌드할 CX 합니다. 자세한 내용은 [는 C+ 둘러보기 + CX](https://msdn.microsoft.com/magazine/dn166929.aspx) 하 고 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)합니다.

이 연습에서는 텍스트 편집기를 사용하여 기본적인 C++/CX 프로그램을 만든 다음 명령줄에서 컴파일합니다. 여기에 나와 있는 내용을 입력하는 대신 C++/CX 프로그램을 직접 사용할 수도 있고 다른 도움말 문서의 C++/CX 코드 샘플을 사용할 수도 있습니다. 이 방법은 구축 하 고 UI 요소가 없는 소형 모듈을 테스트 하는 데 유용 합니다.)

> [!NOTE]
> 또한 Visual Studio IDE를 사용하여 C++/CX 프로그램을 컴파일할 수 있습니다. IDE에서 디자인, 디버깅, 에뮬레이션 및 배포 지원 명령줄에서 사용할 수 없는 포함 하므로 IDE를 사용 하 여 유니버설 Windows 플랫폼 (UWP) 앱을 빌드하는 것이 좋습니다. 자세한 내용은 [C++ UWP 앱을 만들](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)합니다.

## <a name="prerequisites"></a>전제 조건

C++ 언어의 기본적인 사항을 알고 있습니다.

## <a name="compiling-a-ccx-program"></a>C++/CX 프로그램 컴파일

컴파일하려면 C++ /cli를 사용 해야 CX, 합니다 [/ZW](reference/zw-windows-runtime-compilation.md) 컴파일러 옵션. MSVC 컴파일러를 Windows 런타임을 대상으로 하 여 필요한 라이브러리를 링크는.exe 파일을 생성 합니다.

#### <a name="to-compile-a-ccx-application-on-the-command-line"></a>명령줄에서 C++/CX 응용 프로그램을 컴파일하려면

1. 엽니다는 **개발자 명령 프롬프트** 창입니다. (에 **시작** 창을 열려면 **앱**합니다. 열기는 **Visual Studio Tools** Visual Studio 버전 아래의 폴더를 선택 합니다 **개발자 명령 프롬프트** 바로 가기.) 개발자 명령 프롬프트 창을 여는 방법에 대 한 자세한 내용은 참조 하세요. [명령줄에서 MSVC 도구 집합을 사용 하 여](building-on-the-command-line.md)입니다.

   컴퓨터 운영 체제 및 구성에 따라 코드를 정상적으로 컴파일하려면 관리자 자격 증명이 필요할 수 있습니다. 명령 프롬프트 창을 관리자 권한으로을 실행 하려면 바로 가기 메뉴를 열고 **개발자 명령 프롬프트** 를 선택한 후 **관리자 권한으로 실행**합니다.

1. 명령 프롬프트에서 입력 **notepad basiccx.cpp**합니다.

   선택할 **예** 묻는 파일을 만듭니다.

1. 메모장에 다음 줄을 입력합니다.

    ```cpp
    using namespace Platform;

    int main(Platform::Array<Platform::String^>^ args)
    {
        Platform::Details::Console::WriteLine("This is a C++/CX program.");
    }
    ```

1. 메뉴 모음에서 선택 **파일** > **저장**합니다.

   Windows 런타임을 사용 하는 Visual C++ 소스 파일을 만들었습니다 [Platform 네임 스페이스](../cppcx/platform-namespace-c-cx.md) 네임 스페이스입니다.

1. 명령 프롬프트에서 입력 **cl /EHsc /ZW basiccx.cpp /link /subsystem: console**합니다. cl.exe 컴파일러는 이 소스 파일을 .obj 파일로 컴파일한 다음 링커를 실행하여 실행 프로그램인 basiccx.exe를 생성합니다. (합니다 [/EHsc](reference/eh-exception-handling-model.md) 컴파일러 옵션에는 C++ 예외 처리 모델을 지정 하며 [/l i n](reference/link-pass-options-to-linker.md) 콘솔 응용 프로그램을 지정 하는 플래그입니다.)

1. Basiccx.exe 프로그램을 명령 프롬프트를 실행 하려면 입력 **basiccx**합니다.

   프로그램이 다음 텍스트를 표시하고 종료됩니다.

    ```Output
    This is a C++/CX program.
    ```

## <a name="see-also"></a>참고자료

[프로젝트 및 빌드 시스템](projects-and-build-systems-cpp.md)<br/>
[MSVC 컴파일러 옵션](reference/compiler-options.md)
