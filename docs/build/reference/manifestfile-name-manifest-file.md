---
title: /MANIFESTFILE(매니페스트 파일 이름 지정)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.ManifestFile
helpviewer_keywords:
- MANIFESTFILE linker option
- -MANIFESTFILE linker option
- /MANIFESTFILE linker option
ms.assetid: befa5ab2-a9cf-4c9b-969a-e7b4a930f08d
ms.openlocfilehash: e75c6d8171aae22312ba6aaa2d4304d831ec6d0f
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57813840"
---
# <a name="manifestfile-name-manifest-file"></a>/MANIFESTFILE(매니페스트 파일 이름 지정)

```
/MANIFESTFILE:filename
```

## <a name="remarks"></a>설명

/MANIFESTFILE를 사용 하면 매니페스트 파일의 기본 이름을 변경할 수 있습니다.  매니페스트 파일의 기본 이름은 파일 이름에.manifest가 붙은입니다.

에 링크 하지 않은 경우 영향을 주지 것입니다 /MANIFESTFILE [매니페스트/](manifest-create-side-by-side-assembly-manifest.md)합니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. **구성 속성** 노드를 확장합니다.

1. 확장 된 **링커** 노드.

1. 선택 된 **매니페스트 파일** 속성 페이지.

1. 수정 된 **매니페스트 파일** 속성입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

1. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ManifestFile%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
