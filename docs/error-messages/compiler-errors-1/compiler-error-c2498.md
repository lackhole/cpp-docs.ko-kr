---
title: 컴파일러 오류 C2498
ms.date: 11/04/2016
f1_keywords:
- C2498
helpviewer_keywords:
- C2498
ms.assetid: 0839f12c-aaa4-4a02-bb33-7f072715dd14
ms.openlocfilehash: 2b6f6469a221c914e0eef9e190c79a2b2706e651
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756996"
---
# <a name="compiler-error-c2498"></a>컴파일러 오류 C2498

' function ': ' novtable '는 클래스 선언 또는 정의에만 적용할 수 있습니다.

이 오류는 함수와 함께 `__declspec(novtable)`를 사용 하 여 발생할 수 있습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2498를 생성 합니다.

```cpp
// C2498.cpp
// compile with: /c
void __declspec(novtable) f() {}   // C2498
class __declspec(novtable) A {};   // OK
```
