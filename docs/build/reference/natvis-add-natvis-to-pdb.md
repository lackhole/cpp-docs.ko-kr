---
title: / NATVIS (PDB에 Natvis 추가)
ms.date: 08/10/2017
f1_keywords:
- /natvis
- VC.Project.VCLinkerTool.ImportLIbrary
helpviewer_keywords:
- NATVIS linker option
- /NATVIS linker option
- -NATVIS linker option
- Add Natvis file to PDB
ms.assetid: 8747fc0c-701a-4796-bb4d-818ab4465cca
ms.openlocfilehash: e758a49b41a17d805b752947cd1944087c8ff852
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809238"
---
# <a name="natvis-add-natvis-to-pdb"></a>/ NATVIS (PDB에 Natvis 추가)

> /NATVIS:*filename*

## <a name="parameters"></a>매개 변수

*filename*<br/>
PDB 파일에 추가할 Natvis 파일입니다. PDB에 Natvis 파일의 디버거 시각화 포함 합니다.

## <a name="remarks"></a>설명

/NATVIS 옵션 Natvis 파일에 정의 된 디버거 시각화를 포함 *filename* 링크에 의해 생성 된 PDB 파일에 있습니다. 따라서 디버거를.natvis 파일을 독립적으로 시각화를 표시할 수 있습니다. 생성된 된 PDB 파일에 둘 이상의 Natvis 파일을 포함 하려면 여러 /NATVIS 옵션을 사용할 수 있습니다.

PDB 파일을 사용 하 여 만들어지지 않은 경우 링크 무시 /NATVIS를 [디버그/](debug-generate-debug-info.md) 옵션입니다. .Natvis 파일의 생성 및 사용에 대 한 내용은 참조 하세요 [Visual Studio 디버거에서 네이티브 개체의 사용자 지정 뷰 만들기](/visualstudio/debugger/create-custom-views-of-native-objects)합니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **명령줄** 속성 페이지에는 **링커** 폴더.

1. /NATVIS 옵션을 추가 합니다 **추가 옵션** 입력란입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- 이 옵션에 프로그래밍 방식으로 해당 하는 없습니다.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
