---
title: ML 심각한 오류 A1010
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A1010
helpviewer_keywords:
- A1010
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
ms.openlocfilehash: 6ec82f7f6d559d977a9aa039ed91689a0ef4d49a
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856880"
---
# <a name="ml-fatal-error-a1010"></a>ML 심각한 오류 A1010

**일치 하지 않는 블록 중첩:**

시작 블록에 짝이 되는 끝이 없거나, 블록 끝에 일치 하는 시작이 없습니다. 다음 중 하나가 포함 될 수 있습니다.

- 와 같은 상위 수준 지시문 [입니다. 이면](../../assembler/masm/dot-if.md)이 고, 그렇지 않으면 [입니다. ](../../assembler/masm/dot-repeat.md)또는를 반복 [합니다. WHILE](../../assembler/masm/dot-while.md).

- [IF](../../assembler/masm/if-masm.md), [REPEAT](../../assembler/masm/repeat.md)또는 **WHILE**과 같은 조건부 어셈블리 지시문입니다.

- 구조체 또는 공용 구조체 정의입니다.

- 프로시저 정의입니다.

- 세그먼트 정의입니다.

- [POPCONTEXT](../../assembler/masm/popcontext.md) 지시문입니다.

- [If](../../assembler/masm/if-masm.md)와 일치 하지 않는 [ELSE](../../assembler/masm/else-masm.md), [ELSEIF](../../assembler/masm/elseif-masm.md)또는 **ENDIF** 와 같은 조건부 어셈블리 지시문입니다.

## <a name="see-also"></a>참조

[ML 오류 메시지](../../assembler/masm/ml-error-messages.md)<br/>