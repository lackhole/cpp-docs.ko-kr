---
title: NMAKE 심각한 오류 U1035
ms.date: 11/04/2016
f1_keywords:
- U1035
helpviewer_keywords:
- U1035
ms.assetid: 68f0cc59-007e-4109-ac30-7ac4ac447e6d
ms.openlocfilehash: 9c4055bb99243f7d20c1da90aef7b916c46c2749
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324339"
---
# <a name="nmake-fatal-error-u1035"></a>NMAKE 심각한 오류 U1035

구문 오류: 예상 ':' 또는 '=' 구분 기호

콜론 (**:**) 또는 등호 (**=**)가 필요 합니다.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면

1. 콜론 대상을 따르지 않았습니다.

1. 콜론 및 공백 없이 (예: a:) 뒤에 단일 문자 대상입니다. NMAKE는 드라이브 사양으로 해석합니다.

1. 콜론 유추 규칙을 따르지 않았습니다.

1. 매크로 정의 등호 오지 않았습니다.

1. 문자 뒤에 백슬래시 (**\\**)는 새 줄으로 명령을 계속 하는 데 사용 된 합니다.

1. 문자열이는 NMAKE 구문 규칙을 따르지 않는 표시 되었습니다.

1. 메이크파일 워드 프로세서에서 형식이 지정 되었습니다.