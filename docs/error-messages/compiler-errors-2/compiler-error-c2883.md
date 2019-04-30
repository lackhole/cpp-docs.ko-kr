---
title: 컴파일러 오류 C2883
ms.date: 11/04/2016
f1_keywords:
- C2883
helpviewer_keywords:
- C2883
ms.assetid: 5c6d689d-ed42-41ad-b5c0-e9c2e0b8c356
ms.openlocfilehash: 3f32307e519394433927d49aa92333fdff7b70f3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378871"
---
# <a name="compiler-error-c2883"></a>컴파일러 오류 C2883

'name': 함수 선언이 using 선언에 의해 도입 된 'identifier'를 사용 하 여 충돌

함수를 두 번 이상 정의 하려고 했습니다. 첫 번째 정의 네임 스페이스가에서 수행 된 `using` 선언 합니다. 두 번째 지역 정의 했습니다.

다음 샘플에서는 C2883 오류가 생성 됩니다.

```
// C2883.cpp
namespace A {
   void z(int);
}

int main() {
   using A::z;
   void z(int);   // C2883  z is already defined
}
```