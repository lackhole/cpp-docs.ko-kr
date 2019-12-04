---
title: 컴파일러 오류 C2541
ms.date: 11/04/2016
f1_keywords:
- C2541
helpviewer_keywords:
- C2541
ms.assetid: ed95180f-00df-4e62-a8e9-1b6dab8281bf
ms.openlocfilehash: de24503d256b8c7649ce87969b1b2f6a4709ac8f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740847"
---
# <a name="compiler-error-c2541"></a>컴파일러 오류 C2541

' delete ': delete: 포인터가 아닌 개체를 삭제할 수 없습니다.

[Delete](../../cpp/delete-operator-cpp.md) 연산자가 포인터가 아닌 개체에서 사용 되었습니다.

다음 샘플에서는 C2541를 생성 합니다.

```cpp
// C2541.cpp
int main() {
   int i;
   delete i;   // C2541 i not a pointer

   // OK
   int *ip = new int;
   delete ip;
}
```
