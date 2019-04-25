---
title: ARM 어셈블러 진단 메시지
ms.date: 08/30/2018
f1_keywords:
- A2193
- A2196
- A2202
- A2513
- A2557
- A4228
- A4508
- A4509
helpviewer_keywords:
- A2193
- A2196
- A2202
- A2513
- A2557
- A4228
- A4508
- A4509
ms.assetid: 52b38267-6023-4bdc-a0ef-863362f48eec
ms.openlocfilehash: 867ef50065c6ed63a4da6d37523bd5a1f3cbadba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62167845"
---
# <a name="arm-assembler-diagnostic-messages"></a>ARM 어셈블러 진단 메시지

Microsoft ARM 어셈블러 (*armasm*)가 발견 될 때 진단 경고 및 오류를 내보냅니다. 이 문서에서는 가장 일반적으로 발생 한 메시지를 설명 합니다.

## <a name="syntax"></a>구문

> <em>filename</em>**(**<em>line-number</em>**) :** \[**error**|**warning**] **A**<em>number</em>**:** *message*

## <a name="diagnostic-messages---errors"></a>진단 메시지-오류

> A2193:이 명령은 예기치 않은 동작이 생성

ARM 아키텍처는이 명령이 실행 될 때 일어나 보장할 수 없습니다.  이 명령의 잘 정의 된 양식에 대 한 자세한 내용은 참조는 [ARM 아키텍처 참조 설명서](http://go.microsoft.com/fwlink/p/?linkid=246464)합니다.

```asm
    ADD r0, r8, pc         ; A2193: this instruction generates unpredictable behavior
```

> A2196: 16 비트에서 명령 인코딩할 수 없습니다

지정된 된 명령은 16 비트 Thumb 명령으로 인코딩할 수 없습니다.  32 비트 명령에 지정 하거나 대상 레이블에 범위의 16 비트 명령으로 실행할 코드를 다시 정렬 합니다.

어셈블러는 32 비트 분기를 인코딩할 수는 16 비트 분기를 인코딩하고이 오류로 인해 실패 시도할 수 있습니다. 사용 하 여이 문제를 해결할 수 있습니다는 `.W` 지정자를 32 비트 분기를 명시적으로 표시를 합니다.

```asm
    ADD.N r0, r1, r2      ; A2196: instruction cannot be encoded in 16 bits

    B.W label             ; OK
    B.N label             ; A2196: instruction cannot be encoded in 16 bits
    SPACE 10000
label
```

> A2202: THUMB 지역에서 사용할 수 없습니다 사전 UAL 명령 구문

Thumb 코드 통합 어셈블러 언어 (UAL) 구문을 사용 해야 합니다.  오래 된 구문을 사용할 수 없습니다.

```asm
    ADDEQS r0, r1         ; A2202: Pre-UAL instruction syntax not allowed in THUMB region
    ADDSEQ r0, r1         ; OK
```

> A2513: 회전은 짝수 여야 합니다.

ARM 모드에서 상수를 지정 하는 것에 대 한 대체 구문이 있습니다.  작성 하는 대신 `#<const>`를 작성할 수 있습니다 `#<byte>,#<rot>`에 값을 회전 하 여 얻은 상수 값을 나타내는 `<byte>` 오른쪽으로 `<rot>`입니다.  이 구문을 사용 하는 경우에 값을 확인 해야 `<rot>` 도 합니다.

```asm
    MOV r0, #4, #2       ; OK
    MOV r0, #4, #1       ; A2513: Rotation must be even
```

> A2557: 쓰기 저장 하는 바이트 수가 잘못 되었습니다

NEON 구조에 로드 및 저장 지침 (`VLDn`, `VSTn`)에 기본 레지스터에 쓰기 저장을 지정 하기 위한 구문은 대체 합니다.  느낌표 (!) 주소 뒤에 배치 하는 대신 기본 등록에 추가할 오프셋을 나타내는 즉 치 값을 지정할 수 있습니다.  이 구문을 사용 하는 경우 로드 되거나 해당 명령에 의해 저장 된 바이트 수를 정확 하 게 지정 해야 합니다.

```asm
    VLD1.8 {d0-d3}, [r0]!         ; OK
    VLD1.8 {d0-d3}, [r0], #32     ; OK
    VLD1.8 {d0-d3}, [r0], #100    ; A2557: Incorrect number of bytes to write back
```

## <a name="diagnostic-messages---warnings"></a>진단 메시지-경고

> A4228: 맞춤 값 초과 영역 맞춤; 맞춤 보장 되지 않습니다

에 지정 된 맞춤을 `ALIGN` 지시문 묶는 맞춤 보다 크면 `AREA`합니다.  결과적으로, 어셈블러는 보장할 수 없습니다는 `ALIGN` 지시문이 적용 됩니다.

이 해결 하려면에서 지정할 수 있습니다는 `AREA` 지시문을 `ALIGN` 원하는 맞춤 보다 크거나 같은 특성이 있습니다.

```asm
AREA |.myarea1|
ALIGN 8           ; A4228: Alignment value exceeds AREA alignment; alignment not guaranteed

AREA |.myarea2|,ALIGN=3
ALIGN 8           ; OK
```

> A4508: 이 회전된 상수 사용은 사용 되지 않습니다.

ARM 모드에서 상수를 지정 하는 것에 대 한 대체 구문이 있습니다.  작성 하는 대신 `#<const>`를 작성할 수 있습니다 `#<byte>,#<rot>`에 값을 회전 하 여 얻은 상수 값을 나타내는 `<byte>` 오른쪽으로 `<rot>`입니다.  일부 컨텍스트에서 ARM은 않으며 이러한 회전된 상수 사용 이러한 경우에 사용할 기본 `#<const>` 구문 대신 합니다.

```asm
    ANDS r0, r0, #1                ; OK
    ANDS r0, r0, #4, #2            ; A4508: Use of this rotated constant is deprecated
```

> A4509: 조건부 명령의이 폼은 사용 되지 않습니다.

ARMv8 아키텍처에서 ARM으로 이러한 형태의 조건부 명령에 사용 되지 않습니다. 조건부 분기를 사용 하는 코드를 변경 하는 것이 좋습니다. 조건부 지침 여전히 지를 확인 하려면 참조는 [ARM 아키텍처 참조 설명서](http://go.microsoft.com/fwlink/p/?linkid=246464)합니다.

이 경고가 때 내보낸 합니다 **-oldit** 명령줄 스위치를 사용 합니다.

```asm
    ADDEQ r0, r1, r8              ; A4509: This form of conditional instruction is deprecated
```

## <a name="see-also"></a>참고자료

[ARM 어셈블러 명령줄 참조](../../assembler/arm/arm-assembler-command-line-reference.md)<br/>
[ARM 어셈블리 지시문](../../assembler/arm/arm-assembler-directives.md)<br/>
