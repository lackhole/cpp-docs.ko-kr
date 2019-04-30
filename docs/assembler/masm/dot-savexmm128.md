---
title: .SAVEXMM128
ms.date: 08/30/2018
f1_keywords:
- .SAVEXMM128
helpviewer_keywords:
- .SAVEXMM128 directive
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
ms.openlocfilehash: c29ec47170c5e0f46f02d53f23ab477a79bbdc32
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62205227"
---
# <a name="savexmm128"></a>.SAVEXMM128

생성 중 하나를 `UWOP_SAVE_XMM128` 또는 `UWOP_SAVE_XMM128_FAR` 지정한 XMM 레지스터에 대 한 코드 항목을 해제 하 고 현재 프롤로그 오프셋을 사용 하 여 오프셋입니다. MASM 가장 효율적인 인코딩 선택 합니다.

## <a name="syntax"></a>구문

> . savexmm128 xmmreg, 오프셋

## <a name="remarks"></a>설명

. SAVEXMM128 하면 ml64.exe 프레임 함수 해제 될 때 및에서 확장 하는 프롤로그 내 에서만 허용 됩니다 방법을 지정할 수는 [PROC](../../assembler/masm/proc.md) 프레임 선언을 [합니다. 프롤로그 끝](../../assembler/masm/dot-endprolog.md) 지시문입니다. 이러한 지시문 코드를 생성 하지 않습니다. 만 생성할 `.xdata` 고 `.pdata`입니다. . 동작 스택이 없습니다을 실제로 구현 하는 지침 SAVEXMM128 보다 선행 되어야 합니다. 모두 해제 지시문 및 규약 확인 매크로에서 해제를 위한 코드를 래핑하는 것이 좋습니다.

*오프셋* 16의 배수 여야 합니다.

자세한 내용은 [MASM (ml64.exe) x64](../../assembler/masm/masm-for-x64-ml64-exe.md)합니다.

## <a name="see-also"></a>참고자료

[지시문 참조](../../assembler/masm/directives-reference.md)<br/>