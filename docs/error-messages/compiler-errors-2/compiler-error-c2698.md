---
title: 컴파일러 오류 C2698
ms.date: 11/04/2016
f1_keywords:
- C2698
helpviewer_keywords:
- C2698
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
ms.openlocfilehash: f643b7d8c035b4d1d7d8806feb5b121cf76d7796
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62367579"
---
# <a name="compiler-error-c2698"></a>컴파일러 오류 C2698

에 대 한를 사용 하 여 선언을 ' 선언 1'의 기존 using 선언과 공존할 수 없습니다 ' 2' 선언

만든 후는 [선언을 사용 하 여](../../cpp/using-declaration.md) 사용 하 여 모든 데이터 멤버에 대 한 동일한 이름을 사용 하는 동일한 범위에서 선언은 사용할 수 없습니다만 함수를 오버 로드할 수 있습니다.

다음 샘플에서는 C2698를 생성합니다.

```
// C2698.cpp
struct A {
   int x;
};

struct B {
   int x;
};

struct C : A, B {
   using A::x;
   using B::x;   // C2698
}
```