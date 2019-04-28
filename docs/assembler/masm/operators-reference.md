---
title: MASM 연산자 참조
ms.date: 08/30/2018
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), operators reference
- operators [MASM]
ms.assetid: c069cab7-d6b0-4f82-a6ce-0ca3fc7e6428
ms.openlocfilehash: cb97c5dcb640b8d8592d842afd7dbb8cf9d0852c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62210816"
---
# <a name="masm-operators-reference"></a>MASM 연산자 참조

## <a name="arithmetic"></a>산술 연산

||||
|-|-|-|
|[* (곱하기)](operator-multiply.md)|[+ (더하기)](operator-add.md)|[-(빼기 또는 부정)](operator-subtract-2.md)|
|[. (필드)](operator-dot.md)|[/ (나누기)](operator-subtract-1.md)|[&#91;&#93;(인덱스)](operator-brackets.md)|
|[MOD (나머지)](operator-mod.md)|||

## <a name="control-flow"></a>제어 흐름

||||
|-|-|-|
|[\! (논리적 not 런타임)](operator-logical-not-masm-run-time.md)|[\!= (같지 않음 런타임)](operator-not-equal-masm.md)|[&#124;&#124;(런타임 논리 또는)](operator-logical-or.md)|
|[& & (논리적 런타임 및)](operator-logical-and-masm-run-time.md)|[< (런타임 미만)](operator-less-than-masm-run-time.md)|[\<= (작거나 런타임)](operator-less-or-equal-masm-run-time.md)|
|[(같은 런타임) = =](operator-equal-masm-run-time.md)|[> (보다 큰 런타임)](operator-greater-than-masm-run-time.md)|[> = (크거나 런타임)](operator-greater-or-equal-masm-run-time.md)|
|[& (비트 런타임 및)](operator-bitwise-and.md)|||
|[CARRY? (런타임 전달 테스트)](operator-carry-q.md)|[OVERFLOW? (런타임 오버플로 테스트)](operator-overflow-q.md)|[패리티? (런타임 패리티 테스트)](operator-parity-q.md)|
|[SIGN? (런타임 sign 테스트)](operator-sign-q.md)|[ZERO? (0 런타임 테스트)](operator-zero-q.md)||

## <a name="logical-and-shift"></a>논리적 및 Shift

||||
|-|-|-|
|[및 (비트 및)](operator-and.md)|[없습니다 (비트 not)](operator-not.md)|[OR (비트 또는)](operator-or.md)|
|[SHL (shift 왼쪽 비트)](operator-shl.md)|[SHR (오른쪽 shift 비트)](operator-shr.md)|[XOR (배타적 비트 또는)](operator-xor.md)|

## <a name="macro"></a>매크로

||||
|-|-|-|
|[\! (리터럴 문자)](operator-logical-not-masm.md)|[% (텍스트로 처리)](operator-percent.md)||
|[;; (주석으로 처리)](operator-semicolons.md)|[&lt; &gt; (하나의 리터럴로 처리)](operator-literal.md)|[& & (매개 변수 값 대체)](operator-logical-and-masm.md)|

## <a name="miscellaneous"></a>기타

||||
|-|-|-|
|[' ' (문자열로 처리 됨)](operator-single-quote.md)|["" (문자열로 처리 됨)](operator-double-quote.md)||
|: (로컬 레이블 정의)|:: (세그먼트와 오프셋을 등록)|:: (전역 레이블 정의)|
|[; (주석으로 처리)](operator-semicolon.md)|[DUP (반복 선언)](operator-dup.md)||

## <a name="record"></a>녹음

|||
|-|-|
|[마스크 (레코드 또는 필드 비트 마스크 가져오기)](operator-mask.md)|[너비 (레코드 또는 필드 너비 get)](operator-width.md)|

## <a name="relational"></a>관계

||||
|-|-|-|
|[EQ (같음)](operator-eq.md)|[GE (크거나 같음)](operator-ge.md)|[GT (보다 큼)](operator-gt.md)|
|[LE (보다 작거나)](operator-le.md)|[LT (보다 작음)](operator-lt.md)|[NE (같지 않음)](operator-ne.md)|

## <a name="segment"></a>세그먼트

|||
|-|-|
|[: (재정의 세그먼트)](operator-colon.md)|:: (세그먼트와 오프셋을 등록)|
|[IMAGEREL (이미지 상대 오프셋)](operator-imagerel.md)|[LROFFSET (로더 오프셋을 해결 하는 데 사용)](operator-lroffset.md)|
|[오프셋 (세그먼트 상대 오프셋)](operator-offset.md)|[SECTIONREL (섹션 상대 오프셋)](operator-sectionrel.md)|
|[SEG (get 세그먼트)](operator-seg.md)||

## <a name="type"></a>형식

||||
|-|-|-|
|[높음 (가장 낮은 16 비트의 상위 8 비트)](operator-high.md)|[HIGH32 (64 비트의 상위 32 비트)](operator-high32.md)|[HIGHWORD (가장 낮은 32 비트의 상위 16 비트)](operator-highword.md)|
|[길이 (배열의 요소 수)](operator-length.md)|[LENGTHOF (배열의 요소 수)](operator-lengthof.md)|[낮음 (낮은 8 비트)](operator-low.md)|
|[LOW32 (낮은 32 비트)](operator-low32.md)|[LOWWORD (낮은 16 비트)](operator-lowword.md)|[OPATTR (get 인수 형식 정보)](operator-opattr.md)|
|[PTR (포인터와 형식으로)](operator-ptr.md)|[SHORT (mark 짧은 레이블 형식)](operator-short.md)|[크기 (형식 또는 변수의 크기)](operator-size.md)|
|[SIZEOF (형식 또는 변수의 크기)](operator-sizeof.md)|[이 (현재 위치)](operator-this.md)|[유형 (가져오기 식 유형)](operator-type.md)|
|[. 형식 (get 인수 형식 정보)](operator-dot-type.md)|||

## <a name="see-also"></a>참고자료

[Microsoft 매크로 어셈블러 참조](microsoft-macro-assembler-reference.md)<br/>
