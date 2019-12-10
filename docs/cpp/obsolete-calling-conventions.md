---
title: 사용되지 않는 호출 규칙
ms.date: 11/04/2016
f1_keywords:
- __fortran
- __pascal
- __syscall
helpviewer_keywords:
- WINAPI [C++]
- __syscall keyword [C++]
- __pascal keyword [C++]
- __fortran keyword [C++]
- calling conventions, obsolete
ms.assetid: a91fc665-034a-48ce-b6bd-d27125f308a7
ms.openlocfilehash: 7f059afe02cbbad77920fd8c4a0e6cb7c958e992
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857361"
---
# <a name="obsolete-calling-conventions"></a>사용되지 않는 호출 규칙

**Microsoft 전용**

**__Pascal**, **__fortran**및 **__syscall** 호출 규칙은 더 이상 지원 되지 않습니다. 지원되는 호출 규칙 및 적절한 링커 옵션 중 하나를 사용하여 해당 기능을 에뮬레이트할 수 있습니다.

이제 windows > \<는 대상에 대 한 적절 한 호출 규칙으로 변환 되는 WINAPI 매크로를 지원 합니다. 이전에 파스칼을 사용 했거나 **_pascal \___FAR**WINAPI를 사용 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[인수 전달 및 명명 규칙](../cpp/argument-passing-and-naming-conventions.md)