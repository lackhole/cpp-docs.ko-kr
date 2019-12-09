---
title: 컴파일러 오류 C2255
ms.date: 11/04/2016
f1_keywords:
- C2255
helpviewer_keywords:
- C2255
ms.assetid: 67dc4cb0-de6b-4405-bd64-d47736367a93
ms.openlocfilehash: 758c77b5f54404321eafcc55953c44d2ac7c5412
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758829"
---
# <a name="compiler-error-c2255"></a>컴파일러 오류 C2255

'element': 클래스 정의 외부에서 사용할 수 없습니다.

예를 들어 비멤버 함수를 `friend`로 선언했습니다.

다음 샘플에서는 C2255를 생성합니다.

```cpp
// C2255.cpp
// compile with: /c
class A {
private:
   void func1();
   friend void func2();
};

friend void func1() {}   // C2255
void func2(){}
```
