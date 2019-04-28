---
title: 컴파일러 오류 C2355
ms.date: 11/04/2016
f1_keywords:
- C2355
helpviewer_keywords:
- C2355
ms.assetid: 0a947881-d61f-4f98-8409-32140f39500b
ms.openlocfilehash: 80871a73a7c3b4ad04b475539015f85d21ae88b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302646"
---
# <a name="compiler-error-c2355"></a>컴파일러 오류 C2355

'this': 비정적 멤버 함수 또는 비정적 데이터 멤버 이니셜라이저 안에서만 참조할 수 있습니다.

`this` 포인터는 비정적 멤버 함수 또는 비정적 데이터 멤버 이니셜라이저 내에서만 유효합니다. 이 오류는 클래스 선언 외부에서 멤버 함수 정의의 클래스 범위가 제대로 정규화되지 않은 경우 발생할 수 있습니다. 또한 `this` 포인터가 클래스에 선언되지 않은 함수에서 사용되는 경우에도 오류가 발생할 수 있습니다.

이 문제를 해결하려면 멤버 함수 정의가 클래스의 멤버 함수 선언과 일치하는지, 정적으로 선언되지 않았는지 확인합니다. 데이터 멤버 이니셜라이저의 경우 데이터 멤버가 정적으로 선언되지 않았는지 확인합니다.

다음 샘플에서는 C2355를 생성하고 해결 방법을 보여 줍니다.

```
// C2355.cpp
// compile with: /c
class MyClass {};
MyClass *p = this;   // C2355

// OK
class MyClass2 {
public:
   void Test() {
      MyClass2 *p = this;
   }
};
```