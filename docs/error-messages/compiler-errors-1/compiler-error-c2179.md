---
title: 컴파일러 오류 C2179
ms.date: 11/04/2016
f1_keywords:
- C2179
helpviewer_keywords:
- C2179
ms.assetid: f929bfc6-3964-4e54-87d6-7529b9b6c0b9
ms.openlocfilehash: 4a8abd8d862d4d6b08b1d0efd1d47d0413b60a81
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385994"
---
# <a name="compiler-error-c2179"></a>컴파일러 오류 C2179

'type': 특성 인수에서 형식 매개 변수를 사용할 수 없습니다

제네릭 형식 매개 변수는 런타임에 확인 됩니다. 그러나 특성 매개 변수는 컴파일 타임에 확인 되어야 합니다. 따라서 제네릭 형식 매개 변수 특성에 대 한 인수로 사용할 수 없습니다.

## <a name="example"></a>예제

다음 샘플 C2179를 생성합니다.

```
// C2179.cpp
// compile with: /clr
using namespace System;

public ref struct Attr : Attribute {
   Attr(Type ^ a) {
      x = a;
   }

   Type ^ x;
};

ref struct G {};

generic<typename T>
public ref class Z {
public:
   Type ^ d;
   [Attr(T::typeid)]   // C2179
   // try the following line instead
   // [Attr(G::typeid)]
   T t;
};
```