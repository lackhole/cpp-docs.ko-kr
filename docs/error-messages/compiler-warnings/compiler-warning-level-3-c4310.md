---
title: 컴파일러 경고(수준 3) C4310
ms.date: 11/04/2016
f1_keywords:
- C4310
helpviewer_keywords:
- C4310
ms.assetid: cba3eca1-f1ed-499c-9243-337446bdbdd8
ms.openlocfilehash: b8d011d0e41c7d3fe6de7468d098ddd08f09565c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402075"
---
# <a name="compiler-warning-level-3-c4310"></a>컴파일러 경고(수준 3) C4310

캐스트 상수 값을 자릅니다.

상수 값을 더 작은 형식으로 캐스팅 됩니다. 컴파일러에서 캐스트 데이터를 자릅니다를 수행 합니다. 다음 샘플에서는 C4310 오류가 생성 됩니다.

```
// C4310.cpp
// compile with: /W4
int main() {
   long int a;
   a = (char) 128;   // C4310, use value 0-127 to resolve
}
```