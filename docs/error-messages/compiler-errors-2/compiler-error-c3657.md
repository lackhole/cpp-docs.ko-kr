---
title: 컴파일러 오류 C3657
ms.date: 11/04/2016
f1_keywords:
- C3657
helpviewer_keywords:
- C3657
ms.assetid: 89a28a18-4c17-43a1-bda6-deb52c32d203
ms.openlocfilehash: f979d5776bea5e8fb6e0255bdcdeaacb284932ac
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410488"
---
# <a name="compiler-error-c3657"></a>컴파일러 오류 C3657

소멸자가 명시적으로 재정의할 수 없습니다. 또는 명시적으로 재정의할 수

소멸자 또는 종료자 명시적으로 재정의할 수 없습니다. 자세한 내용은 [명시적으로 재정의](../../extensions/explicit-overrides-cpp-component-extensions.md)합니다.

## <a name="example"></a>예제

다음 샘플 C3657를 생성합니다.

```
// C3657.cpp
// compile with: /clr
public ref struct I {
   virtual ~I() { }
   virtual void a();
};

public ref struct D : I {
   virtual ~D() = I::~I {}   // C3657
   virtual void a() = I::a {}   // OK
};
```