---
title: 컴파일러 오류 C2270
ms.date: 11/04/2016
f1_keywords:
- C2270
helpviewer_keywords:
- C2270
ms.assetid: b52c068e-0b61-42e7-b775-4d57b3ddcba0
ms.openlocfilehash: 67dc970ffb5dac218072ff98046f88c31a9c2db9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758725"
---
# <a name="compiler-error-c2270"></a>컴파일러 오류 C2270

' function ': 비멤버 함수에는 한정자를 사용할 수 없습니다.

비멤버 함수는 [const](../../cpp/const-cpp.md), [volatile](../../cpp/volatile-cpp.md)또는 다른 메모리 모델 한정자를 사용 하 여 선언 됩니다.

다음 샘플에서는 C2270를 생성 합니다.

```cpp
// C2270.cpp
// compile with: /c
void func1(void) const;   // C2270, nonmember function

void func2(void);

class CMyClass {
public:
   void func2(void) const;
};
```
