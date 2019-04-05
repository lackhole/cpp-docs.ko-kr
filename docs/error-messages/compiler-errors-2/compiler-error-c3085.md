---
title: 컴파일러 오류 C3085
ms.date: 11/04/2016
f1_keywords:
- C3085
helpviewer_keywords:
- C3085
ms.assetid: 1ac40bf2-f63e-439e-8921-47e6dadc8354
ms.openlocfilehash: 01ebfa0007b9acc08742c57cc0528216eabb0441
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58774752"
---
# <a name="compiler-error-c3085"></a>컴파일러 오류 C3085

'constructor': 생성자는 'keyword'일 수 없습니다.

생성자가 잘못 선언되었습니다. 자세한 내용은 [Override Specifiers](../../extensions/override-specifiers-cpp-component-extensions.md) 를 참조하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3085를 생성합니다.

```
// C3085.cpp
// compile with: /c /clr
ref struct S {
   S() abstract;   // C3085
   S(S%) abstract;   // C3085
};

ref struct T {
   T() sealed {}   // C3085
   T(T%) sealed {}   // C3085
};
```