---
title: LIB 개요
ms.date: 11/04/2016
f1_keywords:
- Lib
helpviewer_keywords:
- LIB [C++], modes
ms.assetid: e997d423-f574-434f-8b56-25585d137ee0
ms.openlocfilehash: 97d7b8892574fbe485a8d6c5e344e4a77aaf8519
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820223"
---
# <a name="overview-of-lib"></a>LIB 개요

LIB에서 만드는 표준 라이브러리, 라이브러리, 파일 가져오기 및 내보내기에 사용할 수 [링크](linker-options.md) 는 프로그램을 빌드할 때입니다. LIB 명령 프롬프트에서 실행 됩니다.

다음과 같은 모드로 LIB를 사용할 수 있습니다.

- [빌드 또는 COFF 라이브러리 수정](managing-a-library.md)

- [멤버 개체를 파일에 추출합니다.](extracting-a-library-member.md)

- [가져오기 라이브러리 및 내보내기 파일 만들기](working-with-import-libraries-and-export-files.md)

이러한 모드는 함께 사용할 수 없습니다. LIB를 한 번에 하나의 모드 에서만 사용할 수 있습니다.

## <a name="lib-options"></a>Lib 옵션

다음 표에서 자세한 정보에 대 한 링크를 사용 하 여 lib.exe 옵션을 나열합니다.

|옵션|설명|
|-|-|
|**/DEF**|가져오기 라이브러리 및 내보내기 파일을 만듭니다.<br/><br/>자세한 내용은 참조 [가져오기 라이브러리 및 내보내기 파일 빌드](building-an-import-library-and-export-file.md)합니다.|
|**/ERRORREPORT**|   Lib.exe 사용 하 여 내부 오류에 대 한 Microsoft로 정보를 보냅니다.<br/><br/>자세한 내용은 참조 [LIB 실행](running-lib.md)합니다.|
|**/EXPORT**|   프로그램에서 함수를 내보냅니다.<br/><br/>자세한 내용은 참조 [가져오기 라이브러리 및 내보내기 파일 빌드](building-an-import-library-and-export-file.md)합니다.|
|**/EXTRACT**|   기존 라이브러리 멤버의 복사본을 포함 하는 개체 (.obj) 파일을 만듭니다.<br/><br/>자세한 내용은 참조 [라이브러리 멤버 추출](extracting-a-library-member.md)합니다.|
|**/INCLUDE**|   기호를 기호 테이블에 추가합니다.<br/><br/>자세한 내용은 참조 [가져오기 라이브러리 및 내보내기 파일 빌드](building-an-import-library-and-export-file.md)합니다.|
|**/LIBPATH**|   환경 라이브러리 경로를 재정의합니다.<br/><br/>자세한 내용은 참조 [라이브러리 관리](managing-a-library.md)합니다.|
|**/LIST**|   표준 출력으로 출력 라이브러리에 대 한 정보를 표시합니다.<br/><br/>자세한 내용은 참조 [라이브러리 관리](managing-a-library.md)합니다.|
|**/LTCG**|   링크 타임 코드 생성을 사용 하 여 빌드될 라이브러리를 하면 됩니다.<br/><br/>자세한 내용은 참조 [LIB 실행](running-lib.md)합니다.|
|**/MACHINE**|   프로그램에 대 한 대상 플랫폼을 지정합니다.<br/><br/>자세한 내용은 참조 [LIB 실행](running-lib.md)합니다.|
|**/NAME**|   가져오기 라이브러리를 빌드할 때 작성 중인 가져오기 라이브러리 DLL의 이름을 지정 합니다.<br/><br/>자세한 내용은 참조 [라이브러리 관리](managing-a-library.md)합니다.|
|**/NODEFAULTLIB**|   외부 참조를 확인할 때 검색 하는 라이브러리 목록에서 하나 이상의 기본 라이브러리를 제거 합니다.<br/><br/>자세한 내용은 참조 [라이브러리 관리](managing-a-library.md)합니다.|
|**/NOLOGO**|   LIB 저작권 메시지 및 버전 번호를 표시 하지 않습니다 하 고 명령 파일의 에코를 방지 합니다.<br/><br/>자세한 내용은 참조 [LIB 실행](running-lib.md)합니다.|
|**/OUT**|   기본 출력 파일 이름을 재정의합니다.<br/><br/>자세한 내용은 참조 [라이브러리 관리](managing-a-library.md)합니다.|
|**/REMOVE**|   출력 라이브러리에서 개체를 제거 합니다.<br/><br/>자세한 내용은 참조 [라이브러리 관리](managing-a-library.md)합니다.|
|**/SUBSYSTEM**|   운영 시스템에 연결 하 여 출력 라이브러리를 생성 하는 프로그램을 실행 하는 방법을 알려줍니다.<br/><br/>자세한 내용은 참조 [라이브러리 관리](managing-a-library.md)합니다.|
|**/VERBOSE**|   추가 하려는.obj 파일의 이름을 비롯 하 여 세션의 진행률에 대 한 세부 정보를 표시 합니다.<br/><br/>자세한 내용은 참조 [LIB 실행](running-lib.md)합니다.|
|**/WX**|   경고를 오류로 처리 합니다.<br/><br/>자세한 내용은 참조 [LIB 실행](running-lib.md)합니다.|

## <a name="see-also"></a>참고자료

[LIB 참조](lib-reference.md)<br/>
[LIB 입력 파일](lib-input-files.md)<br/>
[LIB 출력 파일](lib-output-files.md)<br/>
[기타 LIB 출력](other-lib-output.md)<br/>
[라이브러리 구조](structure-of-a-library.md)
