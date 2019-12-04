---
title: 컴파일러 오류 C2161
ms.date: 11/04/2016
f1_keywords:
- C2161
helpviewer_keywords:
- C2161
ms.assetid: d6798821-13bb-4e60-924f-85f7bf955387
ms.openlocfilehash: dd75fb4ba035f21a71fff1f345c0c397415bc0ec
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758426"
---
# <a name="compiler-error-c2161"></a>컴파일러 오류 C2161

매크로 정의 끝에 '##'이 올 수 없습니다.

매크로 정의가 토큰 붙여넣기 연산자(##)로 종료되었습니다.

다음 샘플에서는 C2161 오류가 발생하는 경우를 보여 줍니다.

```cpp
// C2161.cpp
// compile with: /c
#define mac(a,b) a   // OK
#define mac(a,b) a##   // C2161
```
