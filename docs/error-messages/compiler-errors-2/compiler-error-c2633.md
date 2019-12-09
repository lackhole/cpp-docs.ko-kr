---
title: 컴파일러 오류 C2633
ms.date: 11/04/2016
f1_keywords:
- C2633
helpviewer_keywords:
- C2633
ms.assetid: a7aceb65-4255-42d6-a8fb-e3cb6c4d2270
ms.openlocfilehash: a2e4ca81194968fb50a5442cab3d229a25b8be1b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754682"
---
# <a name="compiler-error-c2633"></a>컴파일러 오류 C2633

' identifier ': ' inline '은 생성자에 대해 유일 하 게 올바른 저장소 클래스입니다.

생성자는 인라인이 아닌 저장소 클래스로 선언 됩니다.

다음 샘플에서는 C2633를 생성 합니다.

```cpp
// C2633.cpp
// compile with: /c
class C {
   extern C();   // C2633, not inline
   inline C();   // OK
};
```
