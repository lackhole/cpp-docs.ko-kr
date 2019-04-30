---
title: 컴파일러 오류 C3271
ms.date: 11/04/2016
f1_keywords:
- C3271
helpviewer_keywords:
- C3271
ms.assetid: 16d8bd1d-2e30-4c6a-a07f-0c4f3342fab5
ms.openlocfilehash: f94ef54408584e40dc406935e36053352ecf38e8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62365652"
---
# <a name="compiler-error-c3271"></a>컴파일러 오류 C3271

'member': FieldOffset 특성에 대한 값 'value'가 잘못되었습니다.

**FieldOffset** 특성에 음수가 전달되었습니다.

다음 샘플에서는 C3271을 생성합니다.

```
// C3271.cpp
// compile with: /clr /c
using namespace System;
using namespace System::Runtime::InteropServices;

[StructLayout(LayoutKind::Explicit)]
value class MyStruct1 {
   public: [FieldOffset(0)] int a;
   public: [FieldOffset(-1)] long b;   // C3271
};
```
