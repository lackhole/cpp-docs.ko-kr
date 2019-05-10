---
title: 컴파일러 오류 C2503
ms.date: 11/04/2016
f1_keywords:
- C2503
helpviewer_keywords:
- C2503
ms.assetid: da86cc89-fd04-400b-aa8d-a5ffaf7e3918
ms.openlocfilehash: c481a27f19a92f47a19f0cfaa7b59cd509bb3c15
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62164945"
---
# <a name="compiler-error-c2503"></a>컴파일러 오류 C2503

'class': 기본 클래스에는 크기가 0 인 배열을 포함할 수 없습니다

기본 클래스 또는 구조체에 크기가 0 인 배열이 포함 되어 있습니다. 클래스에서 배열에 요소가 하나 이상 있어야 합니다.

다음 샘플에서는 C2503 오류가 생성 됩니다.

```
// C2503.cpp
// compile with: /c
class A {
   public:
   int array [];
};

class B : A {};    // C2503

class C {
public:
   int array [10];
};

class D : C {};
```