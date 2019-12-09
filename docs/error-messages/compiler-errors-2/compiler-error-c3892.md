---
title: 컴파일러 오류 C3892
ms.date: 11/04/2016
f1_keywords:
- C3892
helpviewer_keywords:
- C3892
ms.assetid: 83fff42c-ea48-442f-bc2e-b33a6b99d890
ms.openlocfilehash: 73d96c61e918da3aabbfc00b83213fa79a2eedf9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736388"
---
# <a name="compiler-error-c3892"></a>컴파일러 오류 C3892

' var ': const 인 변수에 할당할 수 없습니다.

Const 변수를 선언 하 고 초기화 한 후에는 변경할 수 없습니다.

다음 샘플에서는 C3892를 생성 합니다.

```cpp
// C3892.cpp
// compile with: /clr
ref struct Y1 {
   static const int staticConst = 9;
};

int main() {
   Y1::staticConst = 0;   // C3892
}
```
