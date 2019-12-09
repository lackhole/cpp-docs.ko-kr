---
title: 컴파일러 오류 C2249
ms.date: 11/04/2016
f1_keywords:
- C2249
helpviewer_keywords:
- C2249
ms.assetid: bdd6697c-e04b-49b9-8e40-d9eb6d74f2b6
ms.openlocfilehash: 24db84c9205173f098e493c4ea6393fb96592276
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758894"
---
# <a name="compiler-error-c2249"></a>컴파일러 오류 C2249

' member ': 가상 기본 ' class '에 선언 된 액세스 멤버에 액세스할 수 있는 경로가 없습니다.

`member`는 public이 아닌 `virtual` 기본 클래스 또는 구조체에서 상속 됩니다.

## <a name="example"></a>예제

다음 샘플에서는 C2249를 생성 합니다.

```cpp
// C2249.cpp
class A {
private:
   void privFunc( void ) {};
public:
   void pubFunc( void ) {};
};

class B : virtual public A {} b;

int main() {
   b.privFunc();    // C2249, private member of A
   b.pubFunc();    // OK
}
```

## <a name="example"></a>예제

C2249는 C++ 표준 라이브러리에서 다른 스트림으로 스트림을 할당 하려고 하는 경우에도 발생할 수 있습니다.  다음 샘플에서는 C2249를 생성 합니다.

```cpp
// C2249_2.cpp
#include <iostream>
using namespace std;
int main() {
   cout = cerr;   // C2249
   #define cout cerr;   // OK
}
```
