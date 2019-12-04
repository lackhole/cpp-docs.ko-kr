---
title: 컴파일러 오류 C2791
ms.date: 11/04/2016
f1_keywords:
- C2791
helpviewer_keywords:
- C2791
ms.assetid: 938ad1fb-75d9-4ce2-ad92-83d6249005b5
ms.openlocfilehash: d589094f117135474d1a8788867d2d571bbb5f5d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739547"
---
# <a name="compiler-error-c2791"></a>컴파일러 오류 C2791

' super '를 잘못 사용 했습니다. ' class '에 기본 클래스가 없습니다.

[슈퍼](../../cpp/super.md) 키워드는 기본 클래스가 없는 클래스의 멤버 함수 컨텍스트 내에서 사용 되었습니다.

다음 샘플에서는 C2791를 생성 합니다.

```cpp
// C2791.cpp
struct D {
   void mf() {
      __super::mf();   // C2791
   }
};
```
