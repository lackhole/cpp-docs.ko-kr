---
title: 컴파일러 오류 C2681
ms.date: 11/04/2016
f1_keywords:
- C2681
helpviewer_keywords:
- C2681
ms.assetid: eb42da6d-8d2c-43fd-986b-e73e2b004885
ms.openlocfilehash: 8b311052d3a3525090d954c0dc8cee20e985b1b4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62282142"
---
# <a name="compiler-error-c2681"></a>컴파일러 오류 C2681

'type': 이름에 대 한 잘못 된 식 형식

캐스팅 연산자를 잘못 된 형식에서 변환 하려고 합니다. 예를 들어, 사용 하는 경우는 [dynamic_cast](../../cpp/dynamic-cast-operator.md) 포인터 형식, 원본 식으로 식을 변환 연산자는 포인터 여야 합니다.

다음 샘플에서는 C2681 오류가 생성 됩니다.

```
// C2681.cpp
class A { virtual void f(); };

void g(int i) {
    A* pa;
    pa = dynamic_cast<A*>(i);  // C2681
}
```