---
title: 컴파일러 오류 C2932
ms.date: 11/04/2016
f1_keywords:
- C2932
helpviewer_keywords:
- C2932
ms.assetid: c28e88d9-e654-4367-bfb4-13c780bca9bd
ms.openlocfilehash: 004767d4adbd87a2a21ec73fa720d6992eb31044
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386072"
---
# <a name="compiler-error-c2932"></a>컴파일러 오류 C2932

'class': type-class-id가 'identifier'의 데이터 멤버로 재정의되었습니다.

제네릭 또는 템플릿 클래스를 데이터 멤버로 사용할 수 없습니다.

다음 샘플에서는 C2932를 생성합니다.

```
// C2932.cpp
// compile with: /c
template<class T>
struct TC {};

struct MyStruct {
   int TC<int>;   // C2932
   int TC;   // OK
};
```

C2932는 제네릭을 사용하는 경우에도 발생할 수 있습니다.

```
// C2932b.cpp
// compile with: /clr /c
generic<class T>
ref struct GC {};

struct MyStruct {
   int GC<int>;   // C2932
   int GC;   // OK
};
```