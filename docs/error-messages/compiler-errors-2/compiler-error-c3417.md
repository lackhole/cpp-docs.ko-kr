---
title: 컴파일러 오류 C3417
ms.date: 11/04/2016
f1_keywords:
- C3417
helpviewer_keywords:
- C3417
ms.assetid: 3e7869ea-8948-42fb-ba30-6ccafe499c35
ms.openlocfilehash: 93f287dd7173cc83a8c910d035f80a15c6a4f701
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756164"
---
# <a name="compiler-error-c3417"></a>컴파일러 오류 C3417

' member ': 값 형식은 사용자 정의 특수 멤버 함수를 포함할 수 없습니다.

값 형식은 기본 인스턴스 생성자, 소멸자 또는 복사 생성자와 같은 함수를 포함할 수 없습니다.

다음 샘플에서는 C3517를 생성 합니다.

```cpp
// C3417.cpp
// compile with: /clr /c
value class VC {
   VC(){}   // C3417

   // OK
   static VC(){}
   VC(int i){}
};
```
