---
title: 컴파일러 오류 C2657
ms.date: 11/04/2016
f1_keywords:
- C2657
helpviewer_keywords:
- C2657
ms.assetid: f7cf29a9-684a-4605-9469-ecfee9ba4b03
ms.openlocfilehash: e060c2b9a38866a898a3c5ada9e595464050877e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756099"
---
# <a name="compiler-error-c2657"></a>컴파일러 오류 C2657

문의 시작 부분에 ' class::* '이 (가) 있습니다. 형식을 지정 해야 합니다.

줄은 멤버 포인터 식별자로 시작 합니다.

멤버에 대 한 포인터 선언에서 형식 지정 자가 누락 되어이 오류가 발생할 수 있습니다.

다음 샘플에서는 C2657를 생성 합니다.

```cpp
// C2657.cpp
class C {};
int main() {
   C::* pmc1;        // C2657
   int C::* pmc2;   // OK
}
```
