---
title: NMAKE 심각한 오류 U1073
ms.date: 11/04/2016
f1_keywords:
- U1073
helpviewer_keywords:
- U1073
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
ms.openlocfilehash: 2aa02fd86906bd545373a313fa5e6e409ffb3cf9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366935"
---
# <a name="nmake-fatal-error-u1073"></a>NMAKE 심각한 오류 U1073

'targetname'를 확인 하는 방법을 몰라도합니다

지정된 된 대상 없고 실행할 명령 또는 유추 규칙을 적용 하지 않습니다.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.

1. 대상 이름의 철자를 확인 합니다.

1. 하는 경우 *targetname* 는 의사는 다른 설명 블록에 대상으로 지정 합니다.

1. 하는 경우 *targetname* 는 매크로 호출을 null 문자열로 확장 되지 않고 해야 합니다.