---
title: .SETFRAME
ms.date: 08/30/2018
f1_keywords:
- .SETFRAME
helpviewer_keywords:
- .SETFRAME directive
ms.assetid: eaa9b5ed-4daa-4f1e-bdb6-100758007ab3
ms.openlocfilehash: a21dda496d32abcfeb4692d0228afdbcfd4e5ebb
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397925"
---
# <a name="setframe"></a>.SETFRAME

지정 된 레지스터 (*reg*)와 오프셋 (*오프셋*)을 사용 하 여 해제 정보에서 프레임 레지스터 필드와 오프셋을 채웁니다. 오프셋은 16의 배수 여야 하며 240 보다 작거나 같아야 합니다. 이 지시문은 현재 프롤로그 오프셋을 사용 하 여 지정 된 레지스터에 대 한 `UWOP_SET_FPREG` 해제 코드 항목도 생성 합니다.

## <a name="syntax"></a>구문

> **. SETFRAME** *reg*, *offset*

## <a name="remarks"></a>주의

**. SETFRAME** 을 사용 하면 ml64.exe 사용자가 프레임 함수를 해제 하는 방법을 지정할 수 있으며, 프롤로그 내 에서만 허용 되며, [프로시저](../../assembler/masm/proc.md) 프레임 선언에서로 확장 됩니다 [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) 지시문입니다. 이러한 지시문은 코드를 생성 하지 않습니다. `.xdata` 및 `.pdata`생성 합니다. **. SETFRAME** 앞에는 해제할 작업을 실제로 구현 하는 지침이 있어야 합니다. 규약을 보장 하기 위해 매크로에서 해제할 해제 지시문과 코드를 모두 래핑하는 것이 좋습니다.

자세한 내용은 [x 64 용 MASM (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)을 참조 하세요.

## <a name="sample"></a>샘플

### <a name="description"></a>설명

다음 샘플에서는 프레임 포인터를 사용 하는 방법을 보여 줍니다.

### <a name="code"></a>코드

```asm
; ml64 frmex2.asm /link /entry:frmex2 /SUBSYSTEM:CONSOLE
_text SEGMENT
frmex2 PROC FRAME
   push rbp
.pushreg rbp
   sub rsp, 010h
.allocstack 010h
   mov rbp, rsp
.setframe rbp, 0
.endprolog
   ; modify the stack pointer outside of the prologue (similar to alloca)
   sub rsp, 060h

   ; we can unwind from the following AV because of the frame pointer
   mov rax, 0
   mov rax, [rax] ; AV!

   add rsp, 060h
   add rsp, 010h
   pop rbp
   ret
frmex2 ENDP
_text ENDS
END
```

## <a name="see-also"></a>참고 항목

[지시문 참조](directives-reference.md)
