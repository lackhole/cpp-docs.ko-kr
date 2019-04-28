---
title: 명령 한정자
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, command modifiers
- command modifiers
ms.assetid: b661c432-210f-4f05-bc56-744a46e0fc0b
ms.openlocfilehash: 6131b94a6ee78026b8d5337061a6238df785b64d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272413"
---
# <a name="command-modifiers"></a>명령 한정자

명령 앞에 공백이 나 탭으로 구분 된 필요에 따라 하나 이상의 명령 한정자를 지정할 수 있습니다. 명령과 마찬가지로 한정자를 써야 합니다.

|한정자|용도|
|--------------|-------------|
|\@*command*|명령의 표시를 하지 않습니다. 명령으로는 표시 되지 않도록 설정 하지 않습니다. NMAKE는 기본적으로 실행 된 모든 명령을 표시합니다. /S를 사용 하 여 전체 메이크파일;에 대 한 표시 하지 않으려면 사용 하 여 **입니다. 자동** 메이크파일 부분에 대 한 표시 하지 않으려면입니다.|
|**-**\[*number*] *command*|오류에 대 한 검사를 해제 *명령*입니다. 기본적으로 NMAKE 명령을 0이 아닌 종료 코드를 반환 하는 경우 중지 됩니다. 경우-*번호* 는 종료 코드를 초과 하는 경우 NMAKE 중지 사용 *번호*합니다. 대시 사이 공백이 나 탭을 표시할 수 없습니다 및 *수입니다.* 하나 이상의 공백 또는 탭 사이 나타나야 `number` 하 고 *명령*입니다. / I를 사용 하 여 전체 메이크파일;에 대해 오류 검사를 해제 하려면 사용 하 여 **입니다. 무시** 오류 메이크파일 부분에 대 한 검사를 해제 하려면.|
|**\!** *command*|실행 *명령* 종속 된 각 파일에 대 한 경우 *명령* 사용 하 여 <strong>$ \* \*</strong> (종속성의 모든 종속 파일) 또는 **$?** (대상 보다 나중 타임 스탬프를 사용 하 여 종속성의 모든 종속 파일.)|

## <a name="see-also"></a>참고자료

[메이크파일의 명령](commands-in-a-makefile.md)
