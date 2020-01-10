---
title: MASM 연산자 참조
ms.date: 12/17/2019
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), operators reference
- operators [MASM]
ms.assetid: c069cab7-d6b0-4f82-a6ce-0ca3fc7e6428
ms.openlocfilehash: c0059ab1b0204b79e040d18bd5aa88145775ebcd
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75318763"
---
# <a name="masm-operators-reference"></a>MASM 연산자 참조

## <a name="arithmetic"></a>산술 연산

||||
|-|-|-|
|[* (곱하기)](operator-multiply.md)|[+ (추가)](operator-add.md)|[-(빼기 또는 부정)](operator-subtract-2.md)|
|[. 필드가](operator-dot.md)|[/(나누기)](operator-subtract-1.md)|[&#91;&#93;인덱싱할](operator-brackets.md)|
|[MOD (나머지)](operator-mod.md)|||

## <a name="control-flow"></a>제어 흐름

||||
|-|-|-|
|[\! (런타임 논리적 not)](operator-logical-not-masm-run-time.md)|[\!= (런타임이 같지 않음)](operator-not-equal-masm.md)|[&#124;&#124;(런타임 논리적 or)](operator-logical-or.md)|
|[& & (런타임 논리적 and)](operator-logical-and-masm-run-time.md)|[< (런타임 보다 작음)](operator-less-than-masm-run-time.md)|[\<= (런타임 낮음 또는 같음)](operator-less-or-equal-masm-run-time.md)|
|[= = (런타임 같음)](operator-equal-masm-run-time.md)|[> (런타임 보다 큼)](operator-greater-than-masm-run-time.md)|[> = (런타임 보다 크거나 같음)](operator-greater-or-equal-masm-run-time.md)|
|[& (런타임 비트 and)](operator-bitwise-and.md)|||
|[수행? (런타임 운반 테스트)](operator-carry-q.md)|[오버플로? (런타임 오버플로 테스트)](operator-overflow-q.md)|[대응? (런타임 패리티 테스트)](operator-parity-q.md)|
|[로그인? (런타임 서명 테스트)](operator-sign-q.md)|[반환? (런타임 제로 테스트)](operator-zero-q.md)||

## <a name="logical-and-shift"></a>논리적 and 시프트

||||
|-|-|-|
|[And (비트 and)](operator-and.md)|[NOT (비트 not)](operator-not.md)|[OR (비트 or)](operator-or.md)|
|[SHL (왼쪽 시프트 비트)](operator-shl.md)|[SHR (오른쪽 시프트 비트)](operator-shr.md)|[XOR (배타적 비트 or)](operator-xor.md)|

## <a name="macro"></a>매크로

||||
|-|-|-|
|[\! (문자 리터럴)](operator-logical-not-masm.md)|[% (텍스트로 처리)](operator-percent.md)||
|[;; (주석으로 처리)](operator-semicolons.md)|[&lt; &gt; (한 리터럴로 처리)](operator-literal.md)|[& & (대체 매개 변수 값)](operator-logical-and-masm.md)|

## <a name="miscellaneous"></a>기타

||||
|-|-|-|
|[' ' (문자열로 처리)](operator-single-quote.md)|["" (문자열로 처리)](operator-double-quote.md)||
|: (로컬 레이블 정의)|:: (세그먼트 및 오프셋 등록)|:: (전역 레이블 정의)|
|[; (주석으로 처리)](operator-semicolon.md)|[DUP (반복 선언)](operator-dup.md)||

## <a name="record"></a>녹음

|||
|-|-|
|[마스크 (레코드 또는 필드 비트 마스크 가져오기)](operator-mask.md)|[WIDTH (레코드 또는 필드 너비 가져오기)](operator-width.md)|

## <a name="relational"></a>관계

||||
|-|-|-|
|[EQ (같음)](operator-eq.md)|[GE (크거나 같음)](operator-ge.md)|[GT (보다 큼)](operator-gt.md)|
|[LE (작거나 같음)](operator-le.md)|[LT (보다 작음)](operator-lt.md)|[NE (같지 않음)](operator-ne.md)|

## <a name="segment"></a>세그먼트

|||
|-|-|
|[: (세그먼트 재정의)](operator-colon.md)|:: (세그먼트 및 오프셋 등록)|
|[IMAGEREL (이미지 상대 오프셋)](operator-imagerel.md)|[LROFFSET (로더가 확인 된 오프셋)](operator-lroffset.md)|
|[OFFSET (세그먼트 상대 오프셋)](operator-offset.md)|[섹션 REL (섹션 상대 오프셋)](operator-sectionrel.md)|
|[SEG (세그먼트 가져오기)](operator-seg.md)||

## <a name="type"></a>형식

||||
|-|-|-|
|[높음 (가장 낮은 16 비트의 상위 8 비트)](operator-high.md)|[HIGH32 (64 비트의 상위 32 비트)](operator-high32.md)|[HIGHWORD (가장 낮은 32 비트의 상위 16 비트)](operator-highword.md)|
|[길이 (배열의 요소 수)](operator-length.md)|[LENGTHOF (배열의 요소 수)](operator-lengthof.md)|[낮음 (하위 8 비트)](operator-low.md)|
|[LOW32 (낮은 32 비트)](operator-low32.md)|[LOWWORD (하위 16 비트)](operator-lowword.md)|[OPATTR (인수 형식 정보 가져오기)](operator-opattr.md)|
|[PTR (형식에 대 한 포인터)](operator-ptr.md)|[SHORT (짧은 레이블 형식으로 표시)](operator-short.md)|[크기 (형식 또는 변수 크기)](operator-size.md)|
|[SIZEOF (형식 또는 변수의 크기)](operator-sizeof.md)|[THIS (현재 위치)](operator-this.md)|[형식 (식 형식 가져오기)](operator-type.md)|
|[. 유형 (인수 유형 정보 가져오기)](operator-dot-type.md)|||

## <a name="see-also"></a>참조

[Microsoft 매크로 어셈블러 참조](microsoft-macro-assembler-reference.md)\
[MASM BNF 문법](masm-bnf-grammar.md)
