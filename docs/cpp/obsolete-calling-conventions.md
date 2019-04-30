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
ms.openlocfilehash: 86c75c779158d9f191dd015410cf16c9ce25690d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245035"
---
# <a name="obsolete-calling-conventions"></a>사용되지 않는 호출 규칙

## <a name="microsoft-specific"></a>Microsoft 전용

합니다 **__pascal**를 **__fortran**, 및 **__syscall** 호출 규칙은 더 이상 지원 합니다. 지원되는 호출 규칙 및 적절한 링커 옵션 중 하나를 사용하여 해당 기능을 에뮬레이트할 수 있습니다.

\<windows.h > 이제 대상에 대 한 적절 한 호출 규칙으로 변환 되 WINAPI 매크로 지원 합니다. 이전에 사용한 PASCAL WINAPI 사용 하거나 **__far \__pascal**합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[인수 전달 및 명명 규칙](../cpp/argument-passing-and-naming-conventions.md)