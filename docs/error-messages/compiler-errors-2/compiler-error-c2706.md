---
title: 컴파일러 오류 C2706
ms.date: 11/04/2016
f1_keywords:
- C2706
helpviewer_keywords:
- C2706
ms.assetid: e18da924-c42d-4b09-8e29-f4e0382d7dc6
ms.openlocfilehash: 9767d36d44b99423d600d299d0803901d3dbfec5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62161110"
---
# <a name="compiler-error-c2706"></a>컴파일러 오류 C2706

일치 하는 없이 __except를 잘못 \__try (누락 된 '}'에서 \__try 블록?)

컴파일러의 닫는 중괄호를 찾을 수 없습니다는 `__try` 블록입니다.

다음 샘플에서는 C2706 오류가 생성 됩니다.

```
// C2706.cpp
int main() {
   __try {
      void f();
   // C2706  } missing here
   __except(GetExceptionCode() == 0x0) {
   }
}
```