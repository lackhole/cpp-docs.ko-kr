---
title: 컴파일러 오류 C2160
ms.date: 11/04/2016
f1_keywords:
- C2160
helpviewer_keywords:
- C2160
ms.assetid: a1f694a7-fb16-4437-b7f5-a1af6da94bc5
ms.openlocfilehash: 0cfc0822ab790a456c6fa56142047c1826257477
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740860"
---
# <a name="compiler-error-c2160"></a>컴파일러 오류 C2160

매크로 정의 시작에 '##'이 올 수 없습니다.

매크로 정의가 토큰 붙여넣기 연산자(##)로 시작되었습니다.

다음 샘플에서는 C2160을 생성합니다.

```cpp
// C2160.cpp
// compile with: /c
#define mac(a,b) #a   // OK
#define mac(a,b) ##a   // C2160
```
