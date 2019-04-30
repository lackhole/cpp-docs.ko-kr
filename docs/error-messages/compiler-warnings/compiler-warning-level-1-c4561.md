---
title: 컴파일러 경고(수준 1) C4561
ms.date: 11/04/2016
f1_keywords:
- C4561
helpviewer_keywords:
- C4561
ms.assetid: 3a10c12c-601b-4b6c-9861-331fd022e021
ms.openlocfilehash: 24a3ca8b35266e93f298314f45015b7a480e2af0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397291"
---
# <a name="compiler-warning-level-1-c4561"></a>컴파일러 경고(수준 1) C4561

와 호환 되지 않는 ' __fastcall'는 ' / clr' 옵션: 변환할 '\__stdcall'

합니다 [__fastcall](../../cpp/fastcall.md) 함수 호출 규칙을 사용 하 여 사용할 수는 [/clr](../../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션입니다. 컴파일러에 대 한 호출을 무시 `__fastcall`합니다. 이 경고를 해결 하려면에 대 한 호출을 제거 하거나 **__fastcall** 또는 없이 컴파일 **/clr**합니다.

다음 샘플에서는 C4561 오류가 생성 됩니다.

```
// C4561.cpp
// compile with: /clr /W1 /c
// processor: x86
void __fastcall Func(void *p);   // C4561, remove __fastcall to resolve
```