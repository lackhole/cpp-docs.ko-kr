---
title: .IF
ms.date: 11/05/2019
f1_keywords:
- .IF
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
ms.openlocfilehash: 83c9ff588e2fe273e24e1d0b1c16517c5eee3365
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2019
ms.locfileid: "73703782"
---
# <a name="if-32-bit-masm"></a>. IF (32 비트 MASM)

`condition1` (예: AX > 7)를 테스트 하 고 해당 조건이 true 인 경우 *문을* 실행 하는 코드를 생성 합니다. (32 비트 MASM에만 해당)

## <a name="syntax"></a>구문

> . Condition1 인 경우<br/>
> 문<br/>
> [[. ELSEIF condition2<br/>
> 문]]<br/>
> [[. 사람이<br/>
> 문]]<br/>
> .ENDIF

## <a name="remarks"></a>주의

[인 경우 그 다음에](../../assembler/masm/dot-else.md) 는 원래 조건이 false 인 경우 해당 문이 실행 됩니다. 조건은 런타임에 평가 됩니다.

## <a name="see-also"></a>참조

[지시문 참조](../../assembler/masm/directives-reference.md)<br/>