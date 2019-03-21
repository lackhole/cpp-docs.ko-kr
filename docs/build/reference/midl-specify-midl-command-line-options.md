---
title: /MIDL(MIDL 명령줄 옵션 지정)
ms.date: 09/05/2018
f1_keywords:
- /midl
- VC.Project.VCLinkerTool.MidlCommandFile
helpviewer_keywords:
- -MIDL linker option
- MIDL
- /MIDL linker option
- MIDL linker option
- MIDL, command line options
ms.assetid: 22dc259e-b34c-4ed3-a380-4beb734482c1
ms.openlocfilehash: 584958ac51bdc491ad1bdd16117ecaad6e000ec7
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57814191"
---
# <a name="midl-specify-midl-command-line-options"></a>/MIDL(MIDL 명령줄 옵션 지정)

MIDL 명령줄 옵션에 대 한 지시 파일 지정

## <a name="syntax"></a>구문

> **/MIDL:\@**<em>file</em>

## <a name="arguments"></a>인수

*file*<br/>
포함 된 파일의 이름을 [MIDL 명령줄 옵션](/windows/desktop/Midl/general-midl-command-line-syntax)합니다.

## <a name="remarks"></a>설명

IDL 파일을 TLB 파일로 변환에 대 한 모든 옵션 지정 해야 합니다 *파일*; MIDL 명령줄 옵션을 링커의 명령줄에서 지정할 수 없습니다. /MIDL 지정 하지 않으면, MIDL 컴파일러 IDL 파일 이름 및 다른 옵션 없이 사용 하 여 호출 됩니다.

파일 줄당 하나의 MIDL 명령줄 옵션을 포함 해야 합니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **링커** > **포함 IDL** 속성 페이지.

1. 수정 된 **MIDL 명령** 속성입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MidlCommandFile%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)<br/>
[/IDLOUT(MIDL 출력 파일 이름 지정)](idlout-name-midl-output-files.md)<br/>
[/IGNOREIDL(특성을 MIDL로 처리하지 않음)](ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/TLBOUT(.TLB 파일 이름 지정)](tlbout-name-dot-tlb-file.md)<br/>
[특성을 사용하는 프로그램 빌드](../../windows/building-an-attributed-program.md)
