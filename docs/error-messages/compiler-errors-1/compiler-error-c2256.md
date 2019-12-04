---
title: 컴파일러 오류 C2256
ms.date: 11/04/2016
f1_keywords:
- C2256
helpviewer_keywords:
- C2256
ms.assetid: 171fa2bc-8c72-49cd-afe5-d723b7acd3c5
ms.openlocfilehash: b362a236953701278c57d2b738a6303e83b7637c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758816"
---
# <a name="compiler-error-c2256"></a>컴파일러 오류 C2256

' function '에서 friend 지정자를 잘못 사용 하였습니다.

소멸자 또는 생성자를 [friend](../../cpp/friend-cpp.md)로 지정할 수 없습니다.

다음 샘플에서는 C2256를 생성 합니다.

```cpp
// C2256.cpp
// compile with: /c
class C {
public:
   friend ~C();   // C2256
   ~C();   // OK
};
```
