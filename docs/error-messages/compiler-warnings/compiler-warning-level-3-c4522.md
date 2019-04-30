---
title: 컴파일러 경고(수준 3) C4522
ms.date: 11/04/2016
f1_keywords:
- C4522
helpviewer_keywords:
- C4522
ms.assetid: 7065dc27-0b6c-4e68-a345-c51cdb99a20b
ms.openlocfilehash: de163f0a3925b711f2f3437b700f75bbe994b3e7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401906"
---
# <a name="compiler-warning-level-3-c4522"></a>컴파일러 경고(수준 3) C4522

'class': 할당 연산자가 여러 개 지정

클래스에는 단일 형식의 여러 할당 연산자가 있습니다. 이 경고는 정보를 제공 합니다. 생성자는 프로그램에서 호출할 수 있습니다.

사용 합니다 [경고](../../preprocessor/warning.md) pragma를이 경고를 표시 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4522 오류가 발생 합니다.

```
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