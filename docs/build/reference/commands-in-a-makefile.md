---
title: 메이크파일의 명령
ms.date: 11/04/2016
helpviewer_keywords:
- commands, makefiles
ms.assetid: 8085517e-42f4-493b-b8f8-44311fc08c64
ms.openlocfilehash: fcb8737070931cf95d7bfb3971a84e22c7ad70a4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294397"
---
# <a name="commands-in-a-makefile"></a>메이크파일의 명령

설명 블록 또는 유추 규칙 종속성이 오래 된 경우 실행 하는 명령 블록을 지정 합니다. NMAKE 않는 한 각 명령을 실행 하기 전에 표시 /S, **합니다. 자동**, **! CMDSWITCHES**, 또는 \@ 사용 됩니다. NMAKE 설명 블록에 명령 블록이 따르지 않으면 일치 하는 유추 규칙을 찾습니다.

명령 블록을 고유한 줄에 각 명령을 하나 이상 포함합니다. 명령 블록 또는 종속성 및 규칙 사이의 빈 줄 없습니다 나타날 수 있습니다. 그러나 공백이 나 탭을 포함 하는 줄 나타날 수 있습니다. 이 줄은 null 명령으로 해석 하 고 오류가 발생 하지 않습니다. 명령 줄 사이의 빈 줄 허용 됩니다.

명령줄을 사용 하는 하나 이상의 공백이 나 탭을 사용 하 여 시작합니다. 뒤에 줄 바꿈 문자가 백슬래시 (\)은 명령;에서 공간으로 해석 됩니다. 줄의 끝에 다음 줄으로 명령을 계속 하려면 백슬래시를 사용 합니다. NMAKE 백슬래시를 문자 그대로 해석 백슬래시 뒤에 공백 또는 탭을 비롯 한 모든 기타 문자가 있는 경우.

명령 앞에 세미콜론 (;) 뒤에 명령 블록이 여부 종속성 줄 또는 유추 규칙에 나타날 수 있습니다.

```
project.obj : project.c project.h ; cl /c project.c
```

## <a name="what-do-you-want-to-know-more-about"></a>추가 정보

[명령 한정자](command-modifiers.md)

[파일 이름 부분 구문](filename-parts-syntax.md)

[메이크파일의 인라인 파일](inline-files-in-a-makefile.md)

## <a name="see-also"></a>참고자료

[NMAKE 참조](nmake-reference.md)
