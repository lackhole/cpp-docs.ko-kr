---
title: 메이크파일 전처리 지시문
ms.date: 08/11/2019
f1_keywords:
- '!UNDEF'
- '!INCLUDE'
- '!IFNDEF'
- '!MESSAGE'
helpviewer_keywords:
- ERROR directive
- '!MESSAGE directive'
- IF directive
- '!UNDEF directive'
- IFDEF directive
- '!ELSEIF directive'
- '!IFDEF directive'
- '!IF directive'
- UNDEF directive
- '!CMDSWITCHES directive'
- ENDIF directive
- directives, makefile preprocessing
- INCLUDE directive
- IFNDEF directive
- preprocessing directives, makefiles
- '!IFNDEF directive'
- ELSEIFNDEF directive
- NMAKE program, expressions
- ELSEIF directive
- '!ERROR directive'
- '!ENDIF directive'
- MESSAGE directive
- '!INCLUDE directive'
- '!ELSEIFNDEF directive'
- CMDSWITCHES directive
- '!ELSEIFDEF directive'
- '!ELSE directive'
- NMAKE program, preprocessor directives
- makefiles, preprocessing directives
- ELSE directive
- ELSEIFDEF directive
ms.assetid: bcedeccb-d981-469d-b9e8-ab5d097fd8c2
ms.openlocfilehash: 4825ca180cb1b419a9ffa5232575ba1a24f8805d
ms.sourcegitcommit: db1ed91fa7451ade91c3fb76bc7a2b857f8a5eef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2019
ms.locfileid: "68980520"
---
# <a name="makefile-preprocessing-directives"></a>메이크파일 전처리 지시문

전처리 지시문은 대/소문자를 구분 하지 않습니다. 초기 느낌표 (!)는 줄의 시작 부분에 표시 되어야 합니다. 0 개 이상의 공백이 나 탭은 느낌표에 대해 느낌표 뒤에 올 수 있습니다.

- `!CMDSWITCHES`{`+` &#124; } 옵션 ... `-`

   각 *옵션* 을 on 또는 off로 설정 합니다. 공백 또는 탭은 or `+` `-` 연산자 앞에 나와야 합니다. 연산자와 [옵션 문자](running-nmake.md#nmake-options)사이에는 아무것도 표시 되지 않습니다. 문자는 대/소문자를 구분 하지 않으며 슬래시 (`/`) 없이 지정 됩니다. 일부 옵션을 설정 하 고 다른 옵션을 해제 하려면의 `!CMDSWITCHES`별도 사양을 사용 합니다.

   메이크파일에는/D,/I,/N 및/S만 사용할 수 있습니다. Setup.ini에서/F,/HELP,/NOLOGO,/X 및/?를 제외한 모든 옵션을 사용할 수 있습니다. 설명 블록에 지정 된 변경 내용은 다음 설명 블록까지 적용 되지 않습니다. 이 지시문은 **Makeflags**를 업데이트 합니다. **Makeflags** 가 지정 된 경우 재귀 중에 변경 내용이 상속 됩니다.

- `!ERROR`*텍스트*

   U1050에 *텍스트* 를 표시 한 다음,/k,/i, `.IGNORE`, `!CMDSWITCHES`또는 대시 (`-`) 명령 한정자를 사용 하는 경우에도 NMAKE를 중단 합니다. *텍스트* 앞의 공백이 나 탭은 무시 됩니다.

- `!MESSAGE`*텍스트*

   *텍스트* 를 표준 출력으로 표시 합니다. *텍스트* 앞의 공백이 나 탭은 무시 됩니다.

- `!INCLUDE`[ `<` ] *filename* [ `>` ]

   *파일 이름을* 메이크파일로 읽은 다음 현재 메이크파일을 계속 합니다. NMAKE는 지정 된 또는 현재 디렉터리에 있는 *파일 이름을* 먼저 검색 한 다음, 부모 메이크파일의 디렉터리를 재귀적으로 검색 한 다음, *파일 이름이* 꺾쇠 괄호 (`< >`)로 묶여 있는 **경우에 지정 된 디렉터리에서** Include 환경 변수로 처음 설정 되는 매크로를 포함 합니다. 설정, `.SUFFIXES` `.PRECIOUS`및 유추 규칙을 재귀적 메이크파일에 전달 하는 데 유용 합니다.

- `!IF`*constant_expression*

   `!IF` 는와 `!ELSE` next 사이에 있는 문을 처리 합니다. constant_expression가 0이 아닌 값으로 계산 됩니다 `!ENDIF` .

- `!IFDEF`*macroname*

   `!IFDEF` 와 다음 `!ELSE` 사이 또는 `!ENDIF` *macroname* 이 정의 된 경우 문을 처리 합니다. Null 매크로가 정의 된 것으로 간주 됩니다.

- `!IFNDEF`*macroname*

   와 `!IFNDEF` 다음`!ELSE`사이의 문이나 *macroname* 이 정의 되지 않은 경우를 처리 합니다. `!ENDIF`

- `!ELSE`[`IF` &#124; *constant_expression* &#124; *macroname* macroname] `IFDEF` `IFNDEF`

   `!ELSE` `!ENDIF` 이전`!IFNDEF` , 또는 문이0으로계산되는경우와다음사이의문을처리합니다.`!IFDEF` `!IF` 선택적 키워드를 통해 전처리를 추가로 제어할 수도 있습니다.

- `!ELSEIF`

   `!ELSE IF`의 동의어입니다.

- `!ELSEIFDEF`

   `!ELSE IFDEF`의 동의어입니다.

- `!ELSEIFNDEF`

   `!ELSE IFNDEF`의 동의어입니다.

- `!ENDIF`

   `!IF` ,`!IFDEF`또는 블록`!IFNDEF` 의 끝을 표시 합니다. 같은 줄의 `!ENDIF` 뒤에 오는 모든 텍스트는 무시 됩니다.

- `!UNDEF`*macroname*

   를해제 합니다.

## <a name="see-also"></a>참고자료

- [메이크파일 전처리](makefile-preprocessing.md)