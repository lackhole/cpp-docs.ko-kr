---
title: /MACHINE(대상 플랫폼 지정)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.TargetMachine
- /machine
helpviewer_keywords:
- mapfiles, creating linker
- target platform
- -MACHINE linker option
- /MACHINE linker option
- MACHINE linker option
ms.assetid: 8d41bf4b-7e53-4ab9-9085-d852b08d31c2
ms.openlocfilehash: e64aa7b2ca9e50ebdc0760f64a9b25e851b45310
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818130"
---
# <a name="machine-specify-target-platform"></a>/MACHINE(대상 플랫폼 지정)

```
/MACHINE:{ARM|EBC|X64|X86}
```

## <a name="remarks"></a>설명

/MACHINE 옵션은 프로그램에 대 한 대상 플랫폼을 지정 합니다.

일반적으로 /MACHINE 옵션은 지정할 필요가 없습니다. 링크는.obj 파일에서 컴퓨터 형식을 유추합니다. 그러나 일부 경우에 링크를 확인할 수 없습니다 컴퓨터 유형 및 문제는 [링커 도구 오류 LNK1113](../../error-messages/tool-errors/linker-tools-error-lnk1113.md)합니다. 이러한 오류가 발생 하는 경우 /MACHINE를 지정 합니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 클릭 합니다 **링커** 폴더입니다.

1. 클릭 합니다 **고급** 속성 페이지.

1. 수정 된 **대상 컴퓨터** 속성입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

1. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TargetMachine%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
