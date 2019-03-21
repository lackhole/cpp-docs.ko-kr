---
title: 라이브러리 관리
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLibrarianTool.OVERWRITEAllDefaultLibraries
- VC.Project.VCLibrarianTool.AdditionalDependencies
- VC.Project.VCLibrarianTool.RemoveObjects
- VC.Project.VCLibrarianTool.LibraryPaths
- VC.Project.VCLibrarianTool.OutputFile
- VC.Project.VCLibrarianTool.OVERWRITEDefaultLibraryNames
- VC.Project.VCLibrarianTool.AdditionalLibraryDirectories
- VC.Project.VCLibrarianTool.ListContentsFile
- VC.Project.VCLibrarianTool.ListContents
- VC.Project.VCLibrarianTool.SubSystemVersion
- VC.Project.VCLibrarianTool.OVERWRITEDefaultLibraryName
- VC.Project.VCLibrarianTool.SubSystem
helpviewer_keywords:
- /LIBPATH library manager option
- OUT library manager option
- CONVERT library manager option
- LIBPATH library manager option
- /LIST library manager option
- object files, building and modifying
- -LINK50COMPAT library manager option
- REMOVE library manager option
- SUBSYSTEM library manager option
- /LINK50COMPAT library manager option
- /OUT library manager option
- LIB [C++], managing COFF libraries
- -CONVERT library manager option
- LINK50COMPAT library manager option
- -OUT library manager option
- -REMOVE library manager option
- -LIST library manager option
- /SUBSYSTEM library manager option
- -SUBSYSTEM library manager option
- /REMOVE library manager option
- -LIBPATH library manager option
- object files
- LIST library manager option
- /CONVERT library manager option
ms.assetid: f56a8b85-fbdc-4c09-8d8e-00f0ffe1da53
ms.openlocfilehash: 74b8cf198d46f83de327c68ac5f883bd75e5db80
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812046"
---
# <a name="managing-a-library"></a>라이브러리 관리

LIB에 대 한 기본 모드를 빌드하거나 COFF 개체의 라이브러리를 수정 하는 합니다. LIB은 /EXTRACT (개체를 복사할 파일) 또는 /DEF (가져오기 라이브러리를 빌드)를 지정 하지 않은 경우이 모드에서 실행 됩니다.

개체 및/또는 라이브러리에서 라이브러리를 작성 하려면 다음 구문을 사용 합니다.

```
LIB [options...] files...
```

이 명령은 하나 이상의 입력에서 라이브러리를 만듭니다 *파일*합니다. 합니다 *파일* COFF 개체 파일, 32 비트 OMF 개체 파일 또는 기존 COFF 라이브러리 일 수 있습니다. LIB 지정된 된 파일의 모든 개체를 포함 하는 하나의 라이브러리를 만듭니다. 입력된 파일은 32 비트 OMF 개체 파일, 라이브러리는 라이브러리를 빌드하기 전에 COFF로 변환 합니다. LIB은 LIB 16 비트 버전에서 만든 라이브러리에는 32 비트 OMF 개체를 수락할 수 없습니다. 개체를 추출 하는 16 비트 LIB를 먼저 사용 해야 32 비트 LIB 입력으로 추출 된 개체 파일을 사용할 수 있습니다.

LIB 기본적으로 첫 번째 개체 또는 라이브러리 파일 및 확장의 기본 이름을 사용 하 여 출력 파일의 이름을 지정 합니다. lib 합니다. 출력 파일은 현재 디렉터리에 저장 됩니다. 동일한 이름의 파일이 이미 있는 경우 출력 파일을 기존 파일을 대체 합니다. 기존 라이브러리를 유지 하려면 /OUT 옵션을 사용 하 여 출력 파일의 이름을 지정 합니다.

다음 옵션을 빌드하고 라이브러리 수정에 적용 됩니다.

**/LIBPATH:** *dir*<br/>
환경 라이브러리 경로를 재정의합니다. 자세한 내용은 링크에 대 한 설명을 참조 하세요 [/LIBPATH](libpath-additional-libpath.md) 옵션입니다.

**/LIST**<br/>
표준 출력으로 출력 라이브러리에 대 한 정보를 표시합니다. 출력을 파일로 리디렉션할 수 있습니다. /LIST을 사용 하 여 수정 하지 않고 기존 라이브러리의 콘텐츠를 결정할 수 있습니다.

**/NAME:** *filename*<br/>
가져오기 라이브러리를 빌드할 때 작성 중인 가져오기 라이브러리 DLL의 이름을 지정 합니다.

**/NODEFAULTLIB**<br/>
외부 참조를 확인할 때 검색 하는 라이브러리 목록에서 하나 이상의 기본 라이브러리를 제거 합니다. 참조 [/NODEFAULTLIB](nodefaultlib-ignore-libraries.md) 자세한 내용은 합니다.

**/OUT:** *filename*<br/>
기본 출력 파일 이름을 재정의합니다. 기본적으로 출력 라이브러리, 명령줄 및 확장에서 첫 번째 라이브러리 또는 개체 파일의 기본 이름 사용 하 여 현재 디렉터리에 만들어집니다. lib 합니다.

**/ 제거:** *개체*<br/>
지정 된 생략 *개체* 출력 라이브러리에서. LIB 모든 개체 (개체 파일 또는 라이브러리)를 결합 하 고 다음 /REMOVE로 지정 된 개체를 삭제 하 여 출력 라이브러리를 만듭니다.

**/ 하위 시스템:**{0}**콘솔** &AMP;#124; **EFI_APPLICATION** &AMP;#124; **EFI_BOOT_SERVICE_DRIVER** &AMP;#124; **EFI_ROM** &AMP;#124; **EFI_RUNTIME_DRIVER** &AMP;#124; **네이티브** &AMP;#124; **POSIX** &AMP;#124; **WINDOWS** &AMP;#124; **WINDOWSCE**} [, #[. # #]]<br/>
운영 시스템에 연결 하 여 출력 라이브러리를 생성 하는 프로그램을 실행 하는 방법을 알려줍니다. 자세한 내용은 링크에 대 한 설명을 참조 하세요 [/SUBSYSTEM](subsystem-specify-subsystem.md) 옵션입니다.

LIB 옵션이 명령줄에서 지정 된 대/소문자 구분 하지 않습니다.

다음 라이브러리 관리 작업을 수행 하려면 라이브러리를 사용할 수 있습니다.

- 개체에는 라이브러리를 추가 하려면 기존 라이브러리에 대 한 파일 이름 및 새 개체에 대 한 파일 이름을 지정 합니다.

- 라이브러리를 결합 하려면 라이브러리 파일 이름을 지정 합니다. 개체를 추가 하 고 단일 LIB 명령을 사용 하 여 라이브러리를 결합할 수 있습니다.

- 새 개체를 사용 하 여 라이브러리 멤버를 바꾸려면 바꿀 멤버 개체를 포함 하는 라이브러리 및 새 개체 (또는 포함 된 라이브러리)에 대 한 파일 이름을 지정 합니다. 둘 이상의 입력된 파일에 동일한 이름을 가진 개체가 있으면 LIB 출력 라이브러리에는 LIB 명령에 지정 된 마지막 개체를 배치 합니다. 라이브러리 멤버를 대체 하는 경우에 이전 개체를 포함 하는 라이브러리 후 새 개체 또는 라이브러리를 지정 해야 합니다.

- 라이브러리에서 멤버를 삭제 하려면 /REMOVE 옵션을 사용 합니다. LIB 명령줄 순서에 관계 없이 모든 입력된 개체를 결합 한 후 /REMOVE의 사양을 처리 합니다.

> [!NOTE]
>  멤버 삭제와 같은 단계에서 파일로 추출할 수 없습니다. 먼저 /EXTRACT을 사용 하는 멤버 개체를 추출 하 다음 LIB /REMOVE를 사용 하 여 다시 실행 해야 합니다. 이 동작은 다른 Microsoft 제품에 제공 된 (OMF 라이브러리)에 대 한 16 비트 LIB의 다릅니다.

## <a name="see-also"></a>참고자료

[LIB 참조](lib-reference.md)
