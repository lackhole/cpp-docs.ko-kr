---
title: 가져오기 라이브러리 및 내보내기 파일 빌드
ms.date: 09/05/2018
f1_keywords:
- VC.Project.VCLibrarianTool.ModuleDefinitionFile
- VC.Project.VCLibrarianTool.ExportNamedFunctions
- VC.Project.VCLibrarianTool.GenerateDebug
- VC.Project.VCLibrarianTool.ForceSymbolReferences
helpviewer_keywords:
- OUT library manager option
- INCLUDE library manager option
- /DEF library manager option
- exporting data
- import libraries, building
- -INCLUDE library manager option
- /OUT library manager option
- DEF library manager option
- -DEF library manager option
- -OUT library manager option
- /INCLUDE library manager option
- -EXPORT library manager option
- exporting data, export (.exp) files
- /EXPORT library manager option
- EXPORT library manager option
- .lib files
- EXP files
ms.assetid: 2fe4f30a-1dd6-4b05-84b5-0752e1dee354
ms.openlocfilehash: 37c3169b66e1120dbfdb3a69379430e9bc8a1586
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294793"
---
# <a name="building-an-import-library-and-export-file"></a>가져오기 라이브러리 및 내보내기 파일 빌드

가져오기 라이브러리를 빌드하고 파일 내보내기는 다음 구문을 사용 합니다.

> **LIB /DEF**[**:**<em>deffile</em>] [*options*] [*objfiles*] [*libraries*]

/DEF를 지정 하면 LIB LIB 명령에 전달 되는 내보내기 사양에서 출력 파일을 만듭니다. 내보내기에 사용 하 여 권장 되는 순서 대로 나열 된 지정에 대 한 세 가지가 있습니다.

1. A **__declspec (dllexport)** 중 하나에 정의 된 *objfiles* 또는 *라이브러리*

1. /EXPORT 사양:*이름을* LIB 명령줄에서

1. 정의 **내보내기를** 문에서 *deffile*

이들은 내보내는 프로그램을 연결 하는 경우 내보내기를 지정 하는 데 동일한 메서드입니다. 프로그램 메서드가 둘 이상 사용할 수 있습니다. LIB 명령 부분을 지정할 수 있습니다 (여러 등 *objfiles* 또는 /EXPORT 사양) LIB 명령에서 명령 파일에서 하듯이 수 링크 명령에서입니다.

다음 옵션은 가져오기 라이브러리를 빌드하는 데 적용 되며 파일을 내보냅니다.

> **/OUT:** *import*

에 대 한 기본 출력 파일 이름을 재정의 합니다 *가져올* 생성 되는 라이브러리입니다. /OUT 지정 되지 않은 경우 기본 이름은 첫 번째 개체 파일 또는 LIB 명령과 확장 라이브러리의 기본 이름입니다. lib 합니다. 내보내기 파일에는 가져오기 라이브러리 및 확장으로 동일한 기본 이름이 지정 됩니다. exp.

> **/EXPORT:** *entryname*\[**=** *internalname*]\[,**\@**<em>ordinal</em>\[, **NONAME**]]\[, **DATA**]

다른 프로그램이 함수를 호출할 수 있도록 프로그램에서 함수를 내보냅니다. 데이터를 내보낼 수도 있습니다 (사용 하는 **데이터** 키워드). 내보내기는 일반적으로 DLL에 정의 됩니다.

합니다 *entryname* 호출 프로그램에서 사용 하는 것은 함수 또는 데이터 항목의 이름입니다. 선택적으로 지정할 수 있습니다 합니다 *internalname* 정의 프로그램에 기본적으로 알려진 함수로 *internalname* 동일 *entryname*합니다. 합니다 *서 수* 지정 하지 않으면 경우는 범위는 1부터 65535의 내보내기 테이블에 인덱스를 지정 합니다 *서*, LIB 할당 합니다. 합니다 **NONAME** 키워드는 서 수로만 없이 함수를 내보냅니다는 *entryname*합니다. 합니다 **데이터** 키워드 데이터 전용 개체를 내보내는 데 사용 됩니다.

> **/INCLUDE:** *symbol*

지정한 *기호* 기호 테이블입니다. 이 옵션은 적용 되지 않는 포함 된 라이브러리 개체를 사용 하는 데 유용 합니다.

Note는.dll을 만들기 전에 예비 단계에서 가져오기 라이브러리를 만드는 경우 전달 해야 개체 파일의 동일한 집합.dll을 빌드할 때 가져오기 라이브러리를 빌드할 때는 전달 합니다.

## <a name="see-also"></a>참고자료

[가져오기 라이브러리 및 내보내기 파일을 사용한 작업](working-with-import-libraries-and-export-files.md)
