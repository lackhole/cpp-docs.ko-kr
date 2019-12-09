---
title: 컴파일러 오류 C2086
ms.date: 11/04/2016
f1_keywords:
- C2086
helpviewer_keywords:
- C2086
ms.assetid: 4329bf72-90c8-444c-8524-4ef75e6b2139
ms.openlocfilehash: 417763e8c26918d3cd83702b283244d1c13d9d1f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74735751"
---
# <a name="compiler-error-c2086"></a>컴파일러 오류 C2086

' identifier ': 재정의

식별자가 두 번 이상 정의 되었거나 후속 선언이 이전 선언과 다른 경우

C2086는 참조 C# 된 어셈블리에 대 한 증분 빌드의 결과일 수도 있습니다. 이 오류 C# 를 해결 하려면 어셈블리를 다시 빌드하십시오.

다음 샘플에서는 C2086를 생성 합니다.

```cpp
// C2086.cpp
main() {
  int a;
  int a;   // C2086 not an error in ANSI C
}
```
