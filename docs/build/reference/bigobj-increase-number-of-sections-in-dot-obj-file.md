---
title: /bigobj(.Obj 파일의 섹션 수 늘리기)
ms.date: 03/26/2019
f1_keywords:
- /bigobj
helpviewer_keywords:
- -bigobj compiler option [C++]
- /bigobj compiler option [C++]
- bigobj compiler option [C++]
ms.assetid: ba94d602-4015-4a8d-86ec-49241ab74c12
ms.openlocfilehash: 46399dc0c1ff552b4fc963b686ac6aa6df8b6f71
ms.sourcegitcommit: 06fc71a46e3c4f6202a1c0bc604aa40611f50d36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2019
ms.locfileid: "58508717"
---
# <a name="bigobj-increase-number-of-sections-in-obj-file"></a>/bigobj(.Obj 파일의 섹션 수 늘리기)

**/bigobj** 개체 파일을 포함할 수 있는 섹션의 수를 늘립니다.

## <a name="syntax"></a>구문

> **/bigobj**

## <a name="remarks"></a>설명

개체 파일을 기본적으로 최대 65,279를 포함할 수 있습니다 (거의 2 ^16) 주소 지정 가능 섹션입니다. 이 제한은 플랫폼은 지정 된 대상에 관계 없이 적용 됩니다. **/bigobj** 4,294,967,296 주소 용량을 증가 (2^32).

대부분의 모듈 65279 섹션을 포함 하는.obj 파일을 생성 하지 않습니다. 그러나 컴퓨터에서 생성 된 코드 또는 템플릿 라이브러리를 많이 사용 하는 코드에서 더 많은 섹션을 보유할 수 있는.obj 파일 필요할 수 있습니다. **/bigobj** 시스템에서 생성 된 XAML 코드에 대량의 헤더가 포함 되어 있으므로 유니버설 Windows 플랫폼 (UWP) 프로젝트에서 기본적으로 사용 됩니다. UWP 앱 프로젝트에서이 옵션을 사용 하지 않으면 코드는 컴파일러 오류 C1128를 생성할 수 있습니다.

PE-COFF 개체 파일 형식에 대 한 자세한 내용은 [PE 형식](/windows/desktop/debug/pe-format) Windows 설명서에서.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 C++ 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **C/c + +** > **명령줄** 속성 페이지.

1. 입력 된 **/bigobj** 컴파일러 옵션을 **추가 옵션** 상자.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
