---
title: 컴파일러 경고(수준 3) C4636
ms.date: 11/04/2016
f1_keywords:
- C4636
helpviewer_keywords:
- C4636
ms.assetid: 59112a0f-850f-41c6-bd84-8ae8dc84706a
ms.openlocfilehash: 7327189a61e2545bb6003cd95e1ddb116f9f7c94
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401711"
---
# <a name="compiler-warning-level-3-c4636"></a>컴파일러 경고(수준 3) C4636

'construct': 태그에 적용된 XML 문서 주석에 비어 있지 않은 '' 특성이 필요합니다.

`cref`와 같은 태그에 값이 없었습니다.

## <a name="example"></a>예제

다음 샘플에서는 C4636을 생성합니다.

```
// C4636.cpp
// compile with: /clr /doc /W3 /c
/// <see cref=''/>
// /// <see cref='System::Exception'/>
ref struct A {   // C4636
   void f(int);
};

// OK
/// <see cref='System::Exception'/>
ref struct B {
   void f(int);
};
```