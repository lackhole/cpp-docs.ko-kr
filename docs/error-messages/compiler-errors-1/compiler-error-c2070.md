---
title: 컴파일러 오류 C2070
ms.date: 11/04/2016
f1_keywords:
- C2070
helpviewer_keywords:
- C2070
ms.assetid: 4c8dea63-1227-4aba-be26-2462537f86fb
ms.openlocfilehash: 221b42e6425c84f4e34c99872fc0e51716e2db1b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208907"
---
# <a name="compiler-error-c2070"></a>컴파일러 오류 C2070

'type': 잘못 된 sizeof 피연산자

합니다 [sizeof](../../cpp/sizeof-operator.md) 연산자는 식 또는 형식 이름이 필요 합니다.

다음 샘플에서는 C2070를 생성합니다.

```
// C2070.cpp
void func() {}
int main() {
   int a;
   a = sizeof(func);   // C2070
}
```

해결 방법:

```
// C2070b.cpp
void func() {}
int main() {
   int a;
   a = sizeof(a);
}
```