---
title: 컴파일러 오류 C2474
ms.date: 11/04/2016
f1_keywords:
- C2474
helpviewer_keywords:
- C2474
ms.assetid: 64e6c61e-6e77-480e-bcf0-b30a2fc482ac
ms.openlocfilehash: ed2ba0d80ffcf2ef83abd551026bc6df4939ffbd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743733"
---
# <a name="compiler-error-c2474"></a>컴파일러 오류 C2474

'keyword': 인접한 세미콜론이 없습니다. 키워드거나 식별자일 수 있습니다.

컴파일러가 세미콜론을 찾아야 하며 사용자 의도를 확인할 수 없습니다. 이 오류를 해결하려면 세미콜론을 추가합니다.

## <a name="example"></a>예제

다음 샘플에서는 C2474를 생성합니다.

```cpp
// C2474.cpp
// compile with: /clr /c

ref class A {
   ref class B {}
   property int i;   // C2474 error
};

// OK
ref class B {
   ref class D {};
   property int i;
};

ref class E {
   ref class F {} property;
   int i;
};
```
