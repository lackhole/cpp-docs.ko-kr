---
title: /FIXED(고정 기준 주소)
ms.date: 11/04/2016
f1_keywords:
- /fixed
- VC.Project.VCLinkerTool.FixedBaseAddress
helpviewer_keywords:
- preferred base address for loading program
- /FIXED linker option
- -FIXED linker option
- FIXED linker option
ms.assetid: 929bba5e-b7d8-40ed-943e-056aa3710fc5
ms.openlocfilehash: 6cc89df76e48ee258a7c6608aab12573ab11729b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811526"
---
# <a name="fixed-fixed-base-address"></a>/FIXED(고정 기준 주소)

```
/FIXED[:NO]
```

## <a name="remarks"></a>설명

운영 체제가 기본 설정된 기본 주소에서만 프로그램을 로드하도록 지정합니다. 기본 설정된 기준 주소를 사용할 수 없는 경우 운영 체제 파일을 로드 하지 않습니다. 자세한 내용은 [/BASE(기준 주소)](base-base-address.md)를 참조하세요.

/FIXED:NO는 DLL에 대한 기본 설정이며, /FIXED는 다른 프로젝트 형식에 대한 기본 설정입니다.

/FIXED를 지정 하면 링크는 프로그램에 재배치 섹션을 생성 하지 않습니다. 런타임 시 운영 체제가 지정된 주소에서 프로그램을 로드할 수 없으면, 오류 메시지를 표시하고 프로그램을 로드하지 않습니다.

프로그램에 재배치 섹션 생성 하려면 /fixed: no를 지정 합니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **링커** 폴더입니다.

1. 선택 된 **명령줄** 속성 페이지.

1. 옵션 이름을 입력 하 고 설정 합니다 **추가 옵션** 상자입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
