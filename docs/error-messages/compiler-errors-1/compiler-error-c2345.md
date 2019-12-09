---
title: 컴파일러 오류 C2345
ms.date: 11/04/2016
f1_keywords:
- C2345
helpviewer_keywords:
- C2345
ms.assetid: e1cc88b0-0223-4d07-975b-fa99956a82bd
ms.openlocfilehash: 85d9e312bafe0cf6c9390f7484281e1aefb22aab
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760025"
---
# <a name="compiler-error-c2345"></a>컴파일러 오류 C2345

align(value): 맞춤 값이 잘못되었습니다.

[align](../../cpp/align-cpp.md) 키워드에 허용 범위 외부의 값을 전달했습니다.

다음 코드에서는 C2345를 생성합니다.

```cpp
// C2345.cpp
// compile with: /c
__declspec(align(0)) int a;   // C2345
__declspec(align(1)) int a;   // OK
```
