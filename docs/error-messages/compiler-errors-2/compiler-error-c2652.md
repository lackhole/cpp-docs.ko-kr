---
title: 컴파일러 오류 C2652
ms.date: 11/04/2016
f1_keywords:
- C2652
helpviewer_keywords:
- C2652
ms.assetid: 6e3d1a90-a989-4088-8afd-dc82f6a2d66f
ms.openlocfilehash: 9c9772052b690ad87de1d408c06478d82d48e724
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62282116"
---
# <a name="compiler-error-c2652"></a>컴파일러 오류 C2652

'identifier': 잘못 된 복사 생성자: 첫 번째 매개 변수에는 '식별자'를 사용 해야 합니다.

복사 생성자의 첫 번째 매개 변수는 클래스, 구조체 또는 공용 구조체 정의 동일한 형식을 있습니다. 첫 번째 매개 변수 형식이 있지만 형식 자체에 대 한 참조를 수 있습니다.

다음 샘플에서는 C2651 오류가 생성 됩니다.

```
// C2652.cpp
// compile with: /c
class A {
   A( A );   // C2652 takes an A
};
class B {
   B( B& );   // OK, reference to B
};
```