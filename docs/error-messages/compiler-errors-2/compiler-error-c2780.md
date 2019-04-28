---
title: 컴파일러 오류 C2780
ms.date: 11/04/2016
f1_keywords:
- C2780
helpviewer_keywords:
- C2780
ms.assetid: 423793d8-a3b2-4f35-85f8-ae1d043e2b69
ms.openlocfilehash: 9a427bbd79570a2646447d5326e034035306fac6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257454"
---
# <a name="compiler-error-c2780"></a>컴파일러 오류 C2780

'declaration' : 인수가 N개 있어야 하는데 M개를 사용했습니다.

함수 템플릿에 인수가 너무 적거나 너무 많습니다.

다음 샘플에서는 C2780을 생성하고 해결 방법을 보여 줍니다.

```
// C2780.cpp
template<typename T>
void f(T, T){}

int main() {
   f(1);  // C2780
   // try the following line instead
   // f(1,2);
}
```