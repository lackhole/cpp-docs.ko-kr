---
title: .PUSHREG
ms.date: 08/30/2018
f1_keywords:
- .PUSHREG
helpviewer_keywords:
- .PUSHREG directive
ms.assetid: e0c83758-dfed-40ea-afe6-cb833c8d2d30
ms.openlocfilehash: 19e36f1c0b073c5b174ea9acb0f1eaac7d771c46
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62203982"
---
# <a name="pushreg"></a>.PUSHREG

생성 된 `UWOP_PUSH_NONVOL` 현재 프롤로그의 오프셋을 사용 하 여 번호를 지정 된 등록에 대 한 코드 항목을 해제 합니다.

## <a name="syntax"></a>구문

> . PUSHREG 등록

## <a name="remarks"></a>설명

. PUSHREG 하면 ml64.exe 프레임 함수 해제 될 때 및에서 확장 하는 프롤로그 내 에서만 허용 됩니다 방법을 지정할 수는 [PROC](../../assembler/masm/proc.md) 프레임 선언을 [합니다. 프롤로그 끝](../../assembler/masm/dot-endprolog.md) 지시문입니다. 이러한 지시문 코드를 생성 하지 않습니다. 만 생성할 `.xdata` 고 `.pdata`입니다. . 동작 스택이 없습니다을 실제로 구현 하는 지침 PUSHREG 보다 선행 되어야 합니다. 모두 해제 지시문 및 규약 확인 매크로에서 해제를 위한 코드를 래핑하는 것이 좋습니다.

자세한 내용은 [MASM (ml64.exe) x64](../../assembler/masm/masm-for-x64-ml64-exe.md)합니다.

## <a name="sample"></a>샘플

### <a name="description"></a>설명

다음 샘플에는 비휘발성 tegisters 푸시하는 방법을 보여 줍니다.

### <a name="code"></a>코드

```asm
; ml64 ex1.asm /link /entry:Example1 /SUBSYSTEM:CONSOLE
_text SEGMENT
Example1 PROC FRAME
   push r10
.pushreg r10
   push r15
.pushreg r15
   push rbx
.pushreg rbx
   push rsi
.pushreg rsi
.endprolog
   ; rest of function ...
   ret
Example1 ENDP
_text ENDS
END
```

## <a name="see-also"></a>참고자료

[지시문 참조](../../assembler/masm/directives-reference.md)<br/>