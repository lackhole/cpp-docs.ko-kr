---
title: ML 심각한 오류 A1007
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A1007
helpviewer_keywords:
- A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
ms.openlocfilehash: 01633b4fa084b7d5e14af5a5c6e51e3dca684d2a
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856919"
---
# <a name="ml-fatal-error-a1007"></a>ML 심각한 오류 A1007

**중첩 수준이 너무 깊습니다.**

어셈블러에서 중첩 한도에 도달 했습니다. 이 제한은 별도로 명시 된 경우를 제외 하 고 20 수준입니다.

다음 중 하나가 너무 많이 중첩 되었습니다.

- 와 같은 상위 수준 지시문 [입니다. 이면](../../assembler/masm/dot-if.md)이 고, 그렇지 않으면 [입니다. ](../../assembler/masm/dot-repeat.md)또는를 반복 [합니다. WHILE](../../assembler/masm/dot-while.md).

- 구조 정의입니다.

- 조건부 어셈블리 지시문입니다.

- 프로시저 정의입니다.

- [Pushcontext](../../assembler/masm/pushcontext.md) 지시문입니다. 제한은 10입니다.

- 세그먼트 정의입니다.

- 포함 파일입니다.

- 매크로입니다.

## <a name="see-also"></a>참조

[ML 오류 메시지](../../assembler/masm/ml-error-messages.md)<br/>