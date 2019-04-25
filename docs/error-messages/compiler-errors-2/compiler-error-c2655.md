---
title: 컴파일러 오류 C2655
ms.date: 11/04/2016
f1_keywords:
- C2655
helpviewer_keywords:
- C2655
ms.assetid: beaefa6e-51b3-4df9-9150-960f3fbf40e0
ms.openlocfilehash: 094dabb5ad07796194ae391000ca1e9025602d93
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62161188"
---
# <a name="compiler-error-c2655"></a>컴파일러 오류 C2655

'identifier': 정의 또는 재선언 현재 범위에서

식별자는 전역 범위 에서만 다시 선언할 수 있습니다.

다음 샘플에서는 C2655 오류가 생성 됩니다.

```
// C2655.cpp
class A {};
class B {
public:
   static int i;
};

int B::i;  // OK

int main() {
   A B::i;  // C2655
}
```