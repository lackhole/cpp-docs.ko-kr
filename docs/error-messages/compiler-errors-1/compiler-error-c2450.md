---
title: 컴파일러 오류 C2450
ms.date: 11/04/2016
f1_keywords:
- C2450
helpviewer_keywords:
- C2450
ms.assetid: 929f1c06-8774-468b-be2a-f428757875a2
ms.openlocfilehash: 3cbab274f8f7cd04d5fb86db69572e0b7fc1c04e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208973"
---
# <a name="compiler-error-c2450"></a>컴파일러 오류 C2450

'type' 형식의 switch 식은 올바르지 않습니다.

`switch` 식이 잘못 된 형식입니다. 정수 형식 또는 클래스 형식으로 계산 되어야 정수 형식으로 명확한 변환을 사용 하 여 합니다. 이 사용자 정의 형식으로 계산 되 면 변환 연산자를 제공 해야 합니다.

다음 샘플에서는 C2450를 생성합니다.

```
// C2450.cpp
class X {
public:
   int i;
} x;

class Y {
public:
   int i;
   operator int() { return i; }   // conversion operator
} y;

int main() {
   int j = 1;
   switch ( x ) {   // C2450, x is not type int
   // try the following line instead
   // switch ( y ) {
      default:  ;
   }
}
```