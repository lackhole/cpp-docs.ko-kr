---
title: 컴파일러 오류 C2627
ms.date: 11/04/2016
f1_keywords:
- C2627
helpviewer_keywords:
- C2627
ms.assetid: 7fc6c5ac-c7c9-4f0b-ad52-f52252526458
ms.openlocfilehash: 6b0471aaead1b56f51e4393784306aa6ed928eec
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754734"
---
# <a name="compiler-error-c2627"></a>컴파일러 오류 C2627

' function ': 익명 공용 구조체에는 멤버 함수를 사용할 수 없습니다.

[익명 공용 구조체](../../cpp/unions.md#anonymous_unions) 에는 멤버 함수를 사용할 수 없습니다.

다음 샘플에서는 C2627를 생성 합니다.

```cpp
// C2627.cpp
int main() {
   union { void f(){} };   // C2627
   union X { void f(){} };
}
```
