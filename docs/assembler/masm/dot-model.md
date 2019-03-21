---
title: .MODEL
ms.date: 08/30/2018
f1_keywords:
- .MODEL
helpviewer_keywords:
- .MODEL directive
ms.assetid: 057f00df-1515-4c55-852a-d936c8a34b53
ms.openlocfilehash: c3917fea0f13e54d5f8f73599a2d28482bb6d259
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57743943"
---
# <a name="model"></a>.MODEL

프로그램 메모리 모델을 초기화합니다.

## <a name="syntax"></a>구문

> . 모델 memorymodel [[, langtype]] [[, stackoption]]

### <a name="parameters"></a>매개 변수

*memorymodel*<br/>
코드 및 데이터에 대 한 포인터의 크기를 결정 하는 필수 매개 변수입니다.

*langtype*<br/>
프로시저 및 공용 기호에 대 한 호출 및 명명 규칙을 설정 하는 선택적 매개 변수입니다.

*stackoption*<br/>
선택적 매개 변수입니다.

*stackoption* 경우에 사용 되지 않습니다 *memorymodel* 는 `FLAT`합니다.

지정 `NEARSTACK` 스택 세그먼트를 단일 실제 세그먼트로 그룹화 (`DGROUP`) 데이터와 함께 합니다. 스택 세그먼트 레지스터 (`SS`)는 데이터 세그먼트 레지스터와 동일한 주소를 저장할로 간주 됩니다 (`DS`). `FARSTACK` 스택 그룹화 하지 않습니다 `DGROUP`; 따라서 `SS` 같지 `DS`합니다.

## <a name="remarks"></a>설명

.`MODEL` 사용 되지 않습니다 [MASM (ml64.exe) x64](../../assembler/masm/masm-for-x64-ml64-exe.md)합니다.

다음 표에서 각 매개 변수에 가능한 값은 16 비트 및 32 비트 플랫폼을 대상으로 하는 경우:

|매개 변수|32 비트 값|16 비트 값 (이전 16 비트 개발에 대 한 지원)|
|---------------|--------------------|----------------------------------------------------------------|
|*memorymodel*|`FLAT`|`TINY`, `SMALL`, `COMPACT`, `MEDIUM`, `LARGE`, `HUGE`, `FLAT`|
|*langtype*|`C`, `STDCALL`|`C`, `BASIC`, `FORTRAN`, `PASCAL`, `SYSCALL`, `STDCALL`|
|*stackoption*|사용되지 않음|`NEARSTACK`, `FARSTACK`|

## <a name="code"></a>코드

MASM 관련 샘플에서 컴파일러 예제를 다운로드할 [Visual c + + 샘플 및 Visual Studio 2010에 대 한 관련 문서](http://go.microsoft.com/fwlink/p/?linkid=178749)합니다.

다음 예제에서는 사용 된 `.MODEL` 지시문입니다.

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

## <a name="see-also"></a>참고자료

[지시문 참조](../../assembler/masm/directives-reference.md)<br/>
