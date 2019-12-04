---
title: 컴파일러 오류 C3100
ms.date: 11/04/2016
f1_keywords:
- C3100
helpviewer_keywords:
- C3100
ms.assetid: 7a9c9eaf-08ef-442d-94a0-e457beee8549
ms.openlocfilehash: 4a0e0995b1a4dcbc92f02de03920893f884c2c7c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750041"
---
# <a name="compiler-error-c3100"></a>컴파일러 오류 C3100

' target ': 알 수 없는 특성 한정자입니다.

잘못 된 특성 대상을 지정 했습니다.

자세한 내용은 [User-Defined Attributes](../../extensions/user-defined-attributes-cpp-component-extensions.md)을 참조하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3100를 생성 합니다.

```cpp
// C3100.cpp
// compile with: /clr /c
using namespace System;
[AttributeUsage(AttributeTargets::All)]
public ref class Attr : public Attribute {
public:
   Attr(int t) : m_t(t) {}
   int m_t;
};

[invalid_target:Attr(10)];   // C3100
[assembly:Attr(10)];   // OK
```
