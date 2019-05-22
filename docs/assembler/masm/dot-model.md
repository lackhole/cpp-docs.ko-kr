---
title: .MODEL
ms.date: 08/30/2018
f1_keywords:
- .MODEL
helpviewer_keywords:
- .MODEL directive
ms.assetid: 057f00df-1515-4c55-852a-d936c8a34b53
ms.openlocfilehash: c409bf10a2f863c380cda6b4822583ffb3787da6
ms.sourcegitcommit: 61121faf879cc581a4d39e4baccabf7cf1f673a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "65934093"
---
# <a name="model"></a>.MODEL

프로그램 메모리 모델을 초기화합니다.

## <a name="syntax"></a>구문

> .MODEL memorymodel [[, langtype]] [[, stackoption]]

### <a name="parameters"></a>매개 변수

*memorymodel*<br/>
코드 및 데이터 포인터의 크기를 결정하는 필수 매개 변수입니다.

*langtype*<br/>
프로시저 및 공용 기호에 대한 호출 및 명명 규칙을 설정하는 선택적 매개 변수입니다.

*stackoption*<br/>
선택적 매개 변수입니다.

*memorymodel*이 `FLAT`인 경우 *stackoption*이 사용되지 않습니다.

`NEARSTACK`을 지정하면 스택 세그먼트가 데이터와 함께 단일 실제 세그먼트(`DGROUP`)로 그룹화됩니다. 스택 세그먼트 레지스터(`SS`)는 데이터 세그먼트 레지스터(`DS`)와 동일한 주소를 보유하는 것으로 가정합니다. `FARSTACK`은 스택을 `DGROUP`과 그룹화하지 않습니다. 따라서 `SS`는 `DS`와 같지 않습니다.

## <a name="remarks"></a>주의

.`MODEL` [x64용 MASM(ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)에서 사용되지 않습니다.

다음 표에는 16비트 및 32비트 플랫폼을 대상으로 할 때 각 매개 변수에 대해 가능한 값이 나열되어 있습니다.

|매개 변수|32비트 값|16비트 값(이전 16비트 개발에 대한 지원)|
|---------------|--------------------|----------------------------------------------------------------|
|*memorymodel*|`FLAT`|`TINY`, `SMALL`, `COMPACT`, `MEDIUM`, `LARGE`, `HUGE`, `FLAT`|
|*langtype*|`C`, `STDCALL`|`C`, `BASIC`, `FORTRAN`, `PASCAL`, `SYSCALL`, `STDCALL`|
|*stackoption*|사용되지 않음|`NEARSTACK`, `FARSTACK`|

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

## <a name="see-also"></a>참고 항목

[지시문 참조](../../assembler/masm/directives-reference.md)<br/>
