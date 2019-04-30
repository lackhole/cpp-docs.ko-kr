---
title: 컴파일러 오류 C2255
ms.date: 11/04/2016
f1_keywords:
- C2255
helpviewer_keywords:
- C2255
ms.assetid: 67dc4cb0-de6b-4405-bd64-d47736367a93
ms.openlocfilehash: ae2c61257af3e1aca2d26ce5f8801999f7bb77c1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387088"
---
# <a name="compiler-error-c2255"></a>컴파일러 오류 C2255

'element': 클래스 정의 외부에서 사용할 수 없습니다.

예를 들어 비멤버 함수를 `friend`로 선언했습니다.

다음 샘플에서는 C2255를 생성합니다.

```
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