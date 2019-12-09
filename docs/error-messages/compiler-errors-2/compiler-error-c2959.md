---
title: 컴파일러 오류 C2959
ms.date: 11/04/2016
f1_keywords:
- C2959
helpviewer_keywords:
- C2959
ms.assetid: d66bb2a8-70c3-4209-a358-b0c47f111a50
ms.openlocfilehash: a0e20ed3601babb2f4f53bc293d1dc462f9a30a7
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747633"
---
# <a name="compiler-error-c2959"></a>컴파일러 오류 C2959

제네릭 클래스 또는 함수는 템플릿의 멤버가 될 수 없습니다.

자세한 내용은 [Windows 런타임 및 관리 되는 템플릿](../../extensions/windows-runtime-and-managed-templates-cpp-component-extensions.md) 및 [제네릭](../../extensions/generics-cpp-component-extensions.md)을 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C2959를 생성 합니다.

```cpp
// C2959.cpp
// compile with: /clr /c
template <class T> ref struct S {
   generic <class U> ref struct GR1;   // C2959
};
```
