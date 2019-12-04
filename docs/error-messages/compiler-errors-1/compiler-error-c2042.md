---
title: 컴파일러 오류 C2042
ms.date: 11/04/2016
f1_keywords:
- C2042
helpviewer_keywords:
- C2042
ms.assetid: e111788f-41ce-405a-9824-a4c1c26059e6
ms.openlocfilehash: 6bc66f5b3a7bd669ef06cac3b53631ff7948e8ad
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740392"
---
# <a name="compiler-error-c2042"></a>컴파일러 오류 C2042

signed/unsigned 키워드는 함께 사용할 수 없습니다.

키워드 `signed` 및 `unsigned` 가 단일 선언에서 사용되었습니다.

다음 샘플에서는 C2042를 생성합니다.

```cpp
// C2042.cpp
unsigned signed int i;   // C2042
```

가능한 해결 방법:

```cpp
// C2042b.cpp
// compile with: /c
unsigned int i;
signed int ii;
```
