---
title: 컴파일러 오류 C2100
ms.date: 11/04/2016
f1_keywords:
- C2100
helpviewer_keywords:
- C2100
ms.assetid: 9ed5ea11-9d55-4ddf-8b1a-162c74f3c390
ms.openlocfilehash: 08ff3b138db4ae07b73eb130983903cb60549e15
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752355"
---
# <a name="compiler-error-c2100"></a>컴파일러 오류 C2100

간접 참조가 잘못 되었습니다.

간접 참조 연산자 (`*`)는 포인터가 아닌 값에 적용 됩니다.

다음 샘플에서는 C2100를 생성 합니다.

```cpp
// C2100.cpp
int main() {
   int r = 0, *s = 0;
   s = &r;
   *r = 200;   // C2100
   *s = 200;   // OK
}
```
