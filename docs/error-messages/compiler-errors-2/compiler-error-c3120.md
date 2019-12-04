---
title: 컴파일러 오류 C3120
ms.date: 11/04/2016
f1_keywords:
- C3120
helpviewer_keywords:
- C3120
ms.assetid: 9b6b210f-9948-4517-a4cc-b4aaadebde68
ms.openlocfilehash: ced859be68f780d0f0dee31e31d80b994ee73404
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740951"
---
# <a name="compiler-error-c3120"></a>컴파일러 오류 C3120

' method_name ': 인터페이스 메서드는 가변 인수 목록을 사용할 수 없습니다.

인터페이스 메서드는 가변 인수 목록을 사용할 수 없습니다. 예를 들어 다음 인터페이스 정의에서는 C3120를 생성 합니다.

```cpp
// C3120.cpp
__interface A {
int X(int i, ...);    // C3120
};

int main(void) { return(0); }
```
