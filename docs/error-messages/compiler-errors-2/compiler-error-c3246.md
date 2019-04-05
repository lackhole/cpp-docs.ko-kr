---
title: 컴파일러 오류 C3246
ms.date: 11/04/2016
f1_keywords:
- C3246
helpviewer_keywords:
- C3246
ms.assetid: ad85224a-e540-479b-a5eb-a3bc3964c30b
ms.openlocfilehash: eb5ba268508922daf00adb49cf611c038db76343
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58776703"
---
# <a name="compiler-error-c3246"></a>컴파일러 오류 C3246

'class': 'sealed'로 선언했으므로 'type'에서 상속할 수 없습니다.

[sealed](../../extensions/sealed-cpp-component-extensions.md) 로 표시된 클래스는 다른 클래스의 기본 클래스일 수 없습니다.

다음 샘플에서는 C3246을 생성합니다.

```
// C3246_2.cpp
// compile with: /clr /LD
ref class X sealed {};

ref class Y : public X {}; // C3246
```
