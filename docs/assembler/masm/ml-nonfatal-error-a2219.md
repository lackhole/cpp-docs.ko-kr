---
title: ML 심각하지 않은 오류 A2219
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A2219
helpviewer_keywords:
- A2219
ms.assetid: 5ebc2f40-e47e-4f8e-b7b9-960b9cfc9f6d
ms.openlocfilehash: 611be49a1d4018eeb4edd9ee750d5a0614a83abe
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75311951"
---
# <a name="ml-nonfatal-error-a2219"></a>ML 심각하지 않은 오류 A2219

> 해제 코드의 오프셋에 대 한 맞춤이 잘못 되었습니다.

## <a name="remarks"></a>주의

[&period;ALLOCSTACK](dot-allocstack.md) 및 [&period;savereg](dot-savereg.md) 의 피연산자는 8의 배수 여야 합니다.  [&period;SAVEXMM128](dot-savexmm128.md) 및 [&period;setframe](dot-setframe.md) 의 피연산자는 16의 배수 여야 합니다.

## <a name="see-also"></a>참조

[ML 오류 메시지](ml-error-messages.md)
