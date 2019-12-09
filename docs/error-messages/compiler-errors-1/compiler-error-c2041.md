---
title: 컴파일러 오류 C2041
ms.date: 11/04/2016
f1_keywords:
- C2041
helpviewer_keywords:
- C2041
ms.assetid: c9a33bb1-f9cf-47d6-bd21-7d867a8c37d5
ms.openlocfilehash: 7e148ced19e34a57172e3d606c6efdb2f5d012d6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740457"
---
# <a name="compiler-error-c2041"></a>컴파일러 오류 C2041

기본 ' number '의 ' character ' 숫자가 잘못 되었습니다.

지정 된 문자는 base의 올바른 숫자가 아닙니다 (예: 8 진수 또는 16 진수).

다음 샘플에서는 C2041를 생성 합니다.

```cpp
// C2041.cpp
int i = 081;   // C2041  8 is not a base 8 digit
```

가능한 해결 방법:

```cpp
// C2041b.cpp
// compile with: /c
int j = 071;
```
