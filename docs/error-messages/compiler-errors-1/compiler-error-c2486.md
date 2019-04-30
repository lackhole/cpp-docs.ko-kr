---
title: 컴파일러 오류 C2486
ms.date: 11/04/2016
f1_keywords:
- C2486
helpviewer_keywords:
- C2486
ms.assetid: 436da349-6461-4e32-bfca-4f3e620108e2
ms.openlocfilehash: 8d745c03530f331da83b45c765a2cb4bb7d76d8e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62364352"
---
# <a name="compiler-error-c2486"></a>컴파일러 오류 C2486

' __LOCAL_SIZE' 'naked' 특성이 있는 함수에만 사용할 수

인라인 어셈블리 함수에서 이름 `__LOCAL_SIZE` 으로 선언 된 함수에 대해 예약 된 [naked](../../cpp/naked-cpp.md) 특성입니다.

다음 샘플에서는 C2486를 생성합니다.

```
// C2486.cpp
// processor: x86
void __declspec(naked) f1() {
   __asm {
      mov   eax,   __LOCAL_SIZE
   }
}
void f2() {
   __asm {
      mov   eax,   __LOCAL_SIZE   // C2486
   }
}
```