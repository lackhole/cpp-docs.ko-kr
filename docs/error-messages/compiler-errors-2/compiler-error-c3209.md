---
title: 컴파일러 오류 C3209
ms.date: 11/04/2016
f1_keywords:
- C3209
helpviewer_keywords:
- C3209
ms.assetid: 1de44e39-69d1-4894-8f89-ff92136e8e5d
ms.openlocfilehash: 79a5bc77f0e18a8e55954e25e67a836af8157596
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755137"
---
# <a name="compiler-error-c3209"></a>컴파일러 오류 C3209

' class ': 제네릭 클래스는 관리 되는 또는 WinRTclass 여야 합니다.

제네릭 클래스는 관리되는 클래스 또는 Windows 런타임 클래스여야 합니다.

다음 샘플에서는 C3209를 생성하고 해결 방법을 보여 줍니다.

```cpp
// C3209.cpp
// compile with: /clr
generic <class T>
class C {};   // C3209

// OK - ref class can be generic
generic <class T>
ref class D {};
```
