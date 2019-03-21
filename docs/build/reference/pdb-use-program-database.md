---
title: /PDB(프로그램 데이터베이스 사용)
ms.date: 11/04/2016
f1_keywords:
- /pdb
- VC.Project.VCLinkerTool.ProgramDatabaseFile
helpviewer_keywords:
- -PDB linker option
- /PDB linker option
- PDB linker option
- PDB files, creating
- .pdb files, creating
ms.assetid: d23db0ce-10cb-427a-bc60-d6b2a852723d
ms.openlocfilehash: ddcf83cafd5f499158f3116f04e40397b7f8d0a8
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57821510"
---
# <a name="pdb-use-program-database"></a>/PDB(프로그램 데이터베이스 사용)

```
/PDB:filename
```

## <a name="arguments"></a>인수

*filename*<br/>
링커가 만드는 프로그램 데이터베이스 (PDB)에 대 한 사용자 지정 이름입니다. 기본 이름을 대체합니다.

## <a name="remarks"></a>설명

기본적으로 때 [디버그/](debug-generate-debug-info.md) 를 지정 하면 링커가 디버깅 정보를 보유 하는 프로그램 데이터베이스 (PDB)를 만듭니다. PDB에 대 한 기본 파일 이름은 확장명이.pdb 프로그램의 기본 이름이 있습니다.

/PDB 사용:*filename* PDB 파일의 이름을 지정 합니다. /DEBUG을 지정 하지 않은 경우 /PDB 옵션은 무시 됩니다.

PDB 파일에는 최대 2gb까지 첨부 파일 수 있습니다.

자세한 내용은 [링커 입력 파일로.pdb 파일](dot-pdb-files-as-linker-input.md)합니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 클릭 합니다 **링커** 폴더입니다.

1. 클릭 합니다 **디버그** 속성 페이지.

1. 수정 된 **프로그램 데이터베이스 파일 생성** 속성입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProgramDatabaseFile%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
