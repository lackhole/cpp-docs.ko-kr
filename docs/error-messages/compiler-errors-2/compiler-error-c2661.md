---
title: 컴파일러 오류 C2661
ms.date: 11/04/2016
f1_keywords:
- C2661
helpviewer_keywords:
- C2661
ms.assetid: 60021467-71cd-451b-9877-23840c69309f
ms.openlocfilehash: e4d0e8a1c707374e0e93a5687351a9360fa17c0f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756047"
---
# <a name="compiler-error-c2661"></a>컴파일러 오류 C2661

' function ': 오버 로드 된 함수에는 숫자 매개 변수를 사용 하지 않습니다.

가능한 원인

1. 함수 호출의 실제 매개 변수가 잘못 되었습니다.

1. 함수 선언이 없습니다.

다음 샘플에서는 C2661를 생성 합니다.

```cpp
// C2661.cpp
void func( int ){}
void func( int, int ){}
int main() {
   func( );   // C2661 func( void ) was not declared
   func( 1 );   // OK func( int ) was declared
}
```
