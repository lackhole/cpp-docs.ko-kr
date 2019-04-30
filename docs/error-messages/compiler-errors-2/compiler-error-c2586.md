---
title: 컴파일러 오류 C2586
ms.date: 11/04/2016
f1_keywords:
- C2586
helpviewer_keywords:
- C2586
ms.assetid: dae703c7-5c38-4db6-8411-4d1b22713eb5
ms.openlocfilehash: a6af49bba84eded7d530f6ecc37fac8f6acf16e2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360426"
---
# <a name="compiler-error-c2586"></a>컴파일러 오류 C2586

잘못 된 사용자 정의 변환 구문이: 잘못 된 간접 참조

변환 연산자의 간접 참조는 허용 되지 않습니다.

다음 샘플에서는 C2586 오류가 생성 됩니다.

```
// c2586.cpp
// compile with: /c
struct C {
   * operator int();   // C2586
   operator char();   // OK
};
```