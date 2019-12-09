---
title: 컴파일러 오류 C2971
ms.date: 11/04/2016
f1_keywords:
- C2971
helpviewer_keywords:
- C2971
ms.assetid: fdb5467b-9a41-41ef-ac20-2e9428d5a4fc
ms.openlocfilehash: 9912224c5c871f9bae2c6d22f0d38f5f88c983a9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743291"
---
# <a name="compiler-error-c2971"></a>컴파일러 오류 C2971

' class ': 템플릿 매개 변수 ' param ': ' arg ': 지역 변수를 비 형식 인수로 사용할 수 없습니다.

지역 변수의 이름 또는 주소를 템플릿 인수로 사용할 수 없습니다.

다음 샘플에서는 C2971를 생성 합니다.

```cpp
// C2971.cpp
template <int *pi>
class Y {};

int global_var = 0;

int main() {
   int local_var = 0;
   Y<&local_var> aY;   // C2971
   // try the following line instead
   // Y<&global_var> aY;
}
```
