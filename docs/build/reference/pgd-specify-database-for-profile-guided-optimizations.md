---
title: /PGD(프로필 기반 최적화를 위한 데이터베이스 지정)
ms.date: 03/14/2018
f1_keywords:
- VC.Project.VCLinkerTool.ProfileGuidedDatabase
helpviewer_keywords:
- -PGD linker option
- /PGD linker option
ms.assetid: 9f312498-493b-461f-886f-92652257e443
ms.openlocfilehash: e1d7c9fcb94a9351ce94b66e04b4bfc523248f4e
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812202"
---
# <a name="pgd-specify-database-for-profile-guided-optimizations"></a>/PGD(프로필 기반 최적화를 위한 데이터베이스 지정)

**/PGD 옵션을 사용 하는 사용 되지 않습니다.** Visual Studio 2015부터 선호 합니다 [/GENPROFILE 또는 /FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) 링커 옵션을 대신 합니다. 프로필 기반 최적화 프로세스에서 사용 하 여.pgd 파일의 이름을 지정 하려면이 옵션은 사용 됩니다.

## <a name="syntax"></a>구문

> **/PGD:**_filename_

## <a name="argument"></a>인수

*filename*<br/>
실행 중인 프로그램에 대 한 정보를 저장 하는 데 사용 되는.pgd 파일의 이름을 지정 합니다.

## <a name="remarks"></a>설명

사용 되지 않는 경우 [/ltcg: pginstrument](ltcg-link-time-code-generation.md) 옵션을 사용 하 여 **/PGD** 기본 디렉터리가 아닌 다른 이름 또는.pgd 파일의 위치를 지정 합니다. 지정 하지 않는 경우 **/PGD**,.pgd 파일 기본 이름 출력 파일 (.exe 또는.dll) 기본 이름을 동일 하 고 링크를 호출한 동일한 디렉터리에 만들어집니다.

사용 되지 않는 경우 **/ltcg: pgoptimize** 옵션을 사용 합니다 **/PGD** 최적화 된 이미지를 만드는 데.pgd 파일의 이름을 지정 하는 옵션입니다. *filename* 인수가 일치 해야 합니다 *filename* 에 지정 된 **/ltcg: pginstrument**합니다.

자세한 내용은 [프로필 기반 최적화](../profile-guided-optimizations.md)합니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **링커** > **최적화** 속성 페이지.

1. 수정 된 **프로필 기반 데이터베이스** 속성입니다. **확인**을 선택하여 변경 내용을 저장합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

1. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProfileGuidedDatabase%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)<br/>
