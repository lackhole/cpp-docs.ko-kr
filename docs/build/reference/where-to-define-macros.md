---
title: 매크로를 정의할 위치
ms.date: 11/04/2016
helpviewer_keywords:
- defining macros
- macros, NMAKE
- NMAKE program, defining macros
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
ms.openlocfilehash: dc03644adea4619b3eabe33c481d71f704a9f410
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316368"
---
# <a name="where-to-define-macros"></a>매크로를 정의할 위치

명령줄, 명령 파일, 메이크파일 Tools.ini 파일에 매크로 정의 합니다.

메이크파일의 또는 Tools.ini 파일에서 각 매크로 정의 별도 줄에 표시 되 고 공백 또는 탭을 사용 하 여 시작할 수 없습니다. 공백이 나 탭 등호 앞뒤 무시 됩니다. 모든 [문자를 문자열](defining-an-nmake-macro.md) 리터럴 주변 따옴표 및 공백이 포함 됩니다.

명령줄 또는 명령 파일에서 공백 및 탭 인수를 구분 하 고 등호를 묶을 수 없습니다. 경우 `string` 공백이 나 탭에 포함 된 큰따옴표를 문자열 자체 또는 매크로 전체를 묶습니다 ("").

## <a name="see-also"></a>참고자료

[NMake 매크로 정의](defining-an-nmake-macro.md)
