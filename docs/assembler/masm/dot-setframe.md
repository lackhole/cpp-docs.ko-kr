---
title: .SETFRAME
ms.date: 08/30/2018
f1_keywords:
- .SETFRAME
helpviewer_keywords:
- .SETFRAME directive
ms.assetid: eaa9b5ed-4daa-4f1e-bdb6-100758007ab3
ms.openlocfilehash: c2c35cdb2889350b27e9fb11c397b684506972c5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62178178"
---
# <a name="setframe"></a>.SETFRAME

지정된 된 레지스터를 사용 하 여 해제 정보에서 필드 및 오프셋을 등록 하는 프레임을 채웁니다 (`reg`) 및 오프셋 (`offset`). 오프셋은 16의 배수 여야 합니다. 240 보다 작거나 같음. 이 지시문도 생성을 `UWOP_SET_FPREG` 현재 프롤로그 오프셋을 사용 하 여 지정 된 등록에 대 한 코드 항목을 해제 합니다.

## <a name="syntax"></a>구문

> . SETFRAME reg 오프셋

## <a name="remarks"></a>설명

. SETFRAME 하면 ml64.exe 프레임 함수 해제 될 때 및에서 확장 하는 프롤로그 내 에서만 허용 됩니다 방법을 지정할 수는 [PROC](../../assembler/masm/proc.md) 프레임 선언을 [합니다. 프롤로그 끝](../../assembler/masm/dot-endprolog.md) 지시문입니다. 이러한 지시문 코드를 생성 하지 않습니다. 만 생성할 `.xdata` 고 `.pdata`입니다. . 동작 스택이 없습니다을 실제로 구현 하는 지침 SETFRAME 보다 선행 되어야 합니다. 모두 해제 지시문 및 규약 확인 매크로에서 해제를 위한 코드를 래핑하는 것이 좋습니다.

자세한 내용은 [MASM (ml64.exe) x64](../../assembler/masm/masm-for-x64-ml64-exe.md)합니다.

## <a name="sample"></a>샘플

### <a name="description"></a>설명

다음 샘플에는 프레임 포인터를 사용 하는 방법을 보여 줍니다.

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

## <a name="see-also"></a>참고자료

[지시문 참조](../../assembler/masm/directives-reference.md)<br/>