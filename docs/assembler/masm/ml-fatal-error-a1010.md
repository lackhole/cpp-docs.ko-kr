---
title: ML 심각한 오류 A1010
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A1010
helpviewer_keywords:
- A1010
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
ms.openlocfilehash: eb4d77b856e93a8d64ee6c51bec63ceae59b22e5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62202067"
---
# <a name="ml-fatal-error-a1010"></a>ML 심각한 오류 A1010

**일치 하지 않는 블록 중첩 합니다.**

블록 시작 하는 일치 하는 끝을 없는 또는 블록의 끝에 일치 하는 시작 하는 없습니다. 다음 중 하나는 포함 될 수도 있습니다.

- 와 같은 높은 수준의 지시문 [합니다. IF](../../assembler/masm/dot-if.md), [합니다. 반복](../../assembler/masm/dot-repeat.md), 또는 [합니다. 하지만](../../assembler/masm/dot-while.md)합니다.

- 와 같은 조건부 어셈블리 지시문 [IF](../../assembler/masm/if-masm.md), [반복](../../assembler/masm/repeat.md), 또는 **하는 동안**합니다.

- 구조체 또는 공용 구조체 정의입니다.

- 프로시저 정의 합니다.

- 세그먼트 정의입니다.

- A [POPCONTEXT](../../assembler/masm/popcontext.md) 지시문입니다.

- 조건부 어셈블리를 같은 지시문을 [ELSE](../../assembler/masm/else-masm.md)를 [ELSEIF](../../assembler/masm/elseif-masm.md), 또는 **ENDIF** 없이 일치 하는 [경우](../../assembler/masm/if-masm.md)합니다.

## <a name="see-also"></a>참고자료

[ML 오류 메시지](../../assembler/masm/ml-error-messages.md)<br/>