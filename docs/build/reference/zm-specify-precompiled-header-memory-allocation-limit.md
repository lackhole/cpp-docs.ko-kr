---
title: /Zm(미리 컴파일된 헤더 메모리 할당 제한 지정)
ms.date: 03/08/2019
f1_keywords:
- /zm
helpviewer_keywords:
- PCH files, memory allocation limit
- Zm compiler option [C++]
- /Zm compiler option [C++]
- precompiled header files, memory allocation limit
- Specify Precompiled Header Memory Allocation Limit compiler option
- cl.exe compiler, memory allocation limit
- .pch files, memory allocation limit
- memory allocation, Memory Allocation Limit compiler option
- -Zm compiler option [C++]
ms.assetid: 94c77d5e-6672-46a7-92e0-3f69e277727d
ms.openlocfilehash: 09df8e1ee9a97289e29e1191e8c1585580435b79
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315276"
---
# <a name="zm-specify-precompiled-header-memory-allocation-limit"></a>/Zm(미리 컴파일된 헤더 메모리 할당 제한 지정)

미리 컴파일된 헤더를 생성하기 위해 컴파일러에서 할당하는 메모리의 양을 결정합니다.

## <a name="syntax"></a>구문

```
/Zmfactor
```

## <a name="arguments"></a>인수

*factor*<br/>
미리 컴파일된 헤더를 생성하기 위해 컴파일러에서 사용하는 메모리의 양을 결정하는 배율 인수입니다.

합니다 *비율* 인수는 컴파일러에 정의 된 작업 버퍼의 기본 크기의 백분율입니다. 기본값인 *비율* 100 (퍼센트) 이지만 크거나 작게 지정할 수 있습니다.

## <a name="remarks"></a>설명

Visual Studio 2015 이전 버전에는 C++ 컴파일러가 여러 개별 힙을 사용 했으며 각 제한 합니다. 현재 컴파일러 동적으로 총 힙 크기 한계까지 필요에 따라 힙을 증가 하 고 여러 주소 범위를 구성 하는 미리 컴파일된 헤더를 허용 합니다. 따라서 합니다 **/Zm** 컴파일러 옵션은 거의 필요 하지 않습니다.

컴파일러의 힙 공간이 부족 하 고 내보내는 경우 합니다 [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) 사용 하는 경우 오류 메시지를 **/Zm** 컴파일러 옵션을 너무 많은 메모리를 예약한 것일 수 있습니다. 제거해 합니다 **/Zm** 옵션입니다.

컴파일러에서는 [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) 오류 메시지가 발생 하면 [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) 메시지를 지정 합니다 *비율* 를사용하여컴파일할때사용하는인수 **/Zm** 컴파일러 옵션입니다. 미리 컴파일된 헤더를 사용 하는 경우이 메시지는 중요 한 `#pragma hdrstop`합니다. 다른 경우에는 것은 Windows 가상 메모리 부족 문제 및 사용 하기 위한 권장 사항을 인해 의사 오류를 **/Zm** 옵션을 무시 해야 합니다. 대신 사용 하는 경우 병렬 프로세스 수를 줄이는 것이 좋습니다 합니다 **/maxcpucount** msbuild 옵션입니다. 와 함께에서 EXE 합니다 **/MP** CL 옵션입니다. EXE 수 있습니다. 자세한 내용은 [미리 컴파일된 헤더 (PCH) 문제와 권장 사항을](https://devblogs.microsoft.com/cppblog/precompiled-header-pch-issues-and-recommendations/)합니다.

다음 표는 하는 방법을 *비율* 인수 기본 미리 컴파일된 헤더 버퍼의 크기를 75mb로 가정할 경우 메모리 할당 제한에 영향을 줍니다.

|값 *비율*|메모리 할당 제한|
|-----------------------|-----------------------------|
|10|7.5 MB|
|100|75 MB|
|200|150MB|
|1000|750MB|
|2000|1500 (MB)|

## <a name="other-ways-to-set-the-memory-allocation-limit"></a>메모리 할당 제한을 설정하는 기타 방법

### <a name="to-set-the-zm-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 /Zm 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 탐색 창에서 선택 **구성 속성** > **C /C++** > **명령줄**.

1. 입력 된 **/Zm** 컴파일러 옵션을 **추가 옵션** 상자.

### <a name="to-set-the-zm-compiler-option-programmatically"></a>프로그래밍 방식으로 /Zm 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
