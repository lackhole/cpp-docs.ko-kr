---
title: 컴파일러 오류 C2352
ms.date: 11/04/2016
f1_keywords:
- C2352
helpviewer_keywords:
- C2352
ms.assetid: 0efad8cb-659f-4b3e-8f6f-9f8ec44d345c
ms.openlocfilehash: 387738faa5b55e60cbb9df2185efcb94098011d7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388802"
---
# <a name="compiler-error-c2352"></a>컴파일러 오류 C2352

'class::function': 비정적 멤버 함수를 잘못 호출했습니다.

`static` 멤버 함수가 비정적 멤버 함수를 호출했습니다. 또는 비정적 멤버 함수가 클래스 외부에서 정적 함수로 호출되었습니다.

다음 샘플에서는 C2352를 생성하고 해결 방법을 보여 줍니다.

```
// C2352.cpp
// compile with: /c
class CMyClass {
public:
   static void func1();
   void func2();
   static void func3() {
      func2();   // C2352 calls nonstatic func2
      func1();   // OK calls static func1
   }
};
```

다음 샘플에서는 C2352를 생성하고 해결 방법을 보여 줍니다.

```
// C2352b.cpp
class MyClass {
public:
   void MyFunc() {}
   static void MyFunc2() {}
};

int main() {
   MyClass::MyFunc();   // C2352
   MyClass::MyFunc2();   // OK
}
```