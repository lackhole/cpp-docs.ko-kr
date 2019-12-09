---
title: 컴파일러 오류 C3896
ms.date: 11/04/2016
f1_keywords:
- C3896
helpviewer_keywords:
- C3896
ms.assetid: eb8be0f6-5b4e-4d71-8285-8a2a94f8ba29
ms.openlocfilehash: f15cd73465f4210ed5e5e34bebe2122c0b88f722
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749271"
---
# <a name="compiler-error-c3896"></a>컴파일러 오류 C3896

' member ': 잘못 된 이니셜라이저:이 리터럴 데이터 멤버는 ' nullptr '로만 초기화할 수 있습니다.

[리터럴](../../extensions/literal-cpp-component-extensions.md) 데이터 멤버가 잘못 초기화 되었습니다.  자세한 내용은 [nullptr](../../extensions/nullptr-cpp-component-extensions.md) 를 참조 하세요.

다음 샘플에서는 C3896를 생성 합니다.

```cpp
// C3896.cpp
// compile with: /clr /c
ref class R{};

value class V {
   literal R ^ r = "test";   // C3896
   literal R ^ r2 = nullptr;   // OK
};
```
