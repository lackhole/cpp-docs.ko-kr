---
title: 컴파일러 오류 C2499
ms.date: 11/04/2016
f1_keywords:
- C2499
helpviewer_keywords:
- C2499
ms.assetid: b323ff4d-b3c1-4bfd-b052-ae7292d53222
ms.openlocfilehash: 29fbb691304f9fc101f2367e014ae1e4e2231ff0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756983"
---
# <a name="compiler-error-c2499"></a>컴파일러 오류 C2499

' class ': 클래스는 자체 기본 클래스가 될 수 없습니다.

정의 하는 클래스를 기본 클래스로 지정 하려고 했습니다.

다음 샘플에서는 C2499를 생성 합니다.

```cpp
// C2499.cpp
// compile with: /c
class CMyClass : public CMyClass {};   // C2499
class CMyClass{};   // OK
```
