---
title: LIB 실행
ms.date: 09/28/2018
f1_keywords:
- VC.Project.VCLibrarianTool.TargetMachine
- Lib
- VC.Project.VCLibrarianTool.PrintProgress
- VC.Project.VCLibrarianTool.SuppressStartupBanner
helpviewer_keywords:
- -MACHINE target platform option
- command files, LIB
- MACHINE target platform option
- colon command files
- VERBOSE library manager option
- /NOLOGO library manager option
- dash option specifier
- /MACHINE target platform option
- forward slash option specifier
- -NOLOGO library manager option
- LIB [C++], running LIB
- -VERBOSE library manager option
- /VERBOSE library manager option
- command files
- NOLOGO library manager option
- slash (/)
- semicolon, command files
- / command files
ms.assetid: d54f5c81-7147-4b2c-a8db-68ce6eb1eabd
ms.openlocfilehash: e95427b571cd14ad39a7ba4f368b90e806f13862
ms.sourcegitcommit: faa42c8a051e746d99dcebe70fd4bbaf3b023ace
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2019
ms.locfileid: "57820366"
---
# <a name="running-lib"></a>LIB 실행

LIB 컨트롤에 다양 한 명령줄 옵션을 사용할 수 있습니다.

## <a name="lib-command-line"></a>LIB 명령줄

LIB를 실행 하려면 명령을 입력 하 여 `lib` 옵션 및 작업에 대 한 파일 이름 뒤에 사용 하 여 LIB 수행 합니다. LIB는 또한 다음 섹션에서 설명 하는 명령 파일에서 명령줄 입력을 허용 합니다. LIB 환경 변수를 사용 하지 않습니다.

> [!NOTE]
> LINK32.exe 하는 데 익숙한 및 LIB32.exe 도구와 Microsoft Win32 소프트웨어 개발 키트에 대 한 Windows NT, 수를 사용한 두 명령을 제공 하는 경우 `link32 -lib` 명령 또는 `lib32` 라이브러리를 관리 하 고 만들기 위한 라이브러리를 가져옵니다. 사용 하려면 메이크파일 및 일괄 처리 파일을 변경 해야 합니다 `lib` 명령을 사용 합니다.

## <a name="lib-command-files"></a>LIB 명령 파일

다음 구문을 사용 하 여 명령 파일의 lib 명령줄 인수를 전달할 수 있습니다.

> **LIB \@**<em>commandfile</em>

파일 *commandfile* 텍스트 파일입니다. 없는 공백 또는 탭 간 허용 되는 at 기호 (**\@**) 및 파일 이름입니다. 기본 확장명이 없습니다. 모든 확장을 포함 하 여 전체 파일 이름을 지정 해야 합니다. 와일드 카드를 사용할 수 없습니다. 파일 이름의 절대 또는 상대 경로 지정할 수 있습니다.

명령 파일의 인수 구분할 수 있습니다 공백이 나 탭 하 여 명령줄에서 최대한 줄 바꿈 문자로 구분 될 수도 있습니다. 세미콜론을 사용 하 여 (**;**) 주석을 표시 합니다. LIB 줄의 끝에 세미콜론에서 모든 텍스트를 무시합니다.

명령 파일의 전체 또는 명령줄의 일부를 지정할 수 있습니다 및 LIB 명령에 둘 이상의 명령 파일을 사용할 수 있습니다. LIB 마치 명령줄에서 해당 위치에서 지정한 것 처럼 명령 파일 입력을 허용 합니다. 명령 파일을 중첩할 수 없습니다. LIB은 /NOLOGO 옵션을 사용 하지 않으면 명령 파일의 내용을 에코 합니다.

## <a name="using-lib-options"></a>LIB 옵션을 사용 하 여

옵션 중 하나에 대시 옵션 지정자 구성 됩니다 (**-**) 또는 슬래시 (**/**), 옵션의 이름입니다. 옵션 이름은 약식으로 표기할 수 없습니다. 콜론 뒤에 지정 된 인수를 사용 하는 몇 가지 옵션 (**:**). 옵션 사양에는 공백이나 탭을 사용할 수 없습니다. 한 개 이상의 공백 또는 탭을 사용하여 명령줄에서 옵션 사양을 구분합니다. 옵션 이름 및 해당 키워드 또는 파일 이름 인수는 대 소문자를 구분 하지 않지만 인수로 사용 되는 식별자는 대/소문자 구분. LIB 옵션이 명령줄에서 지정 된 순서에 명령 파일을 처리 합니다. 옵션은 서로 다른 인수를 사용 하 여 반복 되는 경우 처리할 개가 우선적으로 적용 합니다.

다음 옵션은 LIB의 모든 모드에 적용 합니다.

> **/ERRORREPORT** [**NONE** &#124; **PROMPT** &#124; **QUEUE** &#124; **SEND**]

런타임에 lib.exe 실패 하는 경우 사용할 수 있습니다 **/ERRORREPORT** 이러한 내부 오류에 대 한 Microsoft로 정보를 보내도록 합니다.

에 대 한 자세한 내용은 **/ERRORREPORT**를 참조 하십시오 [/errorReport (내부 컴파일러 오류 보고)](errorreport-report-internal-compiler-errors.md)합니다.

> **/LTCG**

"LTCG"는 의미 *링크 타임 코드 생성*합니다. 이 기능을 사용 하려면 컴파일러 간의 공동 작업 ([cl.exe](compiler-options.md)), LIB 및 링커 ([링크](linker-options.md)) 이외의 모든 구성 요소 자체적으로 수행할 수 있는 코드를 최적화 하기 위해.

LIB에 대 한는 **/LTCG** cl.exe의 입력을 사용 하 여 생성 된 개체 파일 포함 옵션을 지정 합니다 [/GL](gl-whole-program-optimization.md) 컴파일러 옵션입니다. LIB 이러한 입력을 발견 하 고 **/LTCG** 지정 하지 않으면 경고나 정보 메시지를 표시 한 후 사용 하도록 설정 하는 /LTCG을 사용해 서 다시 시작 됩니다. 즉, 명시적으로이 옵션을 설정 하는 데 필요한 것 이지만 LIB 자체적으로 다시 시작할 필요가 없기 때문에 이렇게 하려면 빌드 성능이 빨라집니다.

빌드 프로세스의 LIB 출력 링크에 전송 됩니다. 링크에는 자체 별도 **/LTCG** 전체 프로그램 최적화 및 (PGO) 프로필 기반 최적화 계측을 포함 하 여 다양 한 최적화를 수행 하는 데 사용 되는 옵션입니다. 링크 옵션에 대 한 자세한 내용은 참조 하세요. [/LTCG](ltcg-link-time-code-generation.md)합니다.

> **/MACHINE**

프로그램에 대 한 대상 플랫폼을 지정합니다. 일반적으로 /MACHINE 지정할 필요가 없습니다. LIB은.obj 파일에서 컴퓨터 종류를 유추합니다. 그러나 경우에 따라 LIB 컴퓨터 종류를 확인할 수 없습니다 및 오류 메시지입니다. 이러한 오류가 발생 하는 경우 /MACHINE를 지정 합니다. /EXTRACT 모드에서이 옵션은 확인만 합니다. 사용 하 여 `lib /?` 사용 가능한 컴퓨터 형식을 확인 하려면 명령줄에서.

> **/NOLOGO**

LIB 저작권 메시지 및 버전 번호를 표시 하지 않습니다 하 고 명령 파일의 에코를 방지 합니다.

> **/VERBOSE**

추가 하려는.obj 파일의 이름을 비롯 하 여 세션의 진행률에 대 한 세부 정보를 표시 합니다. 이 정보는 표준 출력으로 보내지며 파일로 리디렉션될 수 있습니다.

> **/WX**[**:NO**]

경고를 오류로 처리 합니다. 참조 [/WX (링커 경고를 오류로 처리)](wx-treat-linker-warnings-as-errors.md) 자세한 내용은 합니다.

다른 옵션은 LIB의 특정 모드에만 적용 됩니다. 이러한 옵션은 각 모드를 설명 하는 섹션에서 설명 합니다.

## <a name="see-also"></a>참고자료

[LIB 참조](lib-reference.md)
