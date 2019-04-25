---
title: 컴파일러 오류 C3254
ms.date: 11/04/2016
f1_keywords:
- C3254
helpviewer_keywords:
- C3254
ms.assetid: 93427b10-fa72-4e43-80d1-1a6e122f9f40
ms.openlocfilehash: 7e051c6c44d3b85f6f3faaf5380ecf54cba5d73c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173507"
---
# <a name="compiler-error-c3254"></a>컴파일러 오류 C3254

'명시적 재정의': 클래스 명시적 재정의 'override' 포함 되지만 함수 선언을 포함 하는 인터페이스에서 파생 되지 않습니다

경우 있습니다 [명시적으로 재정의](../../cpp/explicit-overrides-cpp.md) 메서드를 재정의 포함 하는 클래스 파생 되어야 합니다를 직접 또는 간접적으로, 재정의 하는 함수가 포함 된 형식에서입니다.

다음 샘플에서는 C3254를 생성합니다.

```
// C3254.cpp
__interface I
{
   void f();
};

__interface I1 : I
{
};

struct A /* : I1 */
{
   void I1::f()
   {   // C3254, uncomment : I1 to resolve this C3254
   }
};

int main()
{
}
```