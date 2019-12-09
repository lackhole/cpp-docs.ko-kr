---
title: 컴파일러 오류 C2528
ms.date: 11/04/2016
f1_keywords:
- C2528
helpviewer_keywords:
- C2528
ms.assetid: 2ea9d583-67a8-4b16-b35f-a50eeffc03c4
ms.openlocfilehash: f8712cfbd34e852cf852cf9758446849d75d8bdc
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756268"
---
# <a name="compiler-error-c2528"></a>컴파일러 오류 C2528

' name ': 참조에 대 한 포인터가 잘못 되었습니다.

참조에 대 한 포인터를 선언할 수 없습니다. 포인터를 선언 하기 전에 변수를 역참조 합니다.

다음 샘플에서는 C2528를 생성 합니다.

```cpp
// C2528.cpp
int i;
int &ir = i;
int & (*irptr) = ir;    // C2528
```
