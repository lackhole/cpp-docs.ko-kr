---
title: .MODEL
ms.date: 11/05/2019
f1_keywords:
- .MODEL
helpviewer_keywords:
- .MODEL directive
ms.assetid: 057f00df-1515-4c55-852a-d936c8a34b53
ms.openlocfilehash: bfc114a6e71c0eb0ae70005c2657871b6c9e9692
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398106"
---
# <a name="model-32-bit-masm"></a>.MODEL (32-bit MASM)

프로그램 메모리 모델을 초기화합니다. (32-bit MASM only.)

## <a name="syntax"></a>구문

> **.MODEL** *memory-model* ⟦ __,__ *language-type*⟧ ⟦ __,__ *stack-option*⟧

### <a name="parameters"></a>매개 변수

*memory-model*\
코드 및 데이터 포인터의 크기를 결정하는 필수 매개 변수입니다.

*language-type*\
프로시저 및 공용 기호에 대한 호출 및 명명 규칙을 설정하는 선택적 매개 변수입니다.

*stack-option*\
선택적 매개 변수입니다.

*stack-option* is not used if *memory-model* is **FLAT**.

Specifying **NEARSTACK** groups the stack segment into a single physical segment (**DGROUP**) along with data. The stack segment register (**SS**) is assumed to hold the same address as the data segment register (**DS**). **FARSTACK** does not group the stack with **DGROUP**; thus **SS** does not equal **DS**.

## <a name="remarks"></a>주의

**.MODEL** is not used in [MASM for x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

다음 표에는 16비트 및 32비트 플랫폼을 대상으로 할 때 각 매개 변수에 대해 가능한 값이 나열되어 있습니다.

|매개 변수|32비트 값|16비트 값(이전 16비트 개발에 대한 지원)|
|---------------|--------------------|----------------------------------------------------------------|
|*memory-model*|**FLAT**|**TINY**, **SMALL**, **COMPACT**, **MEDIUM**, **LARGE**, **HUGE**, **FLAT**|
|*language-type*|**C**, **STDCALL**|**C**, **BASIC**, **FORTRAN**, **PASCAL**, **SYSCALL**, **STDCALL**|
|*stack-option*|사용되지 않음|**NEARSTACK**, **FARSTACK**|

## <a name="code"></a>코드

MASM 관련 샘플의 경우 [Visual C++ 샘플 및 Visual Studio 2010용 관련 설명서](https://go.microsoft.com/fwlink/p/?linkid=178749)에서 컴파일러 샘플을 다운로드합니다.

다음 예제에서는 `.MODEL` 지시문을 사용하는 방법을 보여줍니다.

## <a name="example"></a>예제

```asm
; file simple.asm
; For x86 (32-bit), assemble with debug information:
;   ml -c -Zi simple.asm
; For x64 (64-bit), assemble with debug information:
;   ml64 -c -DX64 -Zi simple.asm
;
; In this sample, the 'X64' define excludes source not used
;  when targeting the x64 architecture

ifndef X64
.686p
.XMM
.model flat, C
endif

.data
; user data

.code
; user code

fxn PROC public
  xor eax, eax ; zero function return value
  ret
fxn ENDP

end
```

## <a name="see-also"></a>참조

[지시문 참조](../../assembler/masm/directives-reference.md)
