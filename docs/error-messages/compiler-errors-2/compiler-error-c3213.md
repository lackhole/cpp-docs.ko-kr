---
title: 컴파일러 오류 C3213
ms.date: 11/04/2016
f1_keywords:
- C3213
helpviewer_keywords:
- C3213
ms.assetid: 1f079e36-b3e9-40f8-8e95-08eeba3adc82
ms.openlocfilehash: c172ebbc133690eabe5ca25e4427c2c22e8221bf
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756203"
---
# <a name="compiler-error-c3213"></a>컴파일러 오류 C3213

기본 클래스 'base_type'이 'derived_type'보다 액세스하기 어렵습니다.

어셈블리에서 볼 수 있는 형식은 공개적으로 볼 수 있는 기본 클래스를 사용해야 합니다.

다음 샘플에서는 C3213을 생성합니다.

```cpp
// C3213.cpp
// compile with: /clr
private ref struct privateG {
public:
   int i;
};

public ref struct publicG {
public:
   int i;
};

public ref struct V : public privateG {   // C3213
public:
   int j;
};

public ref struct W: public publicG {   // OK
public:
   int j;
};
```
