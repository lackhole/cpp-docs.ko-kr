---
title: 컴파일러 오류 C2661
ms.date: 11/04/2016
f1_keywords:
- C2661
helpviewer_keywords:
- C2661
ms.assetid: 60021467-71cd-451b-9877-23840c69309f
ms.openlocfilehash: 14052fa3676396fe2ffc6ca86196025e7adab7d6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360349"
---
# <a name="compiler-error-c2661"></a>컴파일러 오류 C2661

'function': 오버 로드 된 함수가 없는 숫자 매개 변수를 사용 합니다.

가능한 원인:

1. 함수 호출에서 실제 매개 변수가 잘못 되었습니다.

1. 함수 선언이 없습니다.

다음 샘플에서는 C2661 오류가 생성 됩니다.

```
// C2661.cpp
void func( int ){}
void func( int, int ){}
int main() {
   func( );   // C2661 func( void ) was not declared
   func( 1 );   // OK func( int ) was declared
}
```