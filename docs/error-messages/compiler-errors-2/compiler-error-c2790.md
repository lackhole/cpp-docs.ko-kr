---
title: 컴파일러 오류 C2790
ms.date: 11/04/2016
f1_keywords:
- C2790
helpviewer_keywords:
- C2790
ms.assetid: 38d4fce1-ba00-413d-8bc1-e8aa43d7bc1f
ms.openlocfilehash: c63fe7bb3686692818337e890de7fe4c80a18158
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739560"
---
# <a name="compiler-error-c2790"></a>컴파일러 오류 C2790

' super ':이 키워드는 클래스 멤버 함수의 본문 내 에서만 사용할 수 있습니다.

이 오류 메시지는 사용자가 멤버 함수의 [컨텍스트 외부에서](../../cpp/super.md) 키워드를 사용 하려고 할 때 나타납니다.

다음 샘플에서는 C2790를 생성 합니다.

```cpp
// C2790.cpp
void f() {
   __super::g();   // C2790
}
```
