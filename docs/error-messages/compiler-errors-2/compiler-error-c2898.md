---
title: 컴파일러 오류 C2898
ms.date: 11/04/2016
f1_keywords:
- C2898
helpviewer_keywords:
- C2898
ms.assetid: 68466e11-2541-4f6b-b772-13a642f30dfb
ms.openlocfilehash: d06741735f6358856b70c4264755fe559d4f88a9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74735764"
---
# <a name="compiler-error-c2898"></a>컴파일러 오류 C2898

' 선언 ': 멤버 함수 템플릿은 가상 일 수 없습니다.

다음 샘플에서는 C2898를 생성 합니다.

```cpp
// C2898.cpp
// compile with: /c
class X {
public:
   template<typename T> virtual void f(T t) {}   // C2898
};
```
