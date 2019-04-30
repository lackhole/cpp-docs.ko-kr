---
title: 컴파일러 오류 C2541
ms.date: 11/04/2016
f1_keywords:
- C2541
helpviewer_keywords:
- C2541
ms.assetid: ed95180f-00df-4e62-a8e9-1b6dab8281bf
ms.openlocfilehash: d8b2366bc2899b7a2ac76b0fae133351cd88a541
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386956"
---
# <a name="compiler-error-c2541"></a>컴파일러 오류 C2541

'delete': 삭제: 포인터가 아닌 개체를 삭제할 수 없습니다

합니다 [삭제](../../cpp/delete-operator-cpp.md) 연산자가 포인터가 아닌 개체에 사용 되었습니다.

다음 샘플에서는 C2541 오류가 생성 됩니다.

```
// C2541.cpp
int main() {
   int i;
   delete i;   // C2541 i not a pointer

   // OK
   int *ip = new int;
   delete ip;
}
```