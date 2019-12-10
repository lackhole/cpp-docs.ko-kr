---
title: 컴파일러 오류 C3865
ms.date: 11/04/2016
f1_keywords:
- C3865
helpviewer_keywords:
- C3865
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
ms.openlocfilehash: 960c795fe934433e4e3cf79e4c01c49d00205b9b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761493"
---
# <a name="compiler-error-c3865"></a>컴파일러 오류 C3865

' calling_convention ': 네이티브 멤버 함수에만 사용할 수 있습니다.

호출 규칙은 전역 함수 또는 관리 되는 멤버 함수에 대 한 함수에서 사용 되었습니다. 호출 규칙은 네이티브 (관리 되지 않는) 멤버 함수 에서만 사용할 수 있습니다.

자세한 내용은 [호출 규칙](../../cpp/calling-conventions.md)을 참조 하세요.

다음 샘플에서는 C3865를 생성 합니다.

```cpp
// C3865.cpp
// compile with: /clr
// processor: x86
void __thiscall Func(){}   // C3865

// OK
struct MyType {
   void __thiscall Func(){}
};
```
