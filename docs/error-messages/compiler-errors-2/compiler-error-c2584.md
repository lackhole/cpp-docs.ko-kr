---
title: 컴파일러 오류 C2584
ms.date: 11/04/2016
f1_keywords:
- C2584
helpviewer_keywords:
- C2584
ms.assetid: 836e2c0a-86c0-4742-b432-beb0191ad20e
ms.openlocfilehash: 2c3b10ecd6808ccd864ecf877fe9f1d0e9f30a3a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74748634"
---
# <a name="compiler-error-c2584"></a>컴파일러 오류 C2584

' Class ': 직접 기본 ' Base2 '에 액세스할 수 없습니다. 이미 ' Base1 '의 기본입니다.

`Class`는 이미 `Base1`에서 직접 파생 됩니다. `Base2`도 `Base1`에서 파생 됩니다. `Class`는 `Base1` 다시 상속 (간접적)을 의미 하기 때문에 `Base2`에서 파생 될 수 없습니다. `Base1`는 이미 직접 기본 클래스 이므로 유효 하지 않습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2584를 생성 합니다.

```cpp
// C2584.cpp
// compile with: /c
struct A1 {
   virtual int MyFunction();
};

struct A2 {
    virtual int MyFunction();
};

struct B1: public virtual A1, virtual A2 {
    virtual int MyFunction();
};

struct B2: public virtual A2, virtual A1 {
    virtual int MyFunction();
};

struct C: virtual B1, B2 {
    virtual int MyFunction();
};

struct Z : virtual B2, virtual C {   // C2584
// try the following line insted
// struct Z : virtual C {
    virtual int MyFunction();
};
```
