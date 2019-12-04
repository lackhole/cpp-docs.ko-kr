---
title: 컴파일러 오류 C3452
ms.date: 11/04/2016
f1_keywords:
- C3452
helpviewer_keywords:
- C3452
ms.assetid: e5293dcf-cb70-4133-ae2a-0bb496950ba0
ms.openlocfilehash: c491217f01d8e78375401b54faa48d9db410ccad
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756723"
---
# <a name="compiler-error-c3452"></a>컴파일러 오류 C3452

목록 인수 멤버가 상수가 아닙니다.

인수가 컴파일 시간에 계산할 수 있는 값인 상수가 필요한 특성에 전달되었습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3452를 생성합니다.

```cpp
// C3452.cpp
// compile with: /c
int i;
[module( name="mod", type=dll, custom={i} ) ];   // C3452
// try the following line instead
// [module( name="mod", type=dll, custom={"a"} ) ];
```
