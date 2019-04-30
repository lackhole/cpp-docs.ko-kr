---
title: 컴파일러 오류 C3145
ms.date: 11/04/2016
f1_keywords:
- C3145
helpviewer_keywords:
- C3145
ms.assetid: f165c874-0f51-45c7-85e8-ebe321cbc168
ms.openlocfilehash: e425402bcea3e08764a9a89abfbd9316ca254a83
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345534"
---
# <a name="compiler-error-c3145"></a>컴파일러 오류 C3145

'object': 전역 또는 정적 변수는 WinRT 또는 관리되는 형식 'type'을 가질 수 없습니다.

함수 범위 내에서만 CLR 또는 WinRT 개체를 정의할 수 있습니다.

다음 샘플에서는 C3145 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```
// C3145.cpp
// compile with: /clr
using namespace System;
ref class G {};

G ^ ptr;   // C3145
G ^ ptr2 = gcnew G;   // C3145

ref class GlobalObjects {
public:
   static G ^ ptr;   // OK
   static G ^ ptr2 = gcnew G;   // OK
};

int main() {
   G ^ ptr;   // OK
   G ^ ptr2 = gcnew G;   // OK
}
```

다음 샘플에서는 C3145 오류가 발생하는 경우를 보여 줍니다.

```
// C3145b.cpp
// compile with: /clr
ref class MyClass {
public:
   static int data;
};

interior_ptr<int> p = &(MyClass::data);   // C3145

void Test(interior_ptr<int> x) {}

int main() {
   MyClass ^ h_MyClass = gcnew MyClass;
   interior_ptr<int> p = &(h_MyClass->data);
}
```
