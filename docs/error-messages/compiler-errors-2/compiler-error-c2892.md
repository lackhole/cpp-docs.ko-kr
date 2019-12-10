---
title: 컴파일러 오류 C2892
ms.date: 11/04/2016
f1_keywords:
- C2892
helpviewer_keywords:
- C2892
ms.assetid: c22a5084-2f50-42c2-a56b-6dfe5442edc9
ms.openlocfilehash: f3868a44cf04d6c87092759ea473aa78aa0ad4c4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760891"
---
# <a name="compiler-error-c2892"></a>컴파일러 오류 C2892

지역 클래스는 멤버 템플릿을 가질 수 없습니다.

함수에 정의 된 클래스에서는 템플릿 멤버 함수를 사용할 수 없습니다.

다음 샘플에서는 C2892를 생성 합니다.

```cpp
// C2892.cpp
int main() {
   struct local {
      template<class T>   // C2892
      void f() {}
   };
}
```
