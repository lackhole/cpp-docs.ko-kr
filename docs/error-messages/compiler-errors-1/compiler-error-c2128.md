---
title: 컴파일러 오류 C2128
ms.date: 11/04/2016
f1_keywords:
- c2128
helpviewer_keywords:
- C2128
ms.assetid: 08cbf734-75b3-49f2-9026-9b319947612d
ms.openlocfilehash: 80015118bf9e8bc8d8c4fba578f4ff1fa4651034
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397642"
---
# <a name="compiler-error-c2128"></a>컴파일러 오류 C2128

'function': alloc_text/same_seg는 C 링크가 있는 함수에만 적용

`pragma` `alloc_text` C 링크를 포함 하도록 선언 하는 함수로 사용할 수 있습니다.

다음 샘플에서는 C2128 오류가 생성 됩니다.

```
// C2128.cpp
// compile with: /c

// Delete the following line to resolve.
void func();
// #pragma alloc_text("my segment", func)   // C2128

extern "C" {
void func();
}

#pragma alloc_text("my segment", func)
void func() {}
```