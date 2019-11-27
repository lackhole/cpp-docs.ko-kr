---
title: EXTERN (MASM)
ms.date: 08/30/2018
f1_keywords:
- extern
helpviewer_keywords:
- EXTERN directive
ms.assetid: 667d703d-3aaf-4139-a586-29bc5dab1aff
ms.openlocfilehash: fc66338d90b54ecb12ef3ab1aa56214fb445cb13
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397557"
---
# <a name="extern-masm"></a>EXTERN (MASM)

형식이 *형식인* *name* 이라는 외부 변수, 레이블 또는 기호를 하나 이상 정의 합니다.

## <a name="syntax"></a>구문

> **EXTERN** ⟦*language-type*⟧ *name* ⟦ __(__ *altid* __)__ ⟧ __:__ *type* ⟦ __,__ ⟦*language-type*⟧ *name* ⟦ __(__ *altid* __)__ ⟧ __:__ *type* ... ⟧

## <a name="remarks"></a>주의

*형식은* *이름* 을 상수로 가져오는 [ABS](../../assembler/masm/operator-abs.md)일 수 있습니다. [Extrn](../../assembler/masm/extrn.md)과 동일 합니다.

## <a name="see-also"></a>참고 항목

[지시문 참조](../../assembler/masm/directives-reference.md)
