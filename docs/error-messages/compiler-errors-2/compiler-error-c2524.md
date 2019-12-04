---
title: 컴파일러 오류 C2524
ms.date: 11/04/2016
f1_keywords:
- C2524
helpviewer_keywords:
- C2524
ms.assetid: e71d17f5-2fc2-416b-8dbd-e9bed85eb33a
ms.openlocfilehash: 1e53a0c08f07bf69378fbb7603f63c596f641355
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758660"
---
# <a name="compiler-error-c2524"></a>컴파일러 오류 C2524

' 소멸자 ': 소멸자/종료자에는 ' void ' 매개 변수 목록이 있어야 합니다.

소멸자 또는 종료자에 [void](../../cpp/void-cpp.md)가 아닌 매개 변수 목록이 있습니다. 다른 매개 변수 형식은 허용 되지 않습니다.

## <a name="example"></a>예제

재현 C2524 코드는 다음과 같습니다.

```cpp
// C2524.cpp
// compile with: /c
class A {
   A() {}
   ~A(int i) {}    // C2524
   // try the following line instead
   // ~A() {}
};
```

## <a name="example"></a>예제

재현 C2524 코드는 다음과 같습니다.

```cpp
// C2524_b.cpp
// compile with: /clr /c
ref struct I1 {
protected:
   !I1(int i);   // C2524
   // try the following line instead
   // !I1();
};
```
