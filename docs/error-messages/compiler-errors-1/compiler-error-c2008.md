---
title: 컴파일러 오류 C2008
ms.date: 11/04/2016
f1_keywords:
- C2008
helpviewer_keywords:
- C2008
ms.assetid: e748ccbe-ffd4-4008-aca7-e53c25225209
ms.openlocfilehash: 292f5c6ab9a4e14077f848ff57ff08adefeb09a1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757334"
---
# <a name="compiler-error-c2008"></a>컴파일러 오류 C2008

'character': 매크로 정의에 사용할 수 없습니다.

문자는 매크로 이름 바로 뒤에 표시 됩니다. 오류를 해결 하려면 매크로 이름 뒤에 공백이 있어야 합니다.

다음 샘플에서는 C2008를 생성 합니다.

```cpp
// C2008.cpp
#define TEST1"mytest1"    // C2008
```

가능한 해결 방법:

```cpp
// C2008b.cpp
// compile with: /c
#define TEST2 "mytest2"
```
