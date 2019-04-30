---
title: 컴파일러 경고(수준 1) C4551
ms.date: 11/04/2016
f1_keywords:
- C4551
helpviewer_keywords:
- C4551
ms.assetid: 458b59bd-e2d7-425f-9ba6-268ff200424f
ms.openlocfilehash: 8a30ad5622d8e889a7f3ec64b73ead7c63f65b48
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397356"
---
# <a name="compiler-warning-level-1-c4551"></a>컴파일러 경고(수준 1) C4551

인수 목록이 없습니다. 함수 호출

함수 매개 변수를 사용 하는 경우에 함수 호출 함수 이름 뒤에 오는 괄호와 닫는 괄호를 포함 해야 합니다.

다음 샘플에서는 C4551 오류가 생성 됩니다.

```
// C4551.cpp
// compile with: /W1
void function1() {
}

int main() {
   function1;   // C4551
   function1();   // OK
}
```