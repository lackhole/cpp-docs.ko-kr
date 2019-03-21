---
title: /DEBUG(디버깅 정보 생성)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.GenerateDebugInformation
- /debug
helpviewer_keywords:
- DEBUG linker option
- /DEBUG linker option
- -DEBUG linker option
- PDB files
- debugging [C++], debug information files
- generate debug info linker option
- pdb files, generating debug info
- .pdb files, generating debug info
- debugging [C++], linker option
- program databases [C++]
ms.assetid: 1af389ae-3f8b-4d76-a087-1cdf861e9103
ms.openlocfilehash: ca7ef5d1935ddea0441f49e387e35184c6fd1fc6
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810200"
---
# <a name="debug-generate-debug-info"></a>/DEBUG(디버깅 정보 생성)

```
/DEBUG[:{FASTLINK|FULL|NONE}]
```

## <a name="remarks"></a>설명

합니다 **디버그/** 옵션은 실행 파일에 대 한 디버깅 정보를 만듭니다.

링커가 디버깅 정보를 프로그램 데이터베이스 (PDB) 파일을 넣습니다. 프로그램의 후속 빌드 과정 PDB를 업데이트 합니다.

디버깅을 위해 만든 실행 파일 (.exe 파일 또는 DLL)는 해당 PDB의 경로 이름을 포함 합니다. 디버거가 포함된 된 이름을 읽고 프로그램을 디버깅할 때 PDB를 사용 합니다. 링커는 확장명이.pdb 프로그램의 기본 이름을 사용 하 여 프로그램 데이터베이스 이름을 지정 하 고 생성 된 위치 경로 포함 합니다. 이 기본값을 재정의 하려면 설정 [/PDB](pdb-use-program-database.md) 다른 파일 이름을 지정 합니다.

합니다 **/debug: fastlink** 옵션은 이상 Visual Studio 2017에서 사용할 수 있습니다. 이 옵션 실행 파일을 빌드하는 데 사용 하는 개별 컴파일 제품에 개인 기호 정보를 유지 합니다. 개체 파일 및 전체 복사본을 만들지 않고 실행 파일을 만드는 데 라이브러리의 디버그 정보를 인덱싱하는 제한 된 PDB를 생성 합니다. 이 옵션 2 ~ 4 번 전체 PDB 생성 빨리 연결할 수 있으며 사용 가능한 빌드 제품 있고 로컬로 디버깅 하는 경우 것이 좋습니다. 필요한 빌드 제품 같은 다른 컴퓨터에서 실행 파일 배포 되는 경우 사용할 수 없는 경우 디버깅에 대 한이 제한 된 PDB은 사용할 수 없습니다. 개발자 명령 프롬프트에서이 제한 된 PDB에서 전체 PDB를 생성 하려면 mspdbcmf.exe 도구를 사용할 수 있습니다. Visual Studio에서 프로젝트 또는 솔루션에 대 한 전체 PDB를 만들려면 전체 PDB 파일을 생성 하는 것에 대 한 프로젝트 또는 빌드 메뉴 항목을 사용 합니다.

합니다 **/debug: full** 옵션 PDB를 single로 개별 컴파일 제품 (개체 파일 및 라이브러리)에서 모든 개인 기호 정보를 이동 하 고 링크의 가장 시간이 많이 걸리는 일부가 될 수 있습니다. 그러나 다른 빌드 제품이 같은 실행 파일 배포 되는 경우 사용할 수 있는 경우 실행 파일을 디버깅 하려면 전체 PDB은 사용할 수 있습니다.

합니다 **/debug: NONE** 옵션 PDB를 생성 하지 않습니다.

지정 하는 경우 **/debug** 링커 기본값으로 추가 옵션 없이 **/debug: full** 빌드에 대해 명령줄 및 메이크파일 빌드 릴리스에 대 한 Visual Studio IDE에 디버그 및 릴리스 모두에 대 한 Visual Studio 2015 및 이전 버전에서 생성 됩니다. Visual Studio 2017부터, IDE에서 빌드 시스템에서 기본값으로 **/debug: fastlink** 지정 하는 경우를 **디버그/** 디버그 빌드에 대 한 옵션입니다. 이전 버전과 호환성을 유지 하기 위해 다른 기본값은 변경 되지 않았습니다.

컴파일러의 [C7 호환](z7-zi-zi-debug-information-format.md) (/ Z7) 옵션을 사용 하면.obj 파일에서 디버깅 정보를 유지 합니다. 사용할 수도 있습니다는 [프로그램 데이터베이스](z7-zi-zi-debug-information-format.md) (/Zi) 컴파일러 옵션.obj 파일에 대 한 PDB에 디버깅 정보를 저장 합니다. 링커는 개체의 PDB에 대 한 먼저.obj 파일에 작성 된 절대 경로에서 찾은 다음 디렉터리에 포함 된.obj 파일입니다. 개체의 PDB 파일 이름 또는 링커에 위치를 지정할 수 없습니다.

[/ 증분](incremental-link-incrementally.md) /DEBUG 지정 된 경우 포함 됩니다.

/ 디버그에 대 한 기본값을 변경 합니다 [/opt](opt-optimizations.md) 수에서 REF NOREF 들어오고 ICF NOICF, /opt: ref 또는 /opt: icf 명시적으로 지정 해야 원래 기본값을 사용 하도록 하려는 경우.

만드는.exe 또는.dll 디버그 정보를 포함 하는 것이 불가능 합니다. 디버그 정보는 항상.obj 또는.pdb 파일에 배치 됩니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 클릭 합니다 **링커** 폴더입니다.

1. 클릭 합니다 **디버깅** 속성 페이지.

1. 수정 된 **디버그 정보 생성** PDB 생성을 활성화 하는 속성입니다. 이렇게 하면 Visual Studio 2017에서 기본적으로 /debug: fastlink 수 있습니다.

1. 수정 합니다 **전체 프로그램 데이터베이스 파일 생성** 속성 마다 증분 빌드에 대 한 전체 PDB 생성에 대 한 /debug: full을 사용 하도록 설정 합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

1. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateDebugInformation%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
