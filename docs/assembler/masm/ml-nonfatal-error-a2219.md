---
title: ML 심각하지 않은 오류 A2219
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A2219
helpviewer_keywords:
- A2219
ms.assetid: 5ebc2f40-e47e-4f8e-b7b9-960b9cfc9f6d
ms.openlocfilehash: cf2be5db2aa9c21597c199a6840f4aaa50e0a681
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74854591"
---
# <a name="ml-nonfatal-error-a2219"></a>ML 심각하지 않은 오류 A2219

> 해제 코드의 오프셋에 대 한 맞춤이 잘못 되었습니다.

## <a name="remarks"></a>주의

[&period;ALLOCSTACK](../../assembler/masm/dot-allocstack.md) 및 [&period;savereg](../../assembler/masm/dot-savereg.md) 의 피연산자는 8의 배수 여야 합니다.  [&period;SAVEXMM128](../../assembler/masm/dot-savexmm128.md) 및 [&period;setframe](../../assembler/masm/dot-setframe.md) 의 피연산자는 16의 배수 여야 합니다.

## <a name="see-also"></a>참조

[ML 오류 메시지](../../assembler/masm/ml-error-messages.md)
