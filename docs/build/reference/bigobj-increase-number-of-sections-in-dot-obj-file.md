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

**/bigobj**는 개체 파일에 포함할 수 있는 섹션의 수를 늘립니다.

## <a name="syntax"></a>구문

> **/bigobj**

## <a name="remarks"></a>설명

오브젝트 파일은 기본적으로 최대 65,279개(약 2^16)의 주소 지정 가능 섹션을 보유할 수 있습니다. 이 제한은 지정된 대상 플랫폼에 관계없이 적용됩니다. **/bigobj**는 주쇼용량을 4,294,967,296(2^32)으로 늘립니다.

대부분의 모듈은 65,279개 이상의 섹션을 포함하는.obj 파일을 생성 하지 않습니다. 그러나 시스템에서 생성된 코드나 템플릿 라이브러리를 많이 사용하는 코드는 더 많은 섹션을 포함할 수 있는.obj 파일이 필요할 수 있습니다. **/bigobj**는 시스템에서 생성된 XAML 코드에 대량의 헤더가 포함되어 있으므로 유니버설 Windows 플랫폼(UWP) 프로젝트에서 기본적으로 사용됩니다. UWP 앱 프로젝트에서 이 옵션을 사용하지 않으면 코드 컴파일시 컴파일러가 C1128 오류를 생성할 수 있습니다.

PE-COFF 개체 파일형식에 대한 자세한 내용은 Windows 설명서의 [PE 형식](/windows/desktop/debug/pe-format)을 참조하세요.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화상자를 엽니다. 자세한 내용은 [컴파일러 설정 및 빌드 속성](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++** > **명령줄** 속성 페이지를 선택합니다.

1. **추가 옵션** 상자에 **/bigobj** 컴파일러 옵션을 입력하세요.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
