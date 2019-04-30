---
title: 컴파일러 오류 C3842
ms.date: 11/04/2016
f1_keywords:
- C3842
helpviewer_keywords:
- C3842
ms.assetid: 41a1a44a-c618-40a2-8d26-7da27d14095d
ms.openlocfilehash: a61a69aca53f7f8996d0261a57b749930ecc01cc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385513"
---
# <a name="compiler-error-c3842"></a>컴파일러 오류 C3842

'function': WinRT 또는 관리되는 형식의 멤버 함수에 'const' 및 'volatile' 한정자를 사용할 수 없습니다.

[const](../../cpp/const-cpp.md) 하 고 [volatile](../../cpp/volatile-cpp.md) Windows 런타임 또는 관리 되는 형식의 멤버 함수에서 지원 되지 않습니다.

다음 샘플에서는 C3842를 생성합니다.

```
// C3842a.cpp
// compile with: /clr /c
public ref struct A {
   void f() const {}   // C3842
   void f() volatile {}   // C3842

   void f() {}
};
```