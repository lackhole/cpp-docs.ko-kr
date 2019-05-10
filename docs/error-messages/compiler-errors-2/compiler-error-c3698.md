---
title: 컴파일러 오류 C3698
ms.date: 11/04/2016
f1_keywords:
- C3698
helpviewer_keywords:
- C3698
ms.assetid: 3c02fb08-7ba4-4637-a06f-19926cb2b5f1
ms.openlocfilehash: 78cded92c8f73c77f7871278443bd3dfd4dbe686
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62325184"
---
# <a name="compiler-error-c3698"></a>컴파일러 오류 C3698

'type': 'operator'의 인수로이 형식을 사용할 수 없습니다

관리 되는 개체를 올바르게 선언 되었습니다.

다음 샘플에서는 C3698를 생성합니다.

```
// C3698.cpp
// compile with: /clr

int main() {
   array<int>^a = new array<int>^(20);   // C3698
   array<int>^a2 = gcnew array<int>(20);   // OK
}
```