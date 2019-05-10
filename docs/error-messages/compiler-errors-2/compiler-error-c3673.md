---
title: 컴파일러 오류 C3673
ms.date: 11/04/2016
f1_keywords:
- C3673
helpviewer_keywords:
- C3673
ms.assetid: bb6d2079-05af-4e2c-be0e-75c892e6c590
ms.openlocfilehash: 9fd6920956d6a48ec7e1f15bf54ea8d75bad4aa5
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345430"
---
# <a name="compiler-error-c3673"></a>컴파일러 오류 C3673

'type': 클래스에 복사 생성자가 없습니다

사용자 정의 생성자를 사용 하는 CLR 참조 형식의 개체를 복사할 필요 합니다. 자세한 내용은 [ C++ 참조 형식에 대 한 스택 의미 체계](../../dotnet/cpp-stack-semantics-for-reference-types.md)합니다.

## <a name="example"></a>예제

다음 샘플 C3673를 생성합니다.

```
// C3673.cpp
// compile with: /clr
public ref struct R {
public:
   R() {}
   // Uncomment the following line to resolve.
   // R(R% p) {}
};

int main() {
   R r;
   R s = r;   // C3673
}
```

## <a name="example"></a>예제

다음 샘플 C3673를 생성합니다.

```
// C3673_b.cpp
// compile with: /clr /c
// C3673 expected
using namespace System;
[AttributeUsage(AttributeTargets::Class)]
ref class MyAttr : public Attribute {
public:
   MyAttr() {}
   // Uncomment the following line to resolve.
   // MyAttr(int i) {}
   property int Priority;
   property int Version;
};

[MyAttr]
ref class ClassA {};   // OK, no arguments

[MyAttr(Priority = 1)]
ref class ClassB {};   // OK, named argument

[MyAttr(123)]
ref class ClassC {};   // Positional argument

[MyAttr(123, Version = 1)]
ref class ClassD {};   // Positional and named
```