---
title: 컴파일러 오류 C2581
ms.date: 11/04/2016
f1_keywords:
- C2581
helpviewer_keywords:
- C2581
ms.assetid: 24a4e4c1-24d3-4e42-b760-7dcaf9740b16
ms.openlocfilehash: 03fc7e9da8a9b3a2e2c445f5b06395c2616f0d98
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755436"
---
# <a name="compiler-error-c2581"></a>컴파일러 오류 C2581

' type ': static ' operator = ' 함수가 잘못 되었습니다.

할당 (`=`) 연산자가 `static`잘못 선언 되었습니다. 할당 연산자를 `static`수 없습니다. 자세한 내용은 [사용자 정의 연산자 (C++/cli)](../../dotnet/user-defined-operators-cpp-cli.md)를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C2581를 생성 합니다.

```cpp
// C2581.cpp
// compile with: /clr /c
ref struct Y {
   static Y ^ operator = (Y^ me, int i);   // C2581
   Y^ operator =(int i);   // OK
};
```
