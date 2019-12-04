---
title: 컴파일러 오류 C3075
ms.date: 11/04/2016
f1_keywords:
- C3075
helpviewer_keywords:
- C3075
ms.assetid: f431daa9-e0fa-48f0-a5c3-f99be96b55e3
ms.openlocfilehash: 345cdd17b9da0be8f8d6e9f7b5f48624ade412bd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761584"
---
# <a name="compiler-error-c3075"></a>컴파일러 오류 C3075

'instance': 참조 형식 'type'의 인스턴스는 값 형식에 포함할 수 없습니다.

값 형식이 참조 형식의 인스턴스를 포함할 수 없습니다.

자세한 내용은 [ C++ 참조 형식에 대 한 스택 의미 체계](../../dotnet/cpp-stack-semantics-for-reference-types.md)를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3075를 생성합니다.

```cpp
// C3075.cpp
// compile with: /clr /c
ref struct U {};
value struct X {
   U y;   // C3075
};

ref struct Y {
   U y;   // OK
};
```
