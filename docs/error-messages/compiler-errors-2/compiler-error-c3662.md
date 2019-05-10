---
title: 컴파일러 오류 C3662
ms.date: 11/04/2016
f1_keywords:
- C3662
helpviewer_keywords:
- C3662
ms.assetid: 61bd3e41-a86b-42c0-be89-d992d3906ff1
ms.openlocfilehash: 28d8df02d63fc1b16a392a2df83524cd616d5ab3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400307"
---
# <a name="compiler-error-c3662"></a>컴파일러 오류 C3662

'member' : 재정의 지정자 'specifier'는 관리되는 클래스 또는 WinRT 클래스의 멤버 함수에만 사용할 수 있습니다.

재정의 지정자가 네이티브 형식의 멤버에 사용되었으며, 이는 허용되지 않습니다.

자세한 내용은 [명시적으로 재정의](../../extensions/explicit-overrides-cpp-component-extensions.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3662 오류가 발생하는 경우를 보여 줍니다.

```
// C3662.cpp
// compile with: /clr /c
struct S {
   virtual void f();
};

struct S1 : S {
   virtual void f() new;   // C3662
};

ref struct T {
   virtual void f();
};

ref struct T1 : T {
   virtual void f() new;   // OK
};
```