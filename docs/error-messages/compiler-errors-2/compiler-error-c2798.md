---
title: 컴파일러 오류 C2798
ms.date: 11/04/2016
f1_keywords:
- C2798
helpviewer_keywords:
- C2798
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
ms.openlocfilehash: f3e8f0ac260e49866d1c654f89d34bf57a8ffbc1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152477"
---
# <a name="compiler-error-c2798"></a>컴파일러 오류 C2798

'super::member' 모호합니다.

사용 하 여 참조 하는 멤버를 포함 하는 다중 상속된 구조 [super](../../cpp/super.md)합니다. 오류를 해결할 수 있습니다.

- B1 또는 B2 D.의 상속 목록에서 제거합니다.

- -B2에서 B1의 데이터 멤버의 이름을 변경 합니다.

다음 샘플에서는 C2798 오류가 생성 됩니다.

```
// C2798.cpp
struct B1 {
   int i;
};

struct B2 {
   int i;
};

struct D : B1, B2 {
   void g() {
      __super::i = 4; // C2798
   }
};
```