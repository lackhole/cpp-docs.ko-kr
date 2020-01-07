---
title: .SAVEXMM128
ms.date: 12/17/2019
f1_keywords:
- .SAVEXMM128
helpviewer_keywords:
- .SAVEXMM128 directive
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
ms.openlocfilehash: 6402b75c10b1400d56923116621f00b4d0908822
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75318256"
---
# <a name="savexmm128"></a>.SAVEXMM128

현재 프롤로그 오프셋을 사용 하 여 지정 된 XMM 레지스터 및 오프셋에 대 한 `UWOP_SAVE_XMM128` 또는 `UWOP_SAVE_XMM128_FAR` 해제 코드 항목을 생성 합니다. MASM은 가장 효율적인 인코딩을 선택 합니다.

## <a name="syntax"></a>구문

> **. SAVEXMM128** *xmmreg* , *offset*

## <a name="remarks"></a>주의

**. SAVEXMM128** 를 사용 하면 ml64.exe 사용자가 프레임 함수를 해제 하는 방법을 지정할 수 있으며, 프롤로그 내 에서만 허용 되며, [프로시저](proc.md) 프레임 선언에서로 확장 됩니다 [. ENDPROLOG](dot-endprolog.md) 지시문입니다. 이러한 지시문은 코드를 생성 하지 않습니다. `.xdata` 및 `.pdata`생성 합니다. . SAVEXMM128는 해제할 작업을 실제로 구현 하는 지침을 따라야 합니다. 규약을 보장 하기 위해 매크로에서 해제할 해제 지시문과 코드를 모두 래핑하는 것이 좋습니다.

*오프셋* 은 16의 배수 여야 합니다.

자세한 내용은 [x 64 용 MASM (ml64.exe)](masm-for-x64-ml64-exe.md)을 참조 하세요.

## <a name="see-also"></a>참조

[지시문 참조](directives-reference.md)\
[MASM BNF 문법](masm-bnf-grammar.md)
