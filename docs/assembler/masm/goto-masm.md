---
title: GOTO (MASM)
ms.date: 08/30/2018
f1_keywords:
- goto
helpviewer_keywords:
- GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
ms.openlocfilehash: 424ff295fe37e7c5ff02897a01b99a7c75876f85
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397491"
---
# <a name="goto-masm"></a>GOTO (MASM)

_Macrolabel_ **로 표시 된**줄로 어셈블리를 전송 합니다.

## <a name="syntax"></a>구문

> **GOTO** *macrolabel*

## <a name="remarks"></a>주의

**GOTO** 는 [매크로](macro.md), [FOR](for-masm.md), [forc](forc.md), [REPEAT](repeat.md)및 [WHILE](while-masm.md) 블록 내 에서만 사용할 수 있습니다. *Macrolabel* 대상은 줄에서 유일한 지시문 이어야 하며 선행 콜론 뒤에와 야 합니다.

## <a name="see-also"></a>참고 항목

[지시문 참조](directives-reference.md)
