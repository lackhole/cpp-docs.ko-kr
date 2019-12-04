---
title: 컴파일러 오류 C2378
ms.date: 11/04/2016
f1_keywords:
- C2378
helpviewer_keywords:
- C2378
ms.assetid: 507a91c6-ca72-48df-b3a4-2cf931c86806
ms.openlocfilehash: 63063ec98bbc4d42f3237fd42e42b9fdce489892
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745423"
---
# <a name="compiler-error-c2378"></a>컴파일러 오류 C2378

'identifier': 재정의. 형식 정의를 사용하여 기호를 오버로드할 수 없습니다.

식별자가 `typedef`로 다시 정의되었습니다.

다음 샘플에서는 C2378을 생성합니다.

```cpp
// C2378.cpp
// compile with: /c
int i;
typedef int i;   // C2378
typedef int b;   // OK
```
