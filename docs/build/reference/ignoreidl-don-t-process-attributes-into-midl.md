---
title: /IGNOREIDL (Don&#39;t 프로세스 특성을 MIDL로)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.IgnoreEmbeddedIDL
- /ignoreidl
helpviewer_keywords:
- IGNOREIDL linker option
- -IGNOREIDL linker option
- /IGNOREIDL linker option
ms.assetid: 29514098-6a1c-4317-af2f-1dc268972780
ms.openlocfilehash: 210778adecd87ffdd5f2702c10106f12bd5a1b79
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291681"
---
# <a name="ignoreidl-don39t-process-attributes-into-midl"></a>/IGNOREIDL (Don&#39;t 프로세스 특성을 MIDL로)

```
/IGNOREIDL
```

## <a name="remarks"></a>설명

/IGNOREIDL 옵션 지정 [IDL 특성](../../windows/idl-attributes.md) 원본.idl 파일 코드 처리 되지 않도록 합니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 클릭 합니다 **링커** 폴더입니다.

1. 클릭 합니다 **포함 IDL** 속성 페이지.

1. 수정 된 **포함 IDL 무시** 속성입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreEmbeddedIDL%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)<br/>
[/IDLOUT(MIDL 출력 파일 이름 지정)](idlout-name-midl-output-files.md)<br/>
[/TLBOUT(.TLB 파일 이름 지정)](tlbout-name-dot-tlb-file.md)<br/>
[/MIDL(MIDL 명령줄 옵션 지정)](midl-specify-midl-command-line-options.md)<br/>
[특성을 사용하는 프로그램 빌드](../../windows/building-an-attributed-program.md)
