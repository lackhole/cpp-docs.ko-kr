---
title: 컴파일러 오류 C2466
ms.date: 11/04/2016
f1_keywords:
- C2466
helpviewer_keywords:
- C2466
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
ms.openlocfilehash: 516f9b024947e0100a753e4e010a5b51b1fb24a1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62230531"
---
# <a name="compiler-error-c2466"></a>컴파일러 오류 C2466

상수 크기 0의 배열을 할당할 수 없습니다.

배열 할당 되었거나 0 크기를 사용 하 여 선언 됩니다. 배열 크기에 대 한 상수 식에는 0 보다 큰 정수 여야 합니다. 배열 첨자가 0 선언은 Microsoft 확장 이며만 클래스, 구조체 또는 공용 구조체 멤버에 대해서만 유효 ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).

다음 샘플에서는 C2466 오류가 생성 됩니다.

```
// C2466.cpp
// compile with: /c
int i[0];   // C2466
int j[1];   // OK
char *p;
```