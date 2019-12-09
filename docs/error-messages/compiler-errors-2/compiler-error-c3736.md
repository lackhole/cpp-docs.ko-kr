---
title: 컴파일러 오류 C3736
ms.date: 11/04/2016
f1_keywords:
- C3736
helpviewer_keywords:
- C3736
ms.assetid: 579b773c-41e7-40ea-8382-2e3ce2667f4c
ms.openlocfilehash: 9c4626164fe8fe3fb932fba3ae8e87c774f5aeec
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752849"
---
# <a name="compiler-error-c3736"></a>컴파일러 오류 C3736

' event ': 메서드 이거나, 관리 되는 이벤트의 경우 선택적으로 데이터 멤버 여야 합니다.

네이티브 및 COM 이벤트는 메서드 여야 합니다. .NET 이벤트는 데이터 멤버일 수도 있습니다.

다음 샘플에서는 C3736를 생성 합니다.

```cpp
// C3736.cpp
struct A {
   __event int e();
};

struct B {
   int f;   // C3736
   // The following line resolves the error.
   // int f();
   B(A* a) {
      __hook(&A::e, a, &B::f);
   }
};

int main() {
}
```
