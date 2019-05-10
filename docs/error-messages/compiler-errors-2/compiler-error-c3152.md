---
title: 컴파일러 오류 C3152
ms.date: 11/04/2016
f1_keywords:
- C3152
helpviewer_keywords:
- C3152
ms.assetid: 4ee6e2cd-5d19-4b73-833d-765c35797e4b
ms.openlocfilehash: 270d2fb02365f9c2460257d96bb5f6028707553e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374887"
---
# <a name="compiler-error-c3152"></a>컴파일러 오류 C3152

'construct': 'keyword'은(는) 클래스, 구조체 또는 가상 멤버 함수에만 적용될 수 있습니다.

특정 키워드는 C++ 클래스에만 적용될 수 있습니다.

다음 샘플에서는 C3152를 생성하고 해결 방법을 보여 줍니다.

```
// C3152.cpp
// compile with: /clr /c
ref class C {
   int (*pfn)() sealed;   // C3152
   virtual int g() sealed;   // OK
};
```
