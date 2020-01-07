---
title: XMMWORD
ms.date: 12/17/2019
f1_keywords:
- XMMWORD
helpviewer_keywords:
- XMMWORD directive
ms.assetid: 18026d32-5cab-403e-ad7e-382fb41aa9b8
ms.openlocfilehash: 1116729883bf9b1b9342b30332bab5de6ba59015
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75319114"
---
# <a name="xmmword"></a>XMMWORD

MMX 및 SSE (XMM) 명령을 포함 하는 128 비트 멀티미디어 피연산자에 사용 됩니다.

## <a name="syntax"></a>구문

> **XMMWORD**

## <a name="remarks"></a>주의

**Xmmword** 는 [__m128](../../cpp/m128.md)와 동일한 형식을 표시 하기 위한 것입니다.

## <a name="example"></a>예

```asm
    movdqa   xmm0, xmmword ptr [ebx]
```

## <a name="see-also"></a>참고 항목

[MASM BNF 문법](masm-bnf-grammar.md)
