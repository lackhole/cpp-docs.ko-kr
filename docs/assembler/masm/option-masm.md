---
title: OPTION (MASM)
ms.date: 12/17/2019
f1_keywords:
- option
helpviewer_keywords:
- OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
ms.openlocfilehash: bd50ac2e051db7f02ac077054e5856524745df54
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75318750"
---
# <a name="option"></a>OPTION

어셈블러의 기능을 사용 하거나 사용 하지 않도록 설정 합니다.

## <a name="syntax"></a>구문

> **옵션 옵션** *목록*

## <a name="remarks"></a>주의

사용 가능한 옵션은 다음과 같습니다.

|||||
|-|-|-|-|
|**CASEMAP**|**DOTNAME**|**NODOTNAME**|**에뮬레이터**|
|**NOEMULATOR**|**EPILOGUE**|**EXPR16**|**EXPR32**|
|**LANGUAGE**|**LJMP**|**NOLJMP**|**M510**|
|**NOM510**|**NOKEYWORD**|**NOSIGNEXTEND**|**OFFSET**|
|**OLDMACROS**|**NOOLDMACROS**|**OLDSTRUCTS**|**NOOLDSTRUCTS**|
|**PROC**|**프롤로그**|**READONLY**|**NOREADONLY**|
|**SCOPED**|**NOSCOPED**|**SEGMENT**|**SETIF2**.|

LANGUAGE의 구문은 **language:** <em>x</em>입니다. 여기서 *x* 는 C, SYSCALL, STDCALL, 파스칼, 포트란 또는 BASIC 중 하나입니다.  SYSCALL, 파스칼, 포트란 및 BASIC은에서 지원 되지 않습니다 [. 모델](dot-model.md) FLAT.

## <a name="see-also"></a>참조

[지시문 참조](directives-reference.md)\
[MASM BNF 문법](masm-bnf-grammar.md)
