---
title: BSCMAKE 옵션
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCBscMakeTool.OutputFile
- VC.Project.VCBscMakeTool.SuppressStartupBanner
- VC.Project.VCBscMakeTool.PreserveSBR
helpviewer_keywords:
- /v BSCMAKE option
- Iu BSCMAKE option
- browse information files (.bsc), content
- /Er BSCMAKE option
- NOLOGO BSCMAKE option
- /s BSCMAKE option
- /Ei BSCMAKE option
- /o BSCMAKE option
- /NOLOGO BSCMAKE option
- /Iu BSCMAKE option
- s BSCMAKE option (/s)
- /Em BSCMAKE option
- Em BSCMAKE option
- Es BSCMAKE option
- files [C++], BSCMAKE
- Er BSCMAKE option
- BSCMAKE, options for controlling files
- controlling BSCMAKE options
- El BSCMAKE option
- /El BSCMAKE option
- /Es BSCMAKE option
- Ei BSCMAKE option
ms.assetid: fa2f1e06-c684-41cf-80dd-6a554835ebd2
ms.openlocfilehash: b1d62e8d122cb4f08feef60d6936359b3e246749
ms.sourcegitcommit: 06fc71a46e3c4f6202a1c0bc604aa40611f50d36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2019
ms.locfileid: "58508783"
---
# <a name="bscmake-options"></a>BSCMAKE 옵션

> [!WARNING]
> BSCMAKE는 Visual Studio와 함께 설치되지만 더 이상 IDE에서 사용되지 않습니다. Visual Studio 2008부터 찾아보기 및 기호 정보는 자동으로 솔루션 폴더의 SQL Server .sdf 파일에 저장됩니다.

이 섹션에서는 BSCMAKE를 제어 하는 것에 대 한 사용 가능한 옵션을 설명 합니다. 여러 옵션에는 특정 정보를 포함 시키거나 제외 시켜 찾아보기 정보 파일의 내용을 제어 합니다. 제외 옵션을 더 빠르게 실행 BSCMAKE를 허용할 수 고.bsc 파일을 더 작게 될 수 있습니다. 옵션 이름은 대/소문자 구분 (제외한 **/help** 하 고 **/NOLOGO**).

만 **/NOLOGO** 하 고 **/o** Visual Studio 개발 환경 내에서 사용할 수 있습니다.  참조 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md) 에 대 한 정보에 대 한 프로젝트의 속성 페이지에 액세스 합니다.

**/Ei (** *filename*... **)**<br/>
찾아보기 정보 파일에서 지정된 된 포함 파일의 콘텐츠를 제외합니다. 여러 파일을 지정 하려면 공백을 사용 하 여 이름을 구분 하 고 목록을 괄호로 묶습니다. 괄호가 하나만 지정 하는 경우에 필요 하지 않습니다 *filename*합니다. 사용 하 여 **/Ei** 함께 합니다 **/Es** 옵션에서 제외 되지 않은 파일을 제외할 **/Es**합니다.

**/El**<br/>
로컬 기호를 제외합니다. 기본 로컬 기호를 포함 하는 것입니다. 로컬 기호에 대 한 자세한 내용은 참조 하세요. [.sbr 파일 만들기](creating-an-dot-sbr-file.md)합니다.

**/Em**<br/>
매크로 본문의 기호를 제외합니다. 사용 하 여 **/e m** 찾아보기 정보 파일에 매크로 이름만 포함 합니다. 기본은 매크로 이름 및 매크로 확장의 결과 포함 하는 것입니다.

**/Er (** *symbol*...**)**<br/>
찾아보기 정보 파일에서 지정된 된 기호를 제외합니다. 기호 이름을 여러 개를 지정 하려면 공백을 사용 하 여 이름을 구분 하 고 목록을 괄호로 묶습니다. 괄호가 하나만 지정 하는 경우에 필요 하지 않습니다 *기호*합니다.

**/Es**<br/>
절대 경로 사용 하 여 지정 된 또는 INCLUDE 환경 변수에 지정 된 절대 경로 있는 모든 include 파일 찾아보기 정보 파일에서 제외 합니다. (일반적으로이 시스템 찾아보기 정보 파일에 필요 하지 않을 수 있는 정보가 많이 포함 된 파일을 포함 합니다.) 이 옵션에는 상대 경로 또는 INCLUDE에 상대 경로에 있는 파일 또는 경로 없이 지정 된 파일 제외 되지 않은 합니다. 사용할 수는 **/Ei** 옵션과 함께 **/Es** 파일을 제외할 **/Es** 제외 하지 않습니다. 파일 중 일부만 제외 하려는 경우는 **/Es** 제외 하 고, 사용 하 여 **/Ei** 대신 **/Es** 및 제외 하려는 파일을 나열 합니다.

**/errorreport:**[**none** &#124; **prompt** &#124; **queue** &#124; **send**]<br/>
Bscmake.exe의 내부 오류에 대 한 Microsoft로 정보를 보낼 수 있습니다.

에 대 한 자세한 **/errorreport**를 참조 하십시오 [/errorReport (내부 컴파일러 오류 보고)](errorreport-report-internal-compiler-errors.md)합니다.

**/HELP**<br/>
BSCMAKE 명령줄 구문 요약 정보를 표시 합니다.

**/Iu**<br/>
참조 되지 않은 기호를 포함합니다. BSCMAKE는 기본적으로 정의 되었지만 참조 되지 않는 모든 기호를 기록 하지 않습니다. .Sbr 파일을 압축 된 경우이 옵션은 컴파일러가 이미 참조 되지 않은 기호를 제거 하기 때문에 해당 입력된 파일에 대 한 효과가 없습니다.

**/n**<br/>
비증분 빌드를 강제로 수행합니다. 사용 하 여 **/n** .bsc 파일의 존재 여부와 상관 없이 찾아보기 정보 파일의 전체 빌드를 수행 하는 데.sbr 파일이 잘리지 않도록 방지 합니다. 참조 [BSCMAKE에서.bsc 파일을 빌드하는 방법](how-bscmake-builds-a-dot-bsc-file.md)합니다.

**/NOLOGO**<br/>
BSCMAKE 저작권 메시지를 표시 하지 않습니다.

**/o** *filename*<br/>
찾아보기 정보 파일의 이름을 지정합니다. 기본적으로 BSCMAKE 첫 번째.sbr 파일 및.bsc 확장의 기본 이름 찾아보기 정보 파일을 제공합니다.

**/S (** *filename*... **)**<br/>
처음 발견 된 지정된 된 include 파일을 처리 하 고 그렇지 않으면 제외 하기 BSCMAKE를 알려 줍니다. 처리 시간이 경우 여러 소스 파일에 포함 되어 있지만 때마다 전처리 지시문에 의해 변경 되지 않습니다 (예: 머리글 또는.h, 파일을.c 또는.cpp 소스 파일) 파일을 저장 하려면이 옵션을 사용 합니다. 파일을 만들면 찾아보기 정보 파일에 대 한 중요 하지 않은 방식으로 변경 된 경우이 옵션을 사용 하려면 수도 있습니다. 여러 파일을 지정 하려면 공백을 사용 하 여 이름을 구분 하 고 목록을 괄호로 묶습니다. 괄호가 하나만 지정 하는 경우에 필요 하지 않습니다 *filename*합니다. 포함 될 때마다 파일을 제외 하려면 사용 하려는 경우는 **/Ei** 하거나 **/Es** 옵션입니다.

**/v**<br/>
처리 중인 각.sbr 파일의 이름 및 전체 BSCMAKE 실행 하는 방법에 대 한 정보를 포함 하는 자세한 정보 출력을 제공 합니다.

**/?**<br/>
BSCMAKE 명령줄 구문의 간단한 요약을 표시합니다.

다음 명령줄 BSCMAKE 세.sbr 파일에서 MAIN.bsc의 전체 빌드를 수행 하도록 지시 합니다. BSCMAKE TOOLBOX.h의 중복 인스턴스를 제외 하려면 알려줍니다.

```
BSCMAKE /n /S toolbox.h /o main.bsc file1.sbr file2.sbr file3.sbr
```

## <a name="see-also"></a>참고자료

[BSCMAKE 참조](bscmake-reference.md)
