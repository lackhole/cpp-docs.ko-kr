---
title: x64용 MASM (ml64.exe)
ms.date: 08/30/2018
helpviewer_keywords:
- ml64
- ml64.exe
- masm for x64
ms.assetid: 89059103-f372-4968-80ea-0c7f90bb9c91
ms.openlocfilehash: 1a92d2a22e8aa9df29c18fa36ff4508eb8eec57f
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65445858"
---
# <a name="masm-for-x64-ml64exe"></a>x64용 MASM (ml64.exe)

Visual Studio 코드를 x64 대상으로 호스트 된 버전의 어셈블러 MASM (Microsoft)을 32 비트 및 64 비트를 포함합니다. X64를 받아들이는 어셈블러는이 ml64.exe 라는 어셈블러 언어입니다. 선택 하면 MASM 명령줄 도구가 설치 된 C++ Visual Studio를 설치 하는 동안 작업 합니다. MASM 도구는 별도 다운로드로 제공 됩니다. 다운로드 하 여 Visual Studio의 복사본을 설치 하는 방법에 지침은 [Visual Studio 설치](/visualstudio/install/install-visual-studio)합니다. 전체 Visual Studio IDE를 설치 하지 않을 않지만 원하는 명령줄 도구를 다운로드 합니다 [for Visual Studio Build Tools](https://visualstudio.microsoft.com/downloads/)합니다.

MASM을 사용 하 여 빌드를 명령줄에서 대상으로 x64에 대 한 코드, x64 용 개발자 명령 프롬프트를 사용 해야 필요한 경로 및 기타 환경 변수가 설정 하는 대상입니다. 개발자 명령 프롬프트를 시작 하는 방법에 대 한 자세한 내용은 [C 빌드 /C++ 명령 줄의 코드가](../../build/building-on-the-command-line.md)합니다.

Ml64.exe 명령줄 옵션에 대 한 자세한 내용은 [ML 및 ML64 명령줄 참조](../../assembler/masm/ml-and-ml64-command-line-reference.md)합니다.

인라인 어셈블러 또는 ASM 키워드를 사용 하는 x64 또는 ARM 대상에 대 한 지원 되지 않습니다. X86 코드는 인라인 어셈블러는 포트를 x64 또는 ARM 코드를 변환할 수 있습니다 C++컴파일러 내장 함수를 사용 하 여, 또는 어셈블러 언어 소스 파일을 만듭니다. Microsoft C++ 컴파일러 내장 함수 예제에서는 privileged, 검색/테스트, 연동, 등에에서으로 플랫폼 간 방식으로 최대한 가까운 비트에 대 한 특수 함수 지침을 사용 하 여 수 있도록 지원 합니다. 사용할 수 있는 내장 함수에 대 한 내용은 참조 하세요 [컴파일러 내장 함수](../../intrinsics/compiler-intrinsics.md)합니다.

## <a name="add-an-assembler-language-file-to-a-visual-studio-c-project"></a>Visual Studio에 어셈블러 언어 파일을 추가 C++ 프로젝트

Visual Studio 프로젝트 시스템에는 MASM을 사용 하 여 빌드된 어셈블러 언어 파일을 지원 하면 C++ 프로젝트입니다. X64 어셈블러 언어 소스 파일 및 x64를 완벽 하 게 지 원하는 MASM을 사용 하 여 개체 파일에 빌드를 만들 수 있습니다. 이러한 개체 파일에 연결할 수 있습니다 프로그램 C++ 코드를 x64 용으로 빌드된 대상입니다. 이 x64 부족을 해결 하기 위해 한 가지 방법은 인라인 어셈블러 합니다.

### <a name="to-add-an-assembler-language-file-to-an-existing-visual-studio-c-project"></a>어셈블러 언어 파일을 기존 Visual Studio에 추가할 C++ 프로젝트

1. **솔루션 탐색기**에서 프로젝트를 선택합니다. 메뉴 모음에서 선택 **프로젝트**하십시오 **빌드 사용자 지정**합니다.

1. 에 **Visual C++ 빌드 사용자 지정 파일** 대화 상자에서 옆에 확인란 **masm(.targets,.props)** 합니다. 선택할 **확인** 하 여 선택 내용을 저장 하 고 대화 상자를 닫습니다.

1. 메뉴 모음에서 선택 **프로젝트**하십시오 **새 항목 추가**합니다.

1. 에 **새 항목 추가** 대화 상자에서  **C++ 파일 (.cpp)** 가운데 창에서. 에 **이름** edit 컨트롤, 있는 새 파일 이름을 입력을 **.asm** 대신.cpp 확장명입니다. 선택할 **추가** 프로젝트에 파일을 추가 하 여 대화 상자를 닫습니다.

추가한.asm 파일에 어셈블러 언어 코드를 만듭니다. 솔루션을 빌드할 때 프로젝트에 다음 연결 된 개체 파일에.asm 파일을 조합 하는 MASM 어셈블러 호출 됩니다. 기호 액세스가 보다 용이할 선언으로 어셈블러 함수 `extern "C"` 에서 C++ 사용 하지 않고 소스 코드는 C++ 어셈블러-언어로 장식 규칙이 소스 파일 이름.

## <a name="ml64-specific-directives"></a>ml64 별 지시문

X64를 대상으로 하는 어셈블러 언어 소스 코드에서 다음 ml64 별 지시문을 사용할 수 있습니다.

- [.ALLOCSTACK](../../assembler/masm/dot-allocstack.md)

- [.ENDPROLOG](../../assembler/masm/dot-endprolog.md)

- [.PUSHFRAME](../../assembler/masm/dot-pushframe.md)

- [.PUSHREG](../../assembler/masm/dot-pushreg.md)

- [.SAVEREG](../../assembler/masm/dot-savereg.md)

- [.SAVEXMM128](../../assembler/masm/dot-savexmm128.md)

- [.SETFRAME](../../assembler/masm/dot-setframe.md)

또한 합니다 [PROC](../../assembler/masm/proc.md) 지시문 ml64.exe 사용에 대 한 업데이트 되었습니다.

## <a name="32-bit-address-mode-address-size-override"></a>32 비트 주소 모드 (주소 크기 재정의)

MASM에 메모리 피연산자가 32 비트 레지스터를 포함 하는 경우 0x67 주소 크기 재정을 내보냅니다. 예를 들어, 다음 예제에서는 내보낼 주소 크기 재정의 초래 합니다.

```asm
mov rax, QWORD PTR [ecx]
mov eax, DWORD PTR [ecx*2+r10d]
mov eax, DWORD PTR [ecx*2+r10d+0100h]
prefetch [eax]
movnti rax, QWORD PTR [r8d]
```

MASM 32 비트 치환 나타나면 메모리 피연산자로을 위한는 64 비트 주소 지정 하는 것으로 가정 합니다. 현재 이러한 피연산자를 사용 하 여 32 비트 주소 지정에 대 한 지원 되지 않습니다 됩니다.

마지막으로, 다음 코드에서 볼 수 있듯이 레지스터 크기, 메모리 피연산자 내에서 혼합 오류가 발생 합니다.

```asm
mov eax, DWORD PTR [rcx*2+r10d]
mov eax, DWORD PTR [ecx*2+r10+0100h]
```

## <a name="see-also"></a>참고자료

[Microsoft 매크로 어셈블러 참조](../../assembler/masm/microsoft-macro-assembler-reference.md)<br/>