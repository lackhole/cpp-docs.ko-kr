---
title: /bigobj(.Obj 파일의 섹션 수 늘리기)
ms.date: 11/04/2016
f1_keywords:
- /bigobj
helpviewer_keywords:
- -bigobj compiler option [C++]
- /bigobj compiler option [C++]
- bigobj compiler option [C++]
ms.assetid: ba94d602-4015-4a8d-86ec-49241ab74c12
ms.openlocfilehash: a9685834fc3e1de246c9d9d60d206538b744ce3e
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809862"
---
# <a name="bigobj-increase-number-of-sections-in-obj-file"></a>/bigobj(.Obj 파일의 섹션 수 늘리기)

**/bigobj** 개체 파일을 포함할 수 있는 섹션의 수를 늘립니다.

## <a name="syntax"></a>구문

```
/bigobj
```

## <a name="remarks"></a>설명

기본적으로 개체 파일에는 최대 65,536 보유할 수 (2^16) 주소 지정 가능 섹션입니다. 지정된 대상 플랫폼과는 관계가 없습니다. **/bigobj** 4,294,967,296 주소 용량을 증가 (2^32).

대부분의 모듈 65,536 개 섹션을 포함 하는.obj 파일을 생성 하지 않습니다. 그러나 생성 된 코드, 컴퓨터 또는 템플릿 라이브러리를 많이 사용 하는 코드를 더 많은 섹션을 보유할 수 있는.obj 파일에 필요할 수 있습니다. **/bigobj** 시스템에서 생성 된 XAML 코드에 대량의 헤더가 포함 되어 있으므로 유니버설 Windows 플랫폼 (UWP) 프로젝트에서 기본적으로 사용 됩니다. UWP 앱 프로젝트에서이 옵션을 사용 하지 않도록 설정 하는 경우 컴파일러 오류 C1128이 발생할 가능성이 있습니다.

Visual C++ 2005 이전에 제공 되는 링커는 사용 하 여 생성 된.obj 파일을 읽을 수 없습니다 **/bigobj**합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. **C/C++** 폴더를 클릭합니다.

1. **명령줄** 속성 페이지를 클릭합니다.

1. **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
