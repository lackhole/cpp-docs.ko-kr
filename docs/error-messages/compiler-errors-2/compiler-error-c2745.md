---
title: 컴파일러 오류 C2745
ms.date: 11/04/2016
f1_keywords:
- C2745
helpviewer_keywords:
- C2745
ms.assetid: a1c45f13-7667-4678-aa16-265304a449a1
ms.openlocfilehash: 5fe19bcf55c743bb3e35d1ca9ae28d2b08dcbd89
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759011"
---
# <a name="compiler-error-c2745"></a>컴파일러 오류 C2745

' token ':이 토큰을 식별자로 변환할 수 없습니다.

식별자는 올바른 문자로 구성 되어야 합니다.

다음 샘플에서는 C2745를 생성 합니다.

```cpp
// C2745.cpp
// compile with: /clr
int main() {
   int __identifier([));   // C2745
}
```
