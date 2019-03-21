---
title: NMAKE 실행
ms.date: 09/05/2018
helpviewer_keywords:
- targets, building
- response files, NMAKE
- targets
- command files
- NMAKE program, targets
- NMAKE program, running
- command files, NMAKE
ms.assetid: 0421104d-8b7b-4bf3-86c1-928d9b7c1a8c
ms.openlocfilehash: dac5e9c1676278d150dd9802697a8ae8959a40e5
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827482"
---
# <a name="running-nmake"></a>NMAKE 실행

## <a name="syntax"></a>구문

> **NMAKE** [*옵션* ...] [*매크로* ...] [*대상* ...] [**\@**<em>commandfile</em> ...]

## <a name="remarks"></a>설명

NMAKE 빌드만 지정할 *대상* 또는 지정 되지 않은 경우 첫 번째 메이크파일의 대상으로 합니다. 첫 번째 메이크파일 대상 수를 [의사 대상](pseudotargets.md) 다른 목표를 작성 하는 합니다. NMAKE /F;를 사용 하 여 지정 된 메이크파일을 사용합니다 /F 지정 하지 않으면 현재 디렉터리의 메이크파일 파일을 사용 합니다. 유추 규칙 사용 하 여 명령줄 빌드를 지정 된 메이크파일이 없는 경우 *대상*합니다.

합니다 *commandfile* 명령줄 입력을 포함 텍스트 파일 (또는 응답 파일). 다른 입력 앞 또는 뒤에 \@ *commandfile*합니다. 경로 허용 됩니다. *commandfile*, 줄 바꿈 공백으로 처리 됩니다. 공백이 포함 된 매크로 정의를 따옴표로 묶습니다.

## <a name="what-do-you-want-to-know-more-about"></a>추가 정보

[NMAKE 옵션](nmake-options.md)

[Tools.ini 및 NMake](tools-ini-and-nmake.md)

[NMAKE의 종료 코드](exit-codes-from-nmake.md)

## <a name="see-also"></a>참고자료

[NMAKE 참조](nmake-reference.md)
