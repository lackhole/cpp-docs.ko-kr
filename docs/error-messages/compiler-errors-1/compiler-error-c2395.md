---
title: 컴파일러 오류 C2395
ms.date: 11/04/2016
f1_keywords:
- C2395
helpviewer_keywords:
- C2395
ms.assetid: 2d9e3b28-8c2c-4f41-a57f-61ef88fc2af0
ms.openlocfilehash: 2ac59856770b04dd3c4ea14360e0a83dd99f2150
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744942"
---
# <a name="compiler-error-c2395"></a>컴파일러 오류 C2395

'your_type::operator'op'' : CLR 또는 WinRT 연산자가 잘못되었습니다. 하나 이상의 매개 변수가 ' t ', ' t% ' &, ' t ', ' t ^ ', ' t ^ &% ', ' t = ' your_type ' 형식 이어야 합니다.

Windows 런타임 또는 관리되는 형식의 연산자는 형식이 연산자 반환 값의 형식과 동일한 매개 변수를 하나 이상 사용할 수 없습니다.

다음 샘플에서는 C2395를 생성하고 해결 방법을 보여 줍니다.

```cpp
// C2395.cpp
// compile with: /clr /c
value struct V {
   static V operator *(int i, char c);   // C2395

   // OK
   static V operator *(V v, char c);
   // or
   static V operator *(int i, V& rv);
};
```
