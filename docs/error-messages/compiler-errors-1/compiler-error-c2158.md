---
title: 컴파일러 오류 C2158
ms.date: 11/04/2016
f1_keywords:
- C2158
helpviewer_keywords:
- C2158
ms.assetid: 39028899-e95c-4809-8e65-6111118641ee
ms.openlocfilehash: f098af90d3052d6961eb0892085c02f2e42bbed4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755868"
---
# <a name="compiler-error-c2158"></a>컴파일러 오류 C2158

'type': #pragma make_public 지시문은 현재 템플릿이 아닌 네이티브 형식에만 사용할 수 있습니다.

[make_public](../../preprocessor/make-public.md) pragma는 템플릿이 아닌 네이티브 형식에만 적용할 수 있습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2158을 생성합니다.

```cpp
// C2158.cpp
// compile with: /clr /c
ref class A {};
#pragma make_public(A)   // C2158

template< typename T >
class B {};
#pragma make_public(B)   // C2158
#pragma make_public(B<int>)   // C2158

void C () {}
#pragma make_public(C)   // C2158

class D {};
#pragma make_public(D)   // OK
```
