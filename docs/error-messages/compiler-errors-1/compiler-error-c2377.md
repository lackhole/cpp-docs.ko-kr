---
title: 컴파일러 오류 C2377
ms.date: 11/04/2016
f1_keywords:
- C2377
helpviewer_keywords:
- C2377
ms.assetid: f7660965-bf4c-4cd9-8307-1bd7016678a1
ms.openlocfilehash: a1e8c50f7e5d822571daeefffc93d3e8c572c01b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745501"
---
# <a name="compiler-error-c2377"></a>컴파일러 오류 C2377

'identifier': 재정의. 다른 기호를 사용하여 형식 정의를 오버로드할 수 없습니다.

`typedef` 식별자가 다시 정의되었습니다.

다음 샘플에서는 C2377을 생성합니다.

```cpp
// C2377.cpp
// compile with: /c
typedef int i;
int i;   // C2377
int j;   // OK
```
