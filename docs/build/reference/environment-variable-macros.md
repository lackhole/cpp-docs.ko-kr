---
title: 환경 변수 매크로
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, environment variable macros
- environment variables, macros in NMAKE
- macros, environment-variable
ms.assetid: f8e96635-0906-47b0-9f56-12a6fdf5e347
ms.openlocfilehash: 7f7f8a05545658142001b75ac78975251185a033
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272613"
---
# <a name="environment-variable-macros"></a>환경 변수 매크로

NMAKE는 매크로 정의 세션을 시작 하기 전에 존재 하는 환경 변수를 상속 합니다. 운영 체제 환경에서 변수로 설정 된 경우에 NMAKE 매크로로 제공 됩니다. 상속 된 이름은 대문자로 변환 됩니다. 상속 전처리 전에 발생합니다. /E 옵션 매크로 메이크파일에 동일한 이름의 모든 매크로 재정의 하려면 환경 변수에서 상속을 사용 합니다.

환경 변수 매크로 세션에서 다시 정의할 수 있습니다 하 고 해당 환경 변수를 변경 합니다. 또한 SET 명령 사용 하 여 환경 변수를 변경할 수 있습니다. 세션에서 환경 변수를 변경 하려면 SET 명령을 사용 하 여 변경 되지 않습니다 해당 매크로 있지만.

예를 들어:

```
PATH=$(PATH);\nonesuch

all:
    echo %PATH%
```

이 예제에서는 변경 `PATH` 해당 환경 변수를 변경 `PATH`; 추가 `\nonesuch` 경로에 있습니다.

환경 변수는 메이크파일의 구문상 올바른 것 문자열로 정의 된 경우 매크로가 생성 되 고 경고가 생성 됩니다. 변수 값을 달러 기호 ($)를 포함 하는 경우 NMAKE 매크로 호출의 시작 부분으로 해석 합니다. 매크로 사용 하 여 예기치 않은 동작이 발생할 수 있습니다.

## <a name="see-also"></a>참고자료

[특수 NMake 매크로](special-nmake-macros.md)
