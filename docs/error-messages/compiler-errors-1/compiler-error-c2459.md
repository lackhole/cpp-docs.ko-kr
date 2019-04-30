---
title: 컴파일러 오류 C2459
ms.date: 11/04/2016
f1_keywords:
- C2459
helpviewer_keywords:
- C2459
ms.assetid: 81e29f4c-5b60-40fb-9557-1cdc630d77e8
ms.openlocfilehash: d2e8b375fd1219b11b3a543bf3a565ddee00ccf2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62367956"
---
# <a name="compiler-error-c2459"></a>컴파일러 오류 C2459

'identifier': 정의 하 고 있습니다. 익명 멤버로 서 추가할 수 없습니다.

클래스, 구조체 또는 공용 구조체는 자체 범위에서 익명 공용 구조체의 멤버에 의해 재정의 됩니다.

다음 샘플에서는 C2459 오류가 생성 됩니다.

```
// C2459.cpp
// compile with: /c
class C {
   union { int C; };   // C2459
   union { int D; };
};
```