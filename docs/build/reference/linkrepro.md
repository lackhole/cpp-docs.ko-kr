---
title: /LINKREPRO (링크 재현 디렉터리 이름)
description: 링크 재현을 위한 디렉터리를 설정 하는 링커 또는 라이브러리 도구 옵션입니다.
ms.date: 09/24/2019
f1_keywords:
- /LINKREPRO
helpviewer_keywords:
- LINKREPRO linker option
- /LINKREPRO linker option
- -LINKREPRO linker option
- linker repro reporting
ms.openlocfilehash: d81fb529cdbb0741c6dff58032dad97df89b4d4f
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71686919"
---
# <a name="linkrepro-link-repro-directory-name"></a>/LINKREPRO (링크 재현 디렉터리 이름)

지정 된 디렉터리에서 링크 재현을 생성 하도록 링커 또는 라이브러리 도구에 지시 합니다.

## <a name="syntax"></a>구문

> **/LINKREPRO:** _디렉터리 이름_

### <a name="arguments"></a>인수

**/LINKREPRO:** _directory-이름_\
링크 재현을 저장할 사용자 지정 디렉터리입니다. 공백을 포함 하는 디렉터리 이름은 큰따옴표로 묶어야 합니다.

## <a name="remarks"></a>설명

**/LINKREPRO** 옵션은 *링크 재현*을 만드는 데 사용 됩니다. Microsoft에서 링크 타임에 발생 하거나 라이브러리 작업을 수행 하는 동안 발생 하는 문제를 재현할 수 있도록 하는 빌드 아티팩트의 집합입니다. LTCG (링크 타임 코드 생성), LNK1000 링커 오류 또는 링커 충돌과 관련 된 백엔드 충돌 등의 문제에 유용 합니다. **/LINKREPRO** 링커 옵션을 지정 하거나 명령줄 빌드 환경에서 `link_repro` 환경 변수를 설정 하는 경우이 도구는 링크 재현을 생성 합니다. 자세한 내용은 [Microsoft C++ 도구 집합의 문제를 보고 하는 방법](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md)에 대 한 다시 [전문가 링크](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md#link-repros) 섹션을 참조 하십시오.

**/LINKREPRO** 링커 옵션과 @no__t 1 환경 변수 모두 링크 재현을 위한 출력 디렉터리를 지정 해야 합니다. 명령줄 또는 IDE에서 **/LINKREPRO:** _directory-name_ 옵션을 사용 하 여 디렉터리를 지정 합니다. 지정 하는 _디렉터리 이름은_ 절대 경로 또는 상대 경로일 수 있지만 디렉터리가 있어야 합니다. 명령줄 옵션은 `link_repro` 환경 변수에 설정 된 모든 디렉터리 값을 재정의 합니다.

링크 재현 생성을 특정 대상 파일 이름으로 제한 하는 방법에 대 한 자세한 내용은 [/LINKREPROTARGET](linkreprotarget.md) 옵션을 참조 하세요. 이 옵션은에 대 한 링크 재현을 생성할 특정 대상을 지정 하는 데 사용할 수 있습니다. 링커 또는 라이브러리 도구를 두 번 이상 호출 하는 복잡 한 빌드에서 유용 합니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > 링커명령줄 > 속성 페이지를 선택 합니다.

1. **추가 옵션** 상자에 **/LINKREPRO:** _directory-name_ 옵션을 입력 합니다. 사용자가 지정 하는 _디렉터리 이름_ 값이 있어야 합니다. **확인**을 선택하여 변경 내용을 적용합니다.

링크 재현을 생성 한 후에는이 속성 페이지를 다시 열어 빌드에서 **/LINKREPRO** 옵션을 제거 합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참조

[MSVC 링커 참조](linking.md)\
[MSVC 링커 옵션](linker-options.md)\
[/LINKREPROTARGET](linkreprotarget.md)
