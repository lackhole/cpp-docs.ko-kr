---
title: 컴파일러 경고(수준 3) C4522
ms.date: 11/04/2016
f1_keywords:
- C4522
helpviewer_keywords:
- C4522
ms.assetid: 7065dc27-0b6c-4e68-a345-c51cdb99a20b
ms.openlocfilehash: 84f4785c670c4cc5c167c18b9f15c2417b61df34
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/19/2019
ms.locfileid: "74188965"
---
# <a name="compiler-warning-level-3-c4522"></a>컴파일러 경고(수준 3) C4522

' class ': 할당 연산자를 여러 개 지정 했습니다.

클래스에는 단일 형식의 여러 대입 연산자가 있습니다. 이 경고는 정보 제공 용입니다. 프로그램에서 생성자를 호출할 수 있습니다.

이 경고를 표시 하지 않으려면 [warning](../../preprocessor/warning.md) pragma를 사용 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4522를 생성 합니다.

```cpp
// C4522.cpp
// compile with: /EHsc /W3
#include <iostream>

using namespace std;
class A {
public:
   A& operator=( A & o ) { cout << "A&" << endl; return *this; }
   A& operator=( const A &co ) { cout << "const A&" << endl; return *this; }   // C4522
};

int main() {
   A o1, o2;
   o2 = o1;
   const A o3;
   o1 = o3;
}
```