---
title: 컴파일러 오류 C2846
ms.date: 11/04/2016
f1_keywords:
- C2846
helpviewer_keywords:
- C2846
ms.assetid: bc090ec2-5410-4112-9ec6-261325374375
ms.openlocfilehash: eef558301ce2d623ef78aab40a7a054cd73037df
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750613"
---
# <a name="compiler-error-c2846"></a>컴파일러 오류 C2846

' constructor ': 인터페이스에는 생성자를 사용할 수 없습니다.

시각적 C++ [인터페이스](../../cpp/interface.md) 에는 생성자를 사용할 수 없습니다.

다음 샘플에서는 C2846를 생성 합니다.

```cpp
// C2846.cpp
// compile with: /c
__interface C {
   C();   // C2846 constructor not allowed in an interface
};
```
