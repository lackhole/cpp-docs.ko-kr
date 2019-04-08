---
title: 컴파일러 오류 C3283
ms.date: 11/04/2016
f1_keywords:
- C3283
helpviewer_keywords:
- C3283
ms.assetid: c51d912c-cde3-4928-904e-26734c8954ce
ms.openlocfilehash: 593b04b8593e261aa1980ada7693300b52a869c5
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58779991"
---
# <a name="compiler-error-c3283"></a>컴파일러 오류 C3283

'type': 인터페이스에는 인스턴스 생성자를 사용할 수 없습니다.

CLR [인터페이스](../../extensions/interface-class-cpp-component-extensions.md) 에는 인스턴스 생성자를 사용할 수 없습니다.  정적 생성자는 허용됩니다.

다음 샘플에서는 C3283을 생성합니다.

```
// C3283.cpp
// compile with: /clr
interface class I {
   I();   // C3283
};
```

해결 방법:

```
// C3283b.cpp
// compile with: /clr /c
interface class I {
   static I(){}
};
```