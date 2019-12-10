---
title: .PUSHFRAME
description: 에 대해 설명 합니다. PUSHFRAME MASM 지시문은 프레임 함수를 해제 하는 방법을 지정 하는 데 사용 됩니다.
ms.date: 12/06/2019
f1_keywords:
- .PUSHFRAME
helpviewer_keywords:
- .PUSHFRAME directive
ms.assetid: 17b123d0-4c6d-4fd2-85eb-798e8ad0a73c
ms.openlocfilehash: 5f951396291ecb12dab500a364f176106c5daa8b
ms.sourcegitcommit: 2cac0150ab3bc8260f866451019b8e22c7e1ac11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2019
ms.locfileid: "74945854"
---
# <a name="pushframe"></a>.PUSHFRAME

`UWOP_PUSH_MACHFRAME` 해제 코드 항목을 생성 합니다. 선택적 **코드** 키워드가 지정 된 경우 해제 코드 항목에는 한정자 1이 지정 됩니다. 그렇지 않으면 한정자가 0입니다.

## <a name="syntax"></a>구문

> **. PUSHFRAME** ⟦**CODE**⟧;;

## <a name="remarks"></a>주의

. PUSHFRAME을 사용 하면 ml64.exe 사용자가 프레임 함수를 해제 하는 방법을 지정할 수 있습니다. [PROC](../../assembler/masm/proc.md) 프레임 선언에서로 확장 하는 프롤로그 내 에서만 허용 [됩니다. ENDPROLOG](../../assembler/masm/dot-endprolog.md) 지시문입니다. 이러한 지시문은 코드를 생성 하지 않습니다. `.xdata` 및 `.pdata`생성 합니다. **. PUSHFRAME** 앞에는 해제할 작업을 실제로 구현 하는 지침이 있습니다. 규약을 보장 하기 위해 매크로에서 해제할 해제 지시문과 코드를 모두 래핑하는 것이 좋습니다.

자세한 내용은 [x 64 용 MASM (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)을 참조 하세요.

## <a name="see-also"></a>참조

[지시문 참조](directives-reference.md)
