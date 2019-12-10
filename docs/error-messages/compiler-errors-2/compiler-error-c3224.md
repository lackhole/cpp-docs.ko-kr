---
title: 컴파일러 오류 C3224
ms.date: 11/04/2016
f1_keywords:
- C3224
helpviewer_keywords:
- C3224
ms.assetid: 129be22f-8f3e-4fc6-9ccd-d27d8ef91251
ms.openlocfilehash: 23a83a90c5583a427ffae9a7e69e531981ddd7cc
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757633"
---
# <a name="compiler-error-c3224"></a>컴파일러 오류 C3224

'type': 'number'개의 제네릭 형식 인수를 사용하는 오버로드된 제네릭 클래스가 없습니다.

컴파일러가 적절한 오버로드를 찾지 못했습니다.

다음 샘플에서는 C3224를 생성합니다.

```
// C3224.cs
// compile with: /target:library
public class C<T> {}
public class C<T,U> {}
```

그리고

```cpp
// C3224b.cpp
// compile with: /clr
#using "C3224.dll"
int main() {
   C<int,int,int>^ c = gcnew C<int,int,int>();   // C3224
   C<int,int>^ c2 = gcnew C<int,int>();   // OK
}
```
