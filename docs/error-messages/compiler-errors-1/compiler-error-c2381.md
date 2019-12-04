---
title: 컴파일러 오류 C2381
ms.date: 11/04/2016
f1_keywords:
- C2381
helpviewer_keywords:
- C2381
ms.assetid: cc765f67-64ac-406f-93ef-ae7d548d58d7
ms.openlocfilehash: 834b9939a99c694c702bb268b928575b4beb8856
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745397"
---
# <a name="compiler-error-c2381"></a>컴파일러 오류 C2381

' function ': 재정의 __declspec (noreturn)이 다릅니다.

함수를 선언 하 고 정의 했지만 정의가 [noreturn](../../cpp/noreturn.md) `__declspec` 한정자를 사용 했습니다. `noreturn`를 사용 하 여 함수의 재정의를 구성 합니다. 선언 및 정의는 `noreturn`사용에 동의 해야 합니다.

다음 샘플에서는 C2381를 생성 합니다.

```cpp
// C2381.cpp
// compile with: /c
void f1();
void __declspec(noreturn) f1() {}   // C2381
void __declspec(noreturn) f2() {}   // OK
```
