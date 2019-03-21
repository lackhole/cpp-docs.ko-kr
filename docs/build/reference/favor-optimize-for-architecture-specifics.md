---
title: /favor(아키텍처에 맞게 최적화)
ms.date: 11/04/2016
f1_keywords:
- /favor
helpviewer_keywords:
- -favor compiler option [C++]
- /favor compiler option [C++]
ms.assetid: ad264df2-e30f-4d68-8bd0-10d6bee71a2a
ms.openlocfilehash: b914d3e6e7a2865ec610249ff51d320d7890adcb
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820457"
---
# <a name="favor-optimize-for-architecture-specifics"></a>/favor(아키텍처에 맞게 최적화)

**/favor:** `option` AMD 및 Intel 아키텍처에서 마이크로 아키텍처의 세부 정보 또는 특정 아키텍처에 대 한 최적화 된 코드를 생성 합니다.

## <a name="syntax"></a>구문

> **/favor:**{0}**blend** | **ATOM** | **AMD64** | **INTEL64**}

## <a name="remarks"></a>설명

**/favor:blend**<br/>
(x86 및 x64)는 AMD 및 Intel 아키텍처에서 마이크로 아키텍처 사양에 맞게 최적화된 코드를 생성합니다. 하는 동안 **/favor:blend** 최상의 성능을 제공 하지 못할 수도 광범위 한 x86 및 x64 프로세서에서 최상의 성능을 제공 하도록 설계는 특정 프로세서에 대해 되었습니다. 기본적으로 **/favor:blend** 적용 됩니다.

**/favor:ATOM**<br/>
(x86 및 x64)은 Intel Atom 프로세서 및 Intel Centrino Atom 프로세서 기술 사양에 맞게 최적화된 코드를 생성합니다. 사용 하 여 생성 된 코드가 **/favor:ATOM** Intel 프로세서에 대 한 Intel SSSE3, SSE3, SSE2 및 SSE 지침에도 발생할 수 있습니다.

**/favor:AMD64**<br/>
(x64만 해당)는 AMD Opteron 및 64비트 확장을 지원하는 Athlon 프로세서에 대해 생성된 코드를 최적화합니다. 최적화된 코드는 모든 x64 호환 플랫폼에서 실행할 수 있습니다. 사용 하 여 생성 된 코드가 **/favor:AMD64** Intel64를 지 원하는 Intel 프로세서에서 성능이 저하를 발생할 수 있습니다.

**/favor:INTEL64**<br/>
(x64만 해당)는 Intel64를 지원하는 Intel 프로세서에 대해 생성된 코드를 최적화하며 일반적으로 해당 플랫폼에서 더 나은 성능을 제공합니다. 결과 코드는 모든 x64 플랫폼에서 실행할 수 있습니다. 사용 하 여 생성 된 코드가 **/favor:INTEL64** AMD Opteron 및 64 비트 확장을 지 원하는 Athlon 프로세서에서 성능이 저하를 발생할 수 있습니다.

> [!NOTE]
> Intel64 아키텍처 기술인, 이전의 되었습니다 및 해당 컴파일러 옵션은 **/favor:EM64T**합니다.

X64에 대 한 프로그래밍 하는 방법에 대 한 정보에 대 한 아키텍처를 참조 하세요 [x64 소프트웨어 규칙](../x64-software-conventions.md)합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **C/c + +** 폴더입니다.

1. 선택 된 **명령줄** 속성 페이지.

1. 컴파일러 옵션을 입력 합니다 **추가 옵션** 상자입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
