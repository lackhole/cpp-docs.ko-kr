---
title: 컴파일러 오류 C2516
ms.date: 11/04/2016
f1_keywords:
- C2516
helpviewer_keywords:
- C2516
ms.assetid: cd3accc1-0179-4a13-9587-616908c4ad1d
ms.openlocfilehash: fb0636edd621de06bea553c9975626249ae06d80
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746502"
---
# <a name="compiler-error-c2516"></a>컴파일러 오류 C2516

' name ': 올바른 기본 클래스가 아닙니다.

클래스는 `typedef` 문에 의해 정의 된 형식 이름에서 파생 됩니다.

다음 샘플에서는 C2516를 생성 합니다.

```cpp
// C2516.cpp
typedef unsigned long ulong;
class C : public ulong {}; // C2516
```
