---
title: .DOSSEG
ms.date: 11/05/2019
f1_keywords:
- .DOSSEG
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
ms.openlocfilehash: e27b0ae185542c11ee29119575d5c8225501f71e
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75313849"
---
# <a name="dosseg-32-bit-masm"></a>. .DOSSEG (32 비트 MASM)

MS-DOS 세그먼트 규칙에 따라 세그먼트를 정렬 합니다. CODE first, DGROUP에 없는 세그먼트, DGROUP의 세그먼트 순서로 정렬 합니다. (32 비트 MASM에만 해당)

## <a name="syntax"></a>구문

> **.DOSSEG**

## <a name="remarks"></a>주의

D 그룹의 세그먼트는 다음 순서를 따릅니다. 즉, BSS 나 스택에 있지 않은 세그먼트, BSS 세그먼트 및 finally STACK 세그먼트가 있습니다. 주로 MASM 독립 실행형 프로그램에서 CodeView 지원을 보장 하는 데 사용 됩니다. [.Dosseg](dosseg.md)와 동일 합니다.

## <a name="see-also"></a>참조

[지시문 참조](directives-reference.md)\
[MASM BNF 문법](masm-bnf-grammar.md)
