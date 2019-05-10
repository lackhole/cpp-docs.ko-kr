---
title: 컴파일러 오류 C2673
ms.date: 11/04/2016
f1_keywords:
- C2673
helpviewer_keywords:
- C2673
ms.assetid: 780230c0-619b-4a78-b01d-ff5886306741
ms.openlocfilehash: 8a544b6d96089195d7d28f9a62b091b4f1cfc537
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386839"
---
# <a name="compiler-error-c2673"></a>컴파일러 오류 C2673

'function': 전역 함수에 'this' 포인터가 없습니다.

전역 함수에 액세스 하려고 `this`합니다.

다음 샘플에서는 C2673 오류가 생성 됩니다.

```
// C2673.cpp
int main() {
   this = 0;   // C2673
}
```