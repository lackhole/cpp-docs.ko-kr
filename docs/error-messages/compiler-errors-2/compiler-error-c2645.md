---
title: 컴파일러 오류 C2645
ms.date: 11/04/2016
f1_keywords:
- C2645
helpviewer_keywords:
- C2645
ms.assetid: 6609c2fa-c3b2-4a6b-8e8d-58fb52f67175
ms.openlocfilehash: fa50cf4105c6ceb4f1104e0625ec6492e2d0461a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758231"
---
# <a name="compiler-error-c2645"></a>컴파일러 오류 C2645

멤버 포인터에 대 한 정규화 된 이름이 없습니다. ':: * '가 있습니다.

멤버에 대 한 포인터 선언이 클래스를 지정 하지 않습니다.

다음 샘플에서는 C2645를 생성 합니다.

```cpp
// C2645.cpp
class A {};
int main() {
   int B::* bp;   // C2645 B not defined
   int A::* ap;   // OK
}
```
