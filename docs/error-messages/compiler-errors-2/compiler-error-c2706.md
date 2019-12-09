---
title: 컴파일러 오류 C2706
ms.date: 11/04/2016
f1_keywords:
- C2706
helpviewer_keywords:
- C2706
ms.assetid: e18da924-c42d-4b09-8e29-f4e0382d7dc6
ms.openlocfilehash: bca86d3c0cf886c64a1d668468c793d0e77b2867
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757464"
---
# <a name="compiler-error-c2706"></a>컴파일러 오류 C2706

\__try 일치 하지 않는 __except 잘못 되었습니다. \__try 블록에 '} '가 없습니다.

컴파일러가 `__try` 블록의 닫는 중괄호를 찾지 못했습니다.

다음 샘플에서는 C2706를 생성 합니다.

```cpp
// C2706.cpp
int main() {
   __try {
      void f();
   // C2706  } missing here
   __except(GetExceptionCode() == 0x0) {
   }
}
```
