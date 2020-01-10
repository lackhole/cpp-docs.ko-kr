---
title: GOTO (MASM)
ms.date: 12/16/2019
f1_keywords:
- goto
helpviewer_keywords:
- GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
ms.openlocfilehash: f198658f9a4b85e0b5ec9b7a0c122241e57286f6
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317281"
---
# <a name="goto"></a>GOTO

_Macrolabel_ **로 표시 된**줄로 어셈블리를 전송 합니다.

## <a name="syntax"></a>구문

> **GOTO** *macrolabel*

## <a name="remarks"></a>주의

**GOTO** 는 [매크로](macro.md), [FOR](for-masm.md), [forc](forc.md), [REPEAT](repeat.md)및 [WHILE](while-masm.md) 블록 내 에서만 사용할 수 있습니다. *Macrolabel* 대상은 줄에서 유일한 지시문 이어야 하며 선행 콜론 뒤에와 야 합니다.

## <a name="see-also"></a>참조

[지시문 참조](directives-reference.md)\
[MASM BNF 문법](masm-bnf-grammar.md)
