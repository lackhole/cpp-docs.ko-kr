---
title: 컴파일러 오류 C2809
ms.date: 11/04/2016
f1_keywords:
- C2809
helpviewer_keywords:
- C2809
ms.assetid: ce796b8e-1a8c-4074-995d-1ad09afd0e93
ms.openlocfilehash: d9dffabf318d51a97c172ecee2e4b2d4183a81f3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62281900"
---
# <a name="compiler-error-c2809"></a>컴파일러 오류 C2809

'operator o'에 정식 매개 변수가 없음

연산자에 필요한 매개 변수를 없습니다.

다음 샘플에서는 C2809 오류가 생성 됩니다.

```
// C2809.cpp
// compile with: /c
class A{};
int operator+ ();   // C2809
int operator+ (A);   // OK
```