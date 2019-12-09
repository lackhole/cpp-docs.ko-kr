---
title: 컴파일러 오류 C2287
ms.date: 11/04/2016
f1_keywords:
- C2287
helpviewer_keywords:
- C2287
ms.assetid: 64556299-4e1f-4437-88b7-2464fc0b95bb
ms.openlocfilehash: 234d0e85d0d6772340797fb6880e0ef79d4191ef
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759141"
---
# <a name="compiler-error-c2287"></a>컴파일러 오류 C2287

' class ': 상속 표현: ' representation1 '이 (가) 필요한 ' representation2 ' 보다 일반적이 아닙니다.

클래스가 필요한 것 보다 간단한 표현으로 선언 되었습니다.

다음 샘플에서는 C2287를 생성 합니다.

```cpp
// C2287.cpp
// compile with: /vmg /c
class __single_inheritance X;
class __single_inheritance Y;

struct A { };
struct B { };
struct X : A, B { };  // C2287  X uses multiple inheritance
struct Y : A { };  // OK
```
