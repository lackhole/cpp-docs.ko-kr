---
title: 의사 대상
ms.date: 11/04/2016
helpviewer_keywords:
- makefiles, pseudotargets
- pseudotargets and NMAKE
- NMAKE program, pseudotargets
- timestamps, makefile pseudotargets
- NMAKE program, targets
ms.assetid: c8c479dc-0129-4186-8366-bc6251f2b494
ms.openlocfilehash: 90552d00aaeed804f2bf492a94493882f196167d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319371"
---
# <a name="pseudotargets"></a>의사 대상

의사 대상은 종속 줄에서 파일 이름 대신 사용 되는 레이블입니다. 존재 하지 않는 이며 따라서 오래 된 파일으로 해석 됩니다. NMAKE 의사 대상의 타임 스탬프는 모든 종속 항목 중 가장 최근 가정 합니다. 없는 종속 된 경우 현재 가정 합니다. 의사를 대상으로 사용 하는 경우 해당 명령은 항상 실행 됩니다. 종속 된 것으로 사용 하는 의사 다른 종속성을 대상으로 야 합니다. 그러나 해당 종속성을 명령 블록을 가질 필요가 없습니다.

의사 대상 이름은 대상에 대 한 파일 이름 구문 규칙을 따릅니다. 그러나 이름에서 확장 되지 않은 경우 (즉, 포함 되지 않은 기간), 파일 이름에 대 한 8 자 제한을 초과할 수 있습니다 하 고 최대 256 자까지 사용할 수 있습니다.

## <a name="see-also"></a>참고자료

[대상](targets.md)
