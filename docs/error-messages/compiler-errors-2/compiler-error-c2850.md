---
title: 컴파일러 오류 C2850
ms.date: 11/04/2016
f1_keywords:
- C2850
helpviewer_keywords:
- C2850
ms.assetid: f3efe86c-4168-4e76-a133-3f8314c69f51
ms.openlocfilehash: 0a87767bb9194a0a9858dd1734abbe516ffcfac0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758504"
---
# <a name="compiler-error-c2850"></a>컴파일러 오류 C2850

' 구문 ': 파일 범위 에서만 사용할 수 있습니다. 중첩 된 구문에 포함 될 수 없습니다.

일부 pragma와 같은 구문은 전역 범위에만 나타날 수 있습니다.

다음 샘플에서는 C2850를 생성 합니다.

```cpp
// C2850.cpp
// compile with: /c /Yc
// try the following line instead
// #pragma hdrstop
namespace X {
   #pragma hdrstop   // C2850
};
```
