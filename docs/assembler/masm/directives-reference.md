---
title: 지시문 참조
ms.date: 08/30/2018
f1_keywords:
- Directives Reference
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), directives reference
ms.assetid: da6efcd1-18f7-41de-81cd-a002a02f9a22
ms.openlocfilehash: 12effa33b80403f3e8f1a130ac53a75b02cfefff
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398780"
---
# <a name="directives-reference"></a>지시문 참조

## <a name="x64"></a>x64

||||
|-|-|-|
|[.ALLOCSTACK](../../assembler/masm/dot-allocstack.md)|[.ENDPROLOG](../../assembler/masm/dot-endprolog.md)|[PROC](../../assembler/masm/proc.md)|
|[.PUSHFRAME](../../assembler/masm/dot-pushframe.md)|[.PUSHREG](../../assembler/masm/dot-pushreg.md)|[.SAVEREG](../../assembler/masm/dot-savereg.md)|
|[.SAVEXMM128](../../assembler/masm/dot-savexmm128.md)|[.SETFRAME](../../assembler/masm/dot-setframe.md)||

### <a name="code-labels"></a>코드 레이블

|||
|-|-|
|[않아](../../assembler/masm/align-masm.md)|[EVEN](../../assembler/masm/even.md)|
|[레이블](../../assembler/masm/label-masm.md)|[ORG](../../assembler/masm/org.md)|

### <a name="conditional-assembly"></a>조건부 어셈블리

||||
|-|-|-|
|[사람이](../../assembler/masm/else-masm.md)|[그렇지](../../assembler/masm/elseif-masm.md)|[ELSEIF2](../../assembler/masm/elseif2.md)|
|[때](../../assembler/masm/if-masm.md)|[IF2](../../assembler/masm/if2.md)|[IFB](../../assembler/masm/ifb.md)/[ifnb](../../assembler/masm/ifnb.md)|
|[IFDEF](../../assembler/masm/ifdef.md)/[IFNDEF](../../assembler/masm/ifndef.md)|[IFDIF](../../assembler/masm/ifdif.md)/[IFDIF&#91;&#91;I&#93; ](../../assembler/masm/ifdif.md)|[IFE](../../assembler/masm/ife.md)|
|[Ifidn](../../assembler/masm/ifidn.md)/[ifidn&#91;&#91;I&#93; ](../../assembler/masm/ifidn.md)|||

### <a name="conditional-control-flow"></a>조건부 제어 흐름

||||
|-|-|-|
|[.BREAK](../../assembler/masm/dot-break.md)|[.CONTINUE](../../assembler/masm/dot-continue.md)|[.ELSE](../../assembler/masm/dot-else.md)|
|[. 그렇지](../../assembler/masm/dot-if.md)|[.ENDIF](../../assembler/masm/dot-endif.md)|[.ENDW](../../assembler/masm/dot-endw.md)|
|[.IF](../../assembler/masm/dot-if.md)|[.REPEAT](../../assembler/masm/dot-repeat.md)|[.UNTIL](../../assembler/masm/dot-until.md)|
|[.UNTILCXZ](../../assembler/masm/dot-untilcxz.md)|[.WHILE](../../assembler/masm/dot-while.md)||

### <a name="conditional-error"></a>조건부 오류

||||
|-|-|-|
|[.ERR](../../assembler/masm/dot-err.md)|[.ERR2](../../assembler/masm/dot-err2.md)|[.ERRB](../../assembler/masm/dot-errb.md)|
|[.ERRDEF](../../assembler/masm/dot-errdef.md)|[. .ERRDIF](../../assembler/masm/dot-errdif.md)/[. .ERRDIF&#91;I&#93; &#91;&#93; ](../../assembler/masm/dot-errdif.md)|[.ERRE](../../assembler/masm/dot-erre.md)|
|[. ERRIDN](../../assembler/masm/dot-erridn.md)/[입니다. ERRIDN&#91;&#91;I&#93; ](../../assembler/masm/dot-erridn.md)|[.ERRNB](../../assembler/masm/dot-errnb.md)|[.ERRNDEF](../../assembler/masm/dot-errndef.md)|
|[.ERRNZ](../../assembler/masm/dot-errnz.md)|||

### <a name="data-allocation"></a>데이터 할당

||||
|-|-|-|
|[않아](../../assembler/masm/align-masm.md)|[BYTE](../../assembler/masm/byte-masm.md)/[SBYTE](../../assembler/masm/sbyte-masm.md)|[DWORD](../../assembler/masm/dword.md)/[sdword](../../assembler/masm/sdword.md)|
|[EVEN](../../assembler/masm/even.md)|[FWORD](../../assembler/masm/fword.md)|[레이블](../../assembler/masm/label-masm.md)|
|[ORG](../../assembler/masm/org.md)|[QWORD](../../assembler/masm/qword.md)|[REAL4](../../assembler/masm/real4.md)|
|[REAL8](../../assembler/masm/real8.md)|[REAL10](../../assembler/masm/real10.md)|[TBYTE](../../assembler/masm/tbyte.md)|
|[단어](../../assembler/masm/word.md)/[소드](../../assembler/masm/sword.md)|||

### <a name="equates"></a>매월

||||
|-|-|-|
|[=](../../assembler/masm/equal.md)|[EQU](../../assembler/masm/equ.md)|[TEXTEQU](../../assembler/masm/textequ.md)|

### <a name="listing-control"></a>목록 컨트롤

||||
|-|-|-|
|[.CREF](../../assembler/masm/dot-cref.md)|[.LIST](../../assembler/masm/dot-list.md)|[.LISTALL](../../assembler/masm/dot-listall.md)|
|[.LISTIF](../../assembler/masm/dot-listif.md)|[.LISTMACRO](../../assembler/masm/dot-listmacro.md)|[.LISTMACROALL](../../assembler/masm/dot-listmacroall.md)|
|[.NOCREF](../../assembler/masm/dot-nocref.md)|[.NOLIST](../../assembler/masm/dot-nolist.md)|[.NOLISTIF](../../assembler/masm/dot-nolistif.md)|
|[.NOLISTMACRO](../../assembler/masm/dot-nolistmacro.md)|[PAGE](../../assembler/masm/page.md)|[SUBTITLE](../../assembler/masm/subtitle.md)|
|[.TFCOND](../../assembler/masm/dot-tfcond.md)|[TITLE](../../assembler/masm/title.md)||

### <a name="macros"></a>매크로

||||
|-|-|-|
|[ENDM](../../assembler/masm/endm.md)|[EXITM](../../assembler/masm/exitm.md)|[GOTO](../../assembler/masm/goto-masm.md)|
|[로컬](../../assembler/masm/local-masm.md)|[MACRO](../../assembler/masm/macro.md)|[PURGE](../../assembler/masm/purge.md)|

### <a name="miscellaneous"></a>기타

||||
|-|-|-|
|[앤티앨리어스](../../assembler/masm/alias-masm.md)|[ASSUME](../../assembler/masm/assume.md)|[주석의](../../assembler/masm/comment-masm.md)|
|[ECHO](../../assembler/masm/echo.md)|[종단](../../assembler/masm/end-masm.md)|[.FPO](../../assembler/masm/dot-fpo.md)|
|[되어야](../../assembler/masm/include-masm.md)|[INCLUDELIB](../../assembler/masm/includelib-masm.md)|[MMWORD](../../assembler/masm/mmword.md)|
|[OPTION](../../assembler/masm/option-masm.md)|[POPCONTEXT](../../assembler/masm/popcontext.md)|[PUSHCONTEXT](../../assembler/masm/pushcontext.md)|
|[.RADIX](../../assembler/masm/dot-radix.md)|[.SAFESEH](../../assembler/masm/dot-safeseh.md)|[XMMWORD](../../assembler/masm/xmmword.md)|
|[YMMWORD](../../assembler/masm/ymmword.md)|||

### <a name="procedures"></a>절차

||||
|-|-|-|
|[ENDP](../../assembler/masm/endp.md)|[INVOKE](../../assembler/masm/invoke.md)|[PROC](../../assembler/masm/proc.md)|
|[PROTO](../../assembler/masm/proto.md)|||

### <a name="processor"></a>프로세서

||||
|-|-|-|
|[.386](../../assembler/masm/dot-386.md)|[.386P](../../assembler/masm/dot-386p.md)|[.387](../../assembler/masm/dot-387.md)|
|[.486](../../assembler/masm/dot-486.md)|[.486P](../../assembler/masm/dot-486p.md)|[.586](../../assembler/masm/dot-586.md)|
|[.586P](../../assembler/masm/dot-586p.md)|[.686](../../assembler/masm/dot-686.md)|[.686P](../../assembler/masm/dot-686p.md)|
|[.K3D](../../assembler/masm/dot-k3d.md)|[.MMX](../../assembler/masm/dot-mmx.md)|[.XMM](../../assembler/masm/dot-xmm.md)|

### <a name="repeat-blocks"></a>반복 블록

||||
|-|-|-|
|[ENDM](../../assembler/masm/endm.md)|[에 대 한](../../assembler/masm/for-masm.md)|[FORC](../../assembler/masm/forc.md)|
|[GOTO](../../assembler/masm/goto-masm.md)|[REPEAT](../../assembler/masm/repeat.md)|[진행](../../assembler/masm/while-masm.md)|

### <a name="scope"></a>범위

||||
|-|-|-|
|[COMM](../../assembler/masm/comm.md)|[시키거나](../../assembler/masm/extern-masm.md)|[EXTERNDEF](../../assembler/masm/externdef.md)|
|[INCLUDELIB](../../assembler/masm/includelib-masm.md)|[공개적](../../assembler/masm/public-masm.md)||

### <a name="segment"></a>세그먼트가

||||
|-|-|-|
|[.ALPHA](../../assembler/masm/dot-alpha.md)|[ASSUME](../../assembler/masm/assume.md)|[.DOSSEG](../../assembler/masm/dot-dosseg.md)|
|[종단](../../assembler/masm/end-masm.md)|[종료](../../assembler/masm/ends-masm.md)|[GROUP](../../assembler/masm/group.md)|
|[SEGMENT](../../assembler/masm/segment.md)|[.SEQ](../../assembler/masm/dot-seq.md)||

### <a name="simplified-segment"></a>단순화 된 세그먼트

||||
|-|-|-|
|[.CODE](../../assembler/masm/dot-code.md)|[.CONST](../../assembler/masm/dot-const.md)|[.DATA](../../assembler/masm/dot-data.md)|
|[.DATA?](../../assembler/masm/dot-data-q.md)|[.DOSSEG](../../assembler/masm/dot-dosseg.md)|[.EXIT](../../assembler/masm/dot-exit.md)|
|[.FARDATA](../../assembler/masm/dot-fardata.md)|[.FARDATA?](../../assembler/masm/dot-fardata-q.md)|[.MODEL](../../assembler/masm/dot-model.md)|
|[.STACK](../../assembler/masm/dot-stack.md)|[.STARTUP](../../assembler/masm/dot-startup.md)||

### <a name="string"></a>String

|||
|-|-|
|[CATSTR](../../assembler/masm/catstr.md)|[INSTR](../../assembler/masm/instr.md)|
|[SIZESTR](../../assembler/masm/sizestr.md)|[SUBSTR](../../assembler/masm/substr.md)|

### <a name="structure-and-record"></a>구조 및 레코드

||||
|-|-|-|
|[종료](../../assembler/masm/ends-masm.md)|[기록은](../../assembler/masm/record-masm.md)|[구조체](../../assembler/masm/struct-masm.md)|
|[였](../../assembler/masm/typedef-masm.md)|[UNION](../../assembler/masm/union.md)||

## <a name="see-also"></a>참고 항목

[Microsoft 매크로 어셈블러 참조](../../assembler/masm/microsoft-macro-assembler-reference.md)
