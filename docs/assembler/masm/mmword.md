---
title: MMWORD
ms.date: 12/17/2019
f1_keywords:
- MMWORD
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
ms.openlocfilehash: fd3b9f40b7ff9fa4dae570e0ed906c13a9456424
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75311925"
---
# <a name="mmword"></a>MMWORD

MMX 및 SSE (XMM) 명령을 포함 하는 64 비트 멀티미디어 피연산자에 사용 됩니다.

## <a name="syntax"></a>구문

> **MMWORD**

## <a name="remarks"></a>주의

**Mmword** 는 형식입니다.  MASM에 **단어가** 추가 되기 전에 다음을 사용 하 여 동일한 기능을 달성할 수 있습니다.

```asm
    mov mm0, qword ptr [ebx]
```

두 명령이 모두 64 비트 피연산자에 적용 되는 반면, **qword(64** 는 64 비트 부호 없는 정수의 형식이 고 **mmword** 는 64 비트 멀티미디어 값의 형식입니다.

**Mmword** 는 [__m64](../../cpp/m64.md)와 동일한 형식을 나타냅니다.

## <a name="example"></a>예

```asm
    movq     mm0, mmword ptr [ebx]
```

## <a name="see-also"></a>참고 항목

[MASM BNF 문법](masm-bnf-grammar.md)
