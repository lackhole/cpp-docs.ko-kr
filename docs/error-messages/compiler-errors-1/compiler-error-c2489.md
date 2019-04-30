---
title: 컴파일러 오류 C2489
ms.date: 11/04/2016
f1_keywords:
- C2489
helpviewer_keywords:
- C2489
ms.assetid: 67d8cd98-db7e-4f7f-86b4-4af7bc89ec8b
ms.openlocfilehash: e4024455e17956fc67917e92a3ca531eca5c5e04
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62361037"
---
# <a name="compiler-error-c2489"></a>컴파일러 오류 C2489

'identifier': 'naked' 함수의 함수 범위에서 허용 되지 않습니다 하는 자동 또는 레지스터 변수를 초기화 합니다.

자세한 내용은 [naked](../../cpp/naked-cpp.md)합니다.

다음 샘플에서는 C2489 오류가 생성 됩니다.

```
// C2489.cpp
// processor: x86
__declspec( naked ) int func() {
   int i = 1;   // C2489
   register int j = 1;   // C2489
}
```