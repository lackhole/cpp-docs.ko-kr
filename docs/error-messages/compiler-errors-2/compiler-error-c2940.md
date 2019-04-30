---
title: 컴파일러 오류 C2940
ms.date: 11/04/2016
f1_keywords:
- C2940
helpviewer_keywords:
- C2940
ms.assetid: af6bf2bf-8de6-4cfd-bbf0-4c6b32a30edf
ms.openlocfilehash: c5445b7083d11f1439d3e171d35c3ca39411310d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301918"
---
# <a name="compiler-error-c2940"></a>컴파일러 오류 C2940

'class': type-class-id가 지역 typedef로 재정의됩니다.

제네릭 또는 템플릿 클래스를 지역 `typedef`로 사용할 수 없습니다.

다음 샘플에서는 C2940을 생성합니다.

```
// C2940.cpp
template<class T>
struct TC {};
int main() {
   typedef int TC<int>;   // C2940
   typedef int TC;   // OK
}
```

C2940은 제네릭을 사용하는 경우에도 발생할 수 있습니다.

```
// C2940b.cpp
// compile with: /clr
generic<class T>
ref struct GC { };

int main() {
   typedef int GC<int>;   // C2940
   typedef int GC;
}
```