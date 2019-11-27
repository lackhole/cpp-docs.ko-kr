---
title: XMMWORD
ms.date: 08/30/2018
f1_keywords:
- XMMWORD
helpviewer_keywords:
- XMMWORD directive
ms.assetid: 18026d32-5cab-403e-ad7e-382fb41aa9b8
ms.openlocfilehash: c7783049a143b19295a67cd3e9e40afeab3c814f
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74392789"
---
# <a name="xmmword"></a>XMMWORD

MMX 및 SSE (XMM) 명령을 포함 하는 128 비트 멀티미디어 피연산자에 사용 됩니다.

## <a name="syntax"></a>구문

> **XMMWORD**

## <a name="remarks"></a>주의

**Xmmword** 는 [__m128](../../cpp/m128.md)와 동일한 형식을 표시 하기 위한 것입니다.

## <a name="example"></a>예제

```asm
    movdqa   xmm0, xmmword ptr [ebx]
```
