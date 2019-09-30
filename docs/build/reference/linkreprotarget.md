---
title: /LINKREPROTARGET (링크 재현 파일 이름)
description: 링커 또는 라이브러리 도구 옵션을 선택 하 여 링크 재현을 위한 대상 파일 이름을 설정 합니다.
ms.date: 09/24/2019
f1_keywords:
- /LINKREPROTARGET
helpviewer_keywords:
- LINKREPROTARGET linker option
- /LINKREPROTARGET linker option
- -LINKREPROTARGET linker option
- linker repro reporting
ms.openlocfilehash: 4912e8bc64d31e3ecc97ea25783c7329e7d7861c
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71686907"
---
# <a name="linkreprotarget-link-repro-file-name"></a>/LINKREPROTARGET (링크 재현 파일 이름)

대상에 지정 된 파일 이름이 있는 경우에만 링크 재현을 생성 하도록 링커 또는 라이브러리 도구에 지시 합니다.

## <a name="syntax"></a>구문

> **/LINKREPROTARGET:** _파일 이름_

### <a name="arguments"></a>인수

**/LINKREPROTARGET:** _파일 이름_\
필터링 할 대상 파일 이름입니다. 링크 재현은 명명 된 파일이 출력 대상인 경우에만 생성 됩니다. 공백을 포함 하는 파일 이름은 큰따옴표로 묶어야 합니다. 파일 이름에는 기본 이름과 확장명이 포함 되어야 하지만 경로는 포함 되지 않습니다.

## <a name="remarks"></a>설명

**/LINKREPROTARGET** 옵션은에 대 한 *링크 재현* 을 생성할 대상 파일 이름을 지정 하는 데 사용 됩니다. 링크 재현은 Microsoft에서 링크 시간에 발생 하거나 라이브러리 작업을 수행 하는 동안 발생 하는 문제를 재현할 수 있도록 하는 빌드 아티팩트의 집합입니다. 링커 또는 라이브러리 도구는 [/LINKREPRO](linkrepro.md) 옵션을 지정 하거나 명령줄 빌드 환경에서 `link_repro` 환경 변수를 설정할 때 링크 재현을 생성 합니다.

**/LINKREPROTARGET** 옵션은 링커 또는 라이브러리 도구를 두 번 이상 호출 하는 복잡 한 빌드에서 유용 합니다. 이를 통해 *문제 .dll*등의 링크 재현을 위한 특정 대상을 지정할 수 있습니다. 도구에서 특정 파일을 생성 하는 경우에만 링크 재현을 생성할 수 있습니다.

링크 재현을 만드는 방법 및 시기에 대 한 자세한 내용은 [Microsoft C++ 도구 집합의 문제를 보고 하는 방법](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md)에 대 한 자세한 [링크 링크](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md#link-repros) 를 참조 하세요.

효과를 적용 하려면 **/LINKREPROTARGET** 옵션에 대해 **/LINKREPRO** 및 [/out](out-output-file-name.md) 옵션을 설정 해야 합니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > 링커명령줄 > 속성 페이지를 선택 합니다.

1. **추가 옵션** 상자에 **/LINKREPROTARGET:** _파일 이름_ 옵션을 입력 합니다. **확인**을 선택하여 변경 내용을 적용합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참조

[MSVC 링커 참조](linking.md)\
[MSVC 링커 옵션](linker-options.md)\
[/LINKREPRO](linkrepro.md)
