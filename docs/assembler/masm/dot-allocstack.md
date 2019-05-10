---
title: .ALLOCSTACK
ms.date: 08/30/2018
f1_keywords:
- .ALLOCSTACK
helpviewer_keywords:
- .ALLOCSTACK directive
ms.assetid: 9801594b-7ac2-4df2-a49d-07d9dd9af99e
ms.openlocfilehash: b92db3d03bb5c45e67473cd4085f2369698f6b42
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62185655"
---
# <a name="allocstack"></a>.ALLOCSTACK

생성 된 **UWOP_ALLOC_SMALL** 또는 **UWOP_ALLOC_LARGE** 프롤로그의 현재 오프셋에 대 한 지정된 된 크기를 사용 하 여 합니다.

## <a name="syntax"></a>구문

> . ALLOCSTACK 크기

## <a name="remarks"></a>설명

지정된 된 크기에 대 한 가장 효율적인 인코딩 MASM를 선택 합니다.

. ALLOCSTACK ml64.exe 프레임 함수 해제 하는 방법을 지정할 수 있습니다 및에서 확장 하는 프롤로그 내 에서만 허용 됩니다 합니다 [PROC](../../assembler/masm/proc.md) 프레임 선언을 [합니다. 프롤로그 끝](../../assembler/masm/dot-endprolog.md) 지시문입니다. 이러한 지시문 코드를 생성 하지 않습니다. 만 생성할 `.xdata` 고 `.pdata`입니다. . 동작 스택이 없습니다을 실제로 구현 하는 지침 ALLOCSTACK 보다 선행 되어야 합니다. 모두 해제 지시문 및 규약 확인 매크로에서 해제를 위한 코드를 래핑하는 것이 좋습니다.

`size` 피연산자를 8의 배수 여야 합니다.

자세한 내용은 (영문)을 참조 하세요 [MASM (ml64.exe) x64](../../assembler/masm/masm-for-x64-ml64-exe.md)합니다.

## <a name="sample"></a>샘플

다음 샘플에는 해제/예외 처리기를 지정 하는 방법을 보여 줍니다.

```asm
; ml64 ex3.asm /link /entry:Example1  /SUBSYSTEM:Console
text SEGMENT
PUBLIC Example3
PUBLIC Example3_UW
Example3_UW PROC NEAR
   ; exception/unwind handler body

   ret 0

Example3_UW ENDP

Example3 PROC FRAME : Example3_UW

   sub rsp, 16
.allocstack 16

.endprolog

   ; function body
    add rsp, 16
   ret 0

Example3 ENDP
text ENDS
END
```

## <a name="see-also"></a>참고자료

[지시문 참조](../../assembler/masm/directives-reference.md)<br/>