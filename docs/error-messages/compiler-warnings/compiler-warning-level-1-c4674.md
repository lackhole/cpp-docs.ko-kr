---
title: 컴파일러 경고(수준 1) C4674
ms.date: 11/04/2016
f1_keywords:
- C4674
helpviewer_keywords:
- C4674
ms.assetid: 638dae0b-b82c-4865-9599-72630827ca09
ms.openlocfilehash: b9428a593ff59cbdfa6d8eb369413a560b4a5ad2
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052549"
---
# <a name="compiler-warning-level-1-c4674"></a>컴파일러 경고(수준 1) C4674

'method'는 'static'으로 선언해야 하며 하나의 매개 변수만 가져야 합니다.

변환 연산자의 서명이 잘못되었습니다. 메서드는 사용자 정의 변환으로 간주되지 않습니다. 연산자 정의에 대 한 자세한 내용은 [사용자 정의 연산자 (C++/Cli)](../../dotnet/user-defined-operators-cpp-cli.md) 및 [사용자 정의 변환 (C++/cli)](../../dotnet/user-defined-conversions-cpp-cli.md)을 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C4674를 생성합니다.

```cpp
// C4674.cpp
// compile with: /clr /WX /W1 /LD
ref class G {
   int op_Implicit(int i) {   // C4674
      return 0;
   }
};
```
