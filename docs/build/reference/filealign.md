---
title: /FILEALIGN (파일의 섹션 맞춤)
ms.date: 10/23/2017
f1_keywords:
- /filealign
helpviewer_keywords:
- linker align sections
- /FILEALIGN linker option
- -FILEALIGN linker option
- FILEALIGN linker option
ms.assetid: c1017a35-8d71-4ad9-934b-a3e3ea037fa0
ms.openlocfilehash: 43cfdd6efb163013d05877e91c8375eb592295a9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62271153"
---
# <a name="filealign-align-sections-in-files"></a>/FILEALIGN (파일의 섹션 맞춤)

합니다 **/FILEALIGN** 링커 옵션을 지정 된 크기의 배수 출력 파일에 기록 하는 섹션의 맞춤을 지정할 수 있습니다.

## <a name="syntax"></a>구문

> __/FILEALIGN:__*size*

### <a name="parameters"></a>매개 변수

*size*<br/>
섹션 맞춤 크기 바이트, 2의 거듭제곱 이어야 합니다.

## <a name="remarks"></a>설명

**/FILEALIGN** 옵션을 사용 하면 링커의 배수인 경계에 출력 파일의 각 섹션에 맞게 합니다 *크기* 값입니다. 기본적으로 링커는 고정 된 맞춤 크기를 사용 하지 않습니다.

합니다 **/FILEALIGN** 페이지를 디스크에서 빠르게 로드 또는 디스크 사용률을 더욱 효율적으로 확인 옵션을 사용할 수 있습니다. 더 작은 섹션 크기를 다운로드를 작게 유지 또는 소형 장치에서 실행 되는 앱에 대 한 유용할 수 있습니다. 섹션 맞춤 디스크에 메모리에서 맞춤 영향을 주지 않습니다.

출력 파일의 섹션에 대한 정보를 확인하려면 [DUMPBIN](dumpbin-reference.md)을 사용하세요.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 선택 된 **명령줄** 속성 페이지에는 **링커** 폴더.

1. 옵션 이름 입력 **/FILEALIGN:** 의 크기와는 **추가 옵션** 상자입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
