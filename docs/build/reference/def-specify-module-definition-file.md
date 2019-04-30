---
title: /DEF(모듈 정의 파일 지정)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.ModuleDefinitionFile
- /def
helpviewer_keywords:
- module definition files, specifying
- DEF linker option
- -DEF linker option
- module definition files
- /DEF linker option
ms.assetid: 6497fa68-65f0-48ca-8f66-b87166fc631a
ms.openlocfilehash: c08412fb50835485e7941b2bb1db088943387b71
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272310"
---
# <a name="def-specify-module-definition-file"></a>/DEF(모듈 정의 파일 지정)

```
/DEF:filename
```

## <a name="arguments"></a>인수

*filename*<br/>
모듈 정의 파일 (.def)을 링커에 전달할의 이름입니다.

## <a name="remarks"></a>설명

/DEF 옵션으로 모듈 정의 파일 (.def)을 링커에 전달 합니다. .Def 파일 하나만 링크를 지정할 수 있습니다. .Def 파일에 대 한 자세한 내용은 참조 하세요 [모듈 정의 파일](module-definition-dot-def-files.md)합니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 클릭 합니다 **링커** 폴더입니다.

1. 클릭 합니다 **입력** 속성 페이지.

1. 수정 된 **모듈 정의 파일** 속성입니다.

개발 환경 내에서.def 파일을 지정 하려면 다른 파일과 함께 프로젝트에 추가 하 고 /DEF 옵션으로 파일을 지정 해야 합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ModuleDefinitionFile%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
