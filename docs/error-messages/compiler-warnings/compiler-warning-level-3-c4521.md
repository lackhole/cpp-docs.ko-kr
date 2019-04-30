---
title: 컴파일러 경고(수준 3) C4521
ms.date: 11/04/2016
f1_keywords:
- C4521
helpviewer_keywords:
- C4521
ms.assetid: 057d770c-ebcf-44cd-b943-1b1bb1ceaa8c
ms.openlocfilehash: 887526810f7e65280adcde422ef871a67ccdde1f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401919"
---
# <a name="compiler-warning-level-3-c4521"></a>컴파일러 경고(수준 3) C4521

'class': 복사 생성자를 여러 개 지정

클래스에 단일 형식의 여러 복사 생성자입니다. 이 경고는 정보를 제공 합니다. 생성자는 프로그램에서 호출할 수 있습니다.

사용 합니다 [경고](../../preprocessor/warning.md) pragma를이 경고를 표시 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4521 오류가 발생 합니다.

```
// C4521.cpp
// compile with: /EHsc /W3
#include <iostream>

using namespace std;
class A {
public:
   A() { cout << "A's default constructor" << endl; }
   A( A &o ) { cout << "A&" << endl; }
   A( const A &co ) { cout << "const A&" << endl; }   // C4521
};

int main() {
   A o1;         // Calls default constructor.
   A o2( o1 );   // Calls A( A& ).
   const A o3;   // Calls default constructor.
   A o4( o3 );   // Calls A( const A& ).
}
```