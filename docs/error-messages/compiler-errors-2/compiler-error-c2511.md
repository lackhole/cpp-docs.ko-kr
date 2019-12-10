---
title: 컴파일러 오류 C2511
ms.date: 11/04/2016
f1_keywords:
- C2511
helpviewer_keywords:
- C2511
ms.assetid: df999efe-fe2b-418b-bb55-4af6a0592631
ms.openlocfilehash: ff78cb50b274fe40d513739264bd7e9894bbed9d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746567"
---
# <a name="compiler-error-c2511"></a>컴파일러 오류 C2511

' identifier ': 오버 로드 된 멤버 함수를 ' class '에서 찾을 수 없습니다.

지정 된 매개 변수를 사용 하 여 선언 된 함수의 버전이 없습니다.  가능한 원인

1. 함수에 전달 된 매개 변수가 잘못 되었습니다.

1. 매개 변수가 잘못 된 순서로 전달 되었습니다.

1. 매개 변수 이름의 맞춤법이 잘못 되었습니다.

다음 샘플에서는 C2511를 생성 합니다.

```cpp
// C2511.cpp
// compile with: /c
class C {
   int c_2;
   int Func(char *, char *);
};

int C::Func(char *, char *, int i) {   // C2511
// try the following line instead
// int C::Func(char *, char *) {
   return 0;
}
```
