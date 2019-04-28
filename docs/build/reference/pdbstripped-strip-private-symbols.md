---
title: /PDBSTRIPPED(전용 기호 제거)
ms.date: 11/04/2016
f1_keywords:
- /pdbstripped
- VC.Project.VCLinkerTool.StripPrivateSymbols
helpviewer_keywords:
- /PDBSTRIPPED linker option
- -PDBSTRIPPED linker option
- .pdb files, stripping private symbols
- PDB files, stripping private symbols
- PDBSTRIPPED linker option
ms.assetid: 9b9e0070-6a13-4142-8180-19c003fbbd55
ms.openlocfilehash: 3ed36eca727a15a3c70bc51a07cd3c143d7f66da
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320138"
---
# <a name="pdbstripped-strip-private-symbols"></a>/PDBSTRIPPED(전용 기호 제거)

```
/PDBSTRIPPED:pdb_file_name
```

## <a name="arguments"></a>인수

*pdb_file_name*<br/>
링커가 만드는 프로그램 데이터베이스 (PDB)에 대 한 사용자 지정 이름입니다.

## <a name="remarks"></a>설명

/PDBSTRIPPED 옵션 PDB 파일을 생성 하는 옵션 컴파일러 또는 링커를 사용 하 여 프로그램 이미지를 빌드하면 두 번째 프로그램 데이터베이스 (PDB) 파일을 만듭니다 ([/debug](debug-generate-debug-info.md)를 [/z7](z7-zi-zi-debug-information-format.md), /Zd 또는 /Zi). 이 두 번째 PDB 파일에서는 고객에게 제공하지 않을 기호가 생략됩니다. 두 번째 PDB 파일의 내용만 포함 됩니다.

- 공용 기호

- 개체 파일 및 제공 하는 실행 파일의 부분 목록

- 프레임 포인터 최적화 (FPO) 디버그 레코드 스택을 통과 하는 데 사용

제거 된 PDB 파일이 포함 되지 않습니다.

- 형식 정보

- 줄 번호 정보

- 로컬 함수와 정적 데이터에 대 한 것과 같은 개체당 파일 CodeView 기호

/PDBSTRIPPED를 사용 하는 경우에 여전히 전체 PDB 파일을 생성 됩니다.

PDB 파일을 만들지 /PDBSTRIPPED 무시 됩니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 클릭 합니다 **링커** 폴더입니다.

1. 클릭 합니다 **디버그** 속성 페이지.

1. 수정 된 **전용 기호 제거** 속성입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StripPrivateSymbols%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
