---
title: 컴파일러 오류 C2272
ms.date: 11/04/2016
f1_keywords:
- C2272
helpviewer_keywords:
- C2272
ms.assetid: 1517706a-9c27-452e-9b10-3424b3d232bc
ms.openlocfilehash: fd6fdecd3a491ce5f068f4d51d413e6767aabe2f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758699"
---
# <a name="compiler-error-c2272"></a>컴파일러 오류 C2272

' function ': 정적 멤버 함수에는 한정자를 사용할 수 없습니다.

`static` 멤버 함수는 [const](../../cpp/const-cpp.md) 또는 [volatile](../../cpp/volatile-cpp.md)과 같은 메모리 모델 지정자를 사용 하 여 선언 되며, 이러한 한정자는 `static` 멤버 함수에서 허용 되지 않습니다.

다음 샘플에서는 C2272를 생성 합니다.

```cpp
// C2272.cpp
// compile with: /c
class CMyClass {
public:
   static void func1() const volatile;   // C2272  func1 is static
   void func2() const volatile;   // OK
};
```
