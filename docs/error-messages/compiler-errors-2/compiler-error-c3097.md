---
title: 컴파일러 오류 C3097
ms.date: 11/04/2016
f1_keywords:
- C3097
helpviewer_keywords:
- C3097
ms.assetid: b24bd8f8-e04f-4fbb-be57-4feb9165572e
ms.openlocfilehash: 71a7762d03c600fed71d76a19088fb70ce311f67
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756814"
---
# <a name="compiler-error-c3097"></a>컴파일러 오류 C3097

'attribute': 특성의 범위는 ‘assembly:’ 또는 ‘module:’이어야 합니다.

전역 특성이 잘못 사용되었습니다.

자세한 내용은 [User-Defined Attributes](../../extensions/user-defined-attributes-cpp-component-extensions.md)을 참조하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3097을 생성합니다.

```cpp
// C3097.cpp
// compile with: /clr /c
using namespace System;

[AttributeUsage(AttributeTargets::All, AllowMultiple = true)]
public ref class Attr : public Attribute {
public:
   Attr(int t) : m_t(t) {}
   int m_t;
};

[Attr(10)];   // C3097
[assembly:Attr(10)];   // OK

[Attr(10)]   // OK
public ref class MyClass {};
```
