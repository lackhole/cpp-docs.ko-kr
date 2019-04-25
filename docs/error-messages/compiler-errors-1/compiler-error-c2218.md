---
title: 컴파일러 오류 C2218
ms.date: 11/04/2016
f1_keywords:
- C2218
helpviewer_keywords:
- C2218
ms.assetid: b0f55da4-8edb-4b45-b298-1a091981bd7b
ms.openlocfilehash: 5a9d897686fc915c9892fa2bcd51fa3ca3c8b05e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165679"
---
# <a name="compiler-error-c2218"></a>컴파일러 오류 C2218

'__vectorcall'은 '/arch:IA32'와 함께 사용할 수 없습니다.

`__vectorcall` 호출 규칙은 SSE2(스트리밍 SIMD 확장명 2) 이상을 포함하는 x86 및 x64 프로세서의 네이티브 코드에서만 지원됩니다. 자세한 내용은 [__vectorcall](../../cpp/vectorcall.md)합니다.

이 오류를 해결하려면 컴파일러 옵션을 대상 SSE2, AVX 또는 AVX2 명령 집합으로 변경합니다. 자세한 내용은 [/arch(x86)](../../build/reference/arch-x86.md)를 참조하세요.