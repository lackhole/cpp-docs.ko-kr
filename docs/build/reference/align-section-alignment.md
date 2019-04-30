---
title: /ALIGN(섹션 맞춤)
ms.date: 12/29/2017
f1_keywords:
- VC.Project.VCLinkerTool.Alignment
- /align
helpviewer_keywords:
- sections, specifying alignment
- ALIGN linker option
- /ALIGN linker option
- -ALIGN linker option
- section alignment
- sections
ms.openlocfilehash: d8d2e6a859c68af473d49dc04b76f0a15056aa56
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295268"
---
# <a name="align-section-alignment"></a>/ALIGN(섹션 맞춤)

## <a name="syntax"></a>구문

> **/ALIGN**[**:**_number_]

### <a name="arguments"></a>인수

*number*<br/>
바이트 맞춤 값입니다.

## <a name="remarks"></a>설명

합니다 **/align** 옵션 프로그램의 선형 주소 공간 내에서 각 섹션의 맞춤을 지정 합니다. 합니다 *번호* 인수 (바이트)에서 이며 2의 거듭제곱 이어야 합니다. 기본값은 4k 4096입니다. 맞춤을 잘못 된 이미지를 생성 하는 경우 링커는 경고가 발생 합니다.

장치 드라이버 등의 응용 프로그램을 작성 하는 경우가 아니면 맞춤을 수정 하지 않아도 됩니다.

맞춤 매개 변수를 사용 하 여 특정 섹션의 맞춤을 수정 하는 것이 가능 합니다 [/section](section-specify-section-attributes.md) 옵션.

지정 된 맞춤 값은 최대 섹션 맞춤 보다 작을 수 없습니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 선택 된 **구성 속성** > **링커** > **명령줄** 속성 페이지.

1. 옵션을 입력 합니다 **추가 옵션** 상자입니다. 선택 **확인** 하거나 **적용** 에 변경 내용을 적용 합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
