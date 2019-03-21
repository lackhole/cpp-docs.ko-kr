---
title: /TLBOUT(.TLB 파일 이름 지정)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.TypeLibraryFile
- /tlbout
helpviewer_keywords:
- tlb files, renaming
- TLBOUT linker option
- /TLBOUT linker option
- .tlb files, renaming
- -TLBOUT linker option
ms.assetid: 0df6d078-2e48-46c9-a1a5-02674d85dce8
ms.openlocfilehash: 4e04514933a521bbf9d927fa6b47bacb87896353
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822264"
---
# <a name="tlbout-name-tlb-file"></a>/TLBOUT(.TLB 파일 이름 지정)

```
/TLBOUT:[path\]filename
```

## <a name="arguments"></a>인수

*path*<br/>
.Tlb 파일을 만들 위치를 절대 또는 상대 경로 지정입니다.

*filename*<br/>
MIDL 컴파일러에 의해 생성 된.tlb 파일의 이름을 지정 합니다. 파일 확장명이 없는 것으로 간주 됩니다. 지정할 *filename*.tlb.tlb 확장 하려는 경우.

## <a name="remarks"></a>설명

/TLBOUT 옵션은 이름 및.tlb 파일의 확장명을 지정합니다.

포함 하는 프로젝트를 연결 하는 경우 MIDL 컴파일러 MSVC 링커에 의해 라고 합니다 [모듈](../../windows/module-cpp.md) 특성입니다.

/TLBOUT을 지정 하지 않은 경우.tlb 파일에서 해당 이름을 받습니다 [/IDLOUT](idlout-name-midl-output-files.md) *filename*합니다. /IDLOUT 지정 하지 않으면.tlb 파일 vc70.tlb을 호출 됩니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 클릭 합니다 **링커** 폴더입니다.

1. 클릭 합니다 **포함 IDL** 속성 페이지.

1. 수정 된 **형식 라이브러리** 속성입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

1. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryFile%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)<br/>
[/IGNOREIDL(특성을 MIDL로 처리하지 않음)](ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/MIDL(MIDL 명령줄 옵션 지정)](midl-specify-midl-command-line-options.md)<br/>
[특성을 사용하는 프로그램 빌드](../../windows/building-an-attributed-program.md)
