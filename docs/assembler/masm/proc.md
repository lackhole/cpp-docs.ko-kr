---
title: PROC
ms.date: 08/30/2018
f1_keywords:
- PROC
helpviewer_keywords:
- PROC directive
ms.assetid: ee5bb6b6-fa15-4d73-b0cf-e650178539a9
ms.openlocfilehash: e7931c97570c0fefcacb0123d75934867793fba4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62210536"
---
# <a name="proc"></a>PROC

호출 프로시저 블록의 시작 및 끝 표시 *레이블*합니다. 블록의 문에서 호출할 수는 **호출** 명령 또는 [INVOKE](../../assembler/masm/invoke.md) 지시문입니다.

## <a name="syntax"></a>구문

> *레이블을* PROC [[*거리*]] [[*langtype*]] [[*가시성*]] [[\<*prologuearg*>]] [[ 사용 하 여 *reglist*]] [[합니다 *매개 변수* [[:*태그*]]]...<br/>
> [[FRAME [[:*ehandler-address*]] ]]<br/>
> *statements*<br/>
> *label* ENDP

## <a name="remarks"></a>설명

[[프레임 [[:*ehandler 주소*]]]] ml64.exe를 사용 하 여만 유효 하 고 MASM.pdata 함수 테이블 항목을 생성 하 여 함수의 구조적에 대 한.xdata에서 정보를 해제 하면 예외 처리 동작을 해제 합니다.

경우는 **프레임** 특성을 사용 하 여 따라야는 [합니다. 프롤로그 끝](../../assembler/masm/dot-endprolog.md) 지시문입니다.

참조 [MASM (ml64.exe) x64](../../assembler/masm/masm-for-x64-ml64-exe.md) ml64.exe를 사용 하 여 대 한 자세한 내용은 합니다.

## <a name="example"></a>예제

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

위의 코드는 다음 함수 테이블 내보내고 정보를 해제 됩니다.

```Output
FileHeader->Machine 34404
Dumping Unwind Information for file ex2.exe

.pdata entry 1 0x00001000 0x00001023

  Unwind data: 0x00002000

    Unwind version: 1
    Unwind Flags: None
    Size of prologue: 0x08
    Count of codes: 3
    Frame register: rbp
    Frame offset: 0x0
    Unwind codes:

      Code offset: 0x08, SET_FPREG, register=rbp, offset=0x00
      Code offset: 0x05, ALLOC_SMALL, size=0x10
      Code offset: 0x01, PUSH_NONVOL, register=rbp
```

## <a name="see-also"></a>참고자료

[지시문 참조](../../assembler/masm/directives-reference.md)<br/>