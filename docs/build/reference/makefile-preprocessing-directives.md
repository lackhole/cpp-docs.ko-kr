---
title: 메이크파일 전처리 지시문
ms.date: 06/14/2018
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
ms.openlocfilehash: 0945d0e1c149b7e1ab31b0dbbd5003f8b15a1e4d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826782"
---
# <a name="makefile-preprocessing-directives"></a>메이크파일 전처리 지시문

전처리 지시문은 대/소문자 구분 하지 않습니다. 느낌표 (!) 줄의 시작 부분에 표시 되어야 합니다. 공백이 나 탭을 0 이상 들여쓰기에 느낌표 뒤에 나타날 수 있습니다.

- **! CMDSWITCHES** {0}**+** &#124; **-**}*옵션* 하는 중...

   각 설정 *옵션* 또는 해제를 나열 합니다. 공백 또는 탭 앞에 나타나야 합니다 + 또는-연산자 연산자 사이 표시할 수 없음 및 [문자 옵션](nmake-options.md)합니다. 문자 대/소문자 구분 하지 않으며 슬래시 (/) 없이 지정 됩니다. Off에서 일부 옵션 등을 설정 하려면 별도 사양 사용 **! CMDSWITCHES**합니다.

   만 /D, I, /N 및 /S 메이크파일의 사용할 수 있습니다. Tools.ini에에서 /F, /HELP /NOLOGO를 제외 하 고 모든 옵션은 허용/X, 및 /? 설명 블록에 지정 된 변경 내용을 다음 설명 블록까지 적용 되지 않습니다. 이 지시문을 업데이트 **MAKEFLAGS**; 경우 재귀 중 변경 내용을 상속 **MAKEFLAGS** 지정 됩니다.

- **!ERROR**  *text*

   표시 *텍스트* 오류 U1050, 다음 중단 NMAKE, 경우에도에서 /K / I, **합니다. 무시**, **! CMDSWITCHES**, 또는 대시 (-) 명령 한정자를 사용 합니다. 공백 또는 탭 앞 *텍스트* 무시 됩니다.

- **!MESSAGE**  *text*

   표시 *텍스트* 을 표준 출력 합니다. 공백 또는 탭 앞 *텍스트* 무시 됩니다.

- **!INCLUDE** [ **\<** ] *filename* [ **>** ]

   읽습니다 *filename* 을 메이크파일으로 현재 메이크파일을 사용 하 여 계속 합니다. Nmake *filename* 먼저 지정 된 또는 현재 디렉터리에 다음 재귀적으로 모든 부모 메이크파일에 서 찾습니다 한 경우 *filename* 꺾쇠 괄호로 묶입니다 (\<>)를 지정 된 디렉터리에는 **포함** 는 처음에 INCLUDE 환경 변수를 설정 하는 매크로 합니다. 이 지시문은 **합니다. 접미사** 설정을 **합니다. 귀중 한**, 및 재귀 메이크파일 유추 규칙입니다.

- **!IF** *constant_expression*

   이전 **! IF** 및 다음 **! ELSE** 또는 **! ENDIF** 하는 경우 *constant_expression* 0이 아닌 값으로 계산 합니다.

- **!IFDEF**  *macroname*

   이전 **! IFDEF** 및 다음 **! ELSE** 또는 **! ENDIF** 하는 경우 *매크로 이름* 정의 됩니다. Null 매크로 정의로 간주 됩니다.

- **!IFNDEF**  *macroname*

   이전 **! IFNDEF** 및 다음 **! ELSE** 또는 **! ENDIF** 하는 경우 *매크로 이름* 정의 되어 있지 않습니다.

- **!ELSE** [**IF** *constant_expression* &#124; **IFDEF** *macroname* &#124; **IFNDEF** *macroname*]

   이전 **! ELSE** 및 다음 **! ENDIF** 하는 경우 이전 **! IF**, **! IFDEF**, 또는 **! IFNDEF** 문은 0으로 계산 합니다. 선택적 키워드 게 전처리 제어할 수 있습니다.

- **!ELSEIF**

   에 대 한 동의어 **! ELSE IF**합니다.

- **!ELSEIFDEF**

   에 대 한 동의어 **! 다른 IFDEF**합니다.

- **!ELSEIFNDEF**

   에 대 한 동의어 **! 다른 IFNDEF**합니다.

- **!ENDIF**

   끝을 표시는 **! IF**, **! IFDEF**, 또는 **! IFNDEF** 블록입니다. 같은 줄에서 **! ENDIF** 같은 줄에는 무시 됩니다.

- **!UNDEF**  *macroname*

   정의 해제 *매크로 이름*합니다.

## <a name="see-also"></a>참고자료

- [메이크파일 전처리](makefile-preprocessing.md)