---
title: 컴파일러 오류 C3181
ms.date: 11/04/2016
f1_keywords:
- C3181
helpviewer_keywords:
- C3181
ms.assetid: 5d450f8b-6cef-4452-a0c4-2076e967451d
ms.openlocfilehash: e30ed7016ca3a4d4948a08c5c09268e52c9a407d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761675"
---
# <a name="compiler-error-c3181"></a>컴파일러 오류 C3181

' type ': 연산자에 대 한 피연산자가 잘못 되었습니다.

[Typeid](../../extensions/typeid-cpp-component-extensions.md) 연산자에 잘못 된 매개 변수가 전달 되었습니다. 매개 변수는 관리 되는 형식 이어야 합니다.

컴파일러는 공용 언어 런타임의 형식에 매핑되는 네이티브 형식에 별칭을 사용 합니다.

다음 샘플에서는 C3181를 생성 합니다.

```cpp
// C3181a.cpp
// compile with: /clr
using namespace System;

int main() {
   Type ^pType1 = interior_ptr<int>::typeid;   // C3181
   Type ^pType2 = int::typeid;   // OK
}
```
