---
title: 컴파일러 오류 C2718
ms.date: 11/04/2016
f1_keywords:
- C2718
helpviewer_keywords:
- C2718
ms.assetid: 78cc71f8-c142-46fc-9aed-970635d74f0c
ms.openlocfilehash: 00ad8da46364cd4a48ebdfde8b4de960e4e015f5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406914"
---
# <a name="compiler-error-c2718"></a>컴파일러 오류 C2718

'parameter': __declspec(align('#')) 인 실제 매개 변수는 맞춰지지 않습니다

합니다 [맞춤](../../cpp/align-cpp.md) `__declspec` 한정자 함수 매개 변수에서 허용 되지 않습니다.

다음 샘플에서는 C2718 오류가 생성 됩니다.

```
// C2718.cpp
typedef struct __declspec(align(32)) AlignedStruct  {
   int i;
} AlignedStruct;

void f2(int i, ...);

void f4() {
   AlignedStruct as;

   f2(0, as);   // C2718, actual parameter is aligned
}
```