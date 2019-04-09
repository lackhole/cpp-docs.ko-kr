---
title: 컴파일러 오류 C3225
ms.date: 11/04/2016
f1_keywords:
- C3225
helpviewer_keywords:
- C3225
ms.assetid: f5f66973-256e-4298-ac46-c87819cbde34
ms.openlocfilehash: cae0572002c849fb5aed771993d3a89ed82c726a
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58778314"
---
# <a name="compiler-error-c3225"></a>컴파일러 오류 C3225

'arg'에 대 한 제네릭 형식 인수는 'type' 일 수 없습니다, 그리고 값 형식 이어야 하거나 형식을 처리 해야 합니다.

제네릭 형식 인수에 올바른 형식의 없습니다.

자세한 내용은 [제네릭](../../extensions/generics-cpp-component-extensions.md)을 참조하세요.

## <a name="example"></a>예제

네이티브 형식 사용 하 여 제네릭 형식을 인스턴스화할 수 없습니다. 다음 샘플 C3225를 생성합니다.

```
// C3225.cpp
// compile with: /clr
class A {};

ref class B {};

generic <class T>
ref class C {};

int main() {
   C<A>^ c = gcnew C<A>;   // C3225
   C<B^>^ c2 = gcnew C<B^>;   // OK
}
```

## <a name="example"></a>예제

다음 샘플 C#을 사용 하 여 구성 요소를 만듭니다. 제약 조건이 제네릭 형식이 값 형식에만 인스턴스화할 수 있습니다 지정 하는지 확인 합니다.

```
// C3225_b.cs
// compile with: /target:library
// a C# program
public class MyList<T> where T: struct {}
```

## <a name="example"></a>예제

이 샘플 사용은 C#-구성 요소를 작성 하 고 MyList만 될 수 있는 제약 조건을 위반 이외의 값 형식인을 사용 하 여 인스턴스화할 <xref:System.Nullable>합니다. 다음 샘플 C3225를 생성합니다.

```
// C3225_c.cpp
// compile with: /clr
#using "C3225_b.dll"
ref class A {};
value class B {};
int main() {
   MyList<A> x;   // C3225
   MyList<B> y;   // OK
}
```