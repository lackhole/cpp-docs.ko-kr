---
title: 컴파일러 오류 C2890
ms.date: 11/04/2016
f1_keywords:
- C2890
helpviewer_keywords:
- C2890
ms.assetid: 49147375-182c-42b1-b170-f475cd436d47
ms.openlocfilehash: d51748e80dad0370b5f735180455dd6c8d113c7a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760904"
---
# <a name="compiler-error-c2890"></a>컴파일러 오류 C2890

' class ': ref 클래스에는 비 인터페이스 기본 클래스를 하나만 사용할 수 있습니다.

참조 클래스에는 기본 클래스를 하나만 사용할 수 있습니다.

다음 샘플에서는 C2890를 생성 합니다.

```cpp
// C2890.cpp
// compile with: /clr /c
ref class A {};
ref class B {};
ref class C : public A, public B {};   // C2890
ref class D : public A {};   // OK
```
