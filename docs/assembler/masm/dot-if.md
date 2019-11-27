---
title: .IF
ms.date: 11/05/2019
f1_keywords:
- .IF
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
ms.openlocfilehash: e8213052dce8d84d62f90d4bc2653435c2b31434
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398232"
---
# <a name="if-32-bit-masm"></a>. IF (32 비트 MASM)

*Condition1* (예: AX > 7)를 테스트 하 고 해당 조건이 true 인 경우 *문을* 실행 하는 코드를 생성 합니다. (32 비트 MASM에만 해당)

## <a name="syntax"></a>구문

> **.**  *Condition1*\
> *문*\
> ⟦ **. ELSEIF** *condition2*\
> *문*⟧ \
> ⟦ **. ELSE**\
> *문*⟧ \
> **.ENDIF**

## <a name="remarks"></a>주의

[인 경우 그 다음에](../../assembler/masm/dot-else.md) 는 원래 조건이 false 인 경우 해당 문이 실행 됩니다. 조건은 런타임에 평가 됩니다.

## <a name="see-also"></a>참고 항목

[지시문 참조](directives-reference.md)
