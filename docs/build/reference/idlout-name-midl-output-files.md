---
title: /IDLOUT(MIDL 출력 파일 이름 지정)
ms.date: 11/04/2016
f1_keywords:
- /idlout
- VC.Project.VCLinkerTool.MergedIDLBaseFileName
helpviewer_keywords:
- MIDL, output file names
- .idl files, path
- MIDL
- /IDLOUT linker option
- IDL files, path
- -IDLOUT linker option
- IDLOUT linker option
ms.assetid: 10d00a6a-85b4-4de1-8732-e422c6931509
ms.openlocfilehash: 3816bb85cb3c711075e3fefeec2d706c2f8cc2ff
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57821471"
---
# <a name="idlout-name-midl-output-files"></a>/IDLOUT(MIDL 출력 파일 이름 지정)

```
/IDLOUT:[path\]filename
```

## <a name="parameters"></a>매개 변수

*path*<br/>
절대 또는 상대 경로 지정 합니다. 경로 지정 하 여는.idl 파일의 위치만 변경 다른 모든 파일은 프로젝트 디렉터리에 배치 됩니다.

*filename*<br/>
MIDL 컴파일러에 의해 생성 된.idl 파일의 이름을 지정 합니다. 파일 확장명이 없는 것으로 간주 됩니다. 지정할 *filename*.idl.idl 확장 하려는 경우.

## <a name="remarks"></a>설명

/IDLOUT 옵션은 이름 및.idl 파일의 확장명을 지정합니다.

포함 하는 프로젝트를 연결 하는 경우 MIDL 컴파일러 MSVC 링커에 의해 라고 합니다 [모듈](../../windows/module-cpp.md) 특성입니다.

/IDLOUT은 MIDL 컴파일러와 관련 된 다른 출력 파일의 파일 이름을 지정 합니다.

- *filename*.tlb

- *filename*_p.c

- *filename*_i.c

- *filename*.h

*filename* /IDLOUT에 전달 하는 매개 변수입니다. 하는 경우 [/TLBOUT](tlbout-name-dot-tlb-file.md) 지정 된 경우.tlb 파일 이름과 /TLBOUT에서 가져오는 *filename*합니다.

/IDLOUT 아니고 /TLBOUT을 지정 하면 링커가 vc70.tlb, vc70.idl, vc70_p.c, vc70_i.c, 및 vc70.h 만듭니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 클릭 합니다 **링커** 폴더입니다.

1. 클릭 합니다 **포함 IDL** 속성 페이지.

1. 수정 된 **병합 IDL 기본 파일 이름** 속성입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergedIDLBaseFileName%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)<br/>
[/IGNOREIDL(특성을 MIDL로 처리하지 않음)](ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/MIDL(MIDL 명령줄 옵션 지정)](midl-specify-midl-command-line-options.md)<br/>
[특성을 사용하는 프로그램 빌드](../../windows/building-an-attributed-program.md)
