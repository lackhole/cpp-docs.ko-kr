---
title: 컴파일러 오류 C2466
ms.date: 11/04/2016
f1_keywords:
- C2466
helpviewer_keywords:
- C2466
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
ms.openlocfilehash: aba4de518b9296fadc4746540e4e738c74908617
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743824"
---
# <a name="compiler-error-c2466"></a>컴파일러 오류 C2466

상수 크기 0의 배열을 할당할 수 없습니다.

크기가 0 인 배열이 할당 되거나 선언 됩니다. 배열 크기에 대 한 상수 식은 0 보다 큰 정수 여야 합니다. 첨자가 0 인 배열 선언은 클래스, 구조체 또는 공용 구조체 멤버와 Microsoft 확장 ([/ze](../../build/reference/za-ze-disable-language-extensions.md)) 에서만 사용할 수 있습니다.

다음 샘플에서는 C2466를 생성 합니다.

```cpp
// C2466.cpp
// compile with: /c
int i[0];   // C2466
int j[1];   // OK
char *p;
```
