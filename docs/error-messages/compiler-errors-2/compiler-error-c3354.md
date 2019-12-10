---
title: 컴파일러 오류 C3354
ms.date: 11/04/2016
f1_keywords:
- C3354
helpviewer_keywords:
- C3354
ms.assetid: 185de401-231e-4999-a149-172ee4c69d84
ms.openlocfilehash: e5945b2112d1d03e4f18944d15028229cce4b668
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738598"
---
# <a name="compiler-error-c3354"></a>컴파일러 오류 C3354

'function': 대리자를 만드는 데 사용되는 함수는 'type' 반환 형식을 사용할 수 없습니다.

다음 형식은 `delegate`에 대한 반환 형식으로 부적합합니다.

- 함수 포인터

- 멤버 포인터

- 멤버 함수에 대한 포인터

- 함수에 대한 참조

- 멤버 함수에 대한 참조

다음 샘플에서는 C3354를 생성합니다.

```cpp
// C3354_2.cpp
// compile with: /clr /c
using namespace System;
typedef void ( *VoidPfn )();

delegate VoidPfn func(); // C3354
// try the following line instead
// delegate  void func();
```
