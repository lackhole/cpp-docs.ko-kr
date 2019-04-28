---
title: 컴파일러 오류 C2807
ms.date: 11/04/2016
f1_keywords:
- C2807
helpviewer_keywords:
- C2807
ms.assetid: bd7a207a-f379-4de6-8ee8-c7cab78b3480
ms.openlocfilehash: 5e3fd05b1c2473efbc1cd102056c73b2f221981d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62281919"
---
# <a name="compiler-error-c2807"></a>컴파일러 오류 C2807

'operator o' 후 위 두 번째 정식 매개 변수 'int' 이어야 합니다.

후 위 연산자는 두 번째 매개 변수 형식이 잘못 되었습니다.

다음 샘플에서는 C2807 오류가 생성 됩니다.

```
// C2807.cpp
// compile with: /c
class X {
public:
   X operator++ ( X );   // C2807 nonvoid parameter
   X operator++ ( int );   // OK, int parameter
};
```