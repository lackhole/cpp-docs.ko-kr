---
title: 컴파일러 경고(수준 4) C4516
ms.date: 11/04/2016
f1_keywords:
- C4516
helpviewer_keywords:
- C4516
ms.assetid: 6677bb1f-d26e-4ab9-8644-6b5a2a8f4ff8
ms.openlocfilehash: 8020103e8e20bf1a5e955cbfdfafc6a328b439e6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62221035"
---
# <a name="compiler-warning-level-4-c4516"></a>컴파일러 경고(수준 4) C4516

'class::symbol': 액세스 선언은 사용 되지 않습니다. 더 나은 대안을 제공 하는 멤버를 사용 하 여 선언

ANSI C++ 위원회에 대 한 액세스 선언이 했습니다 (변경 하지 않고 파생된 클래스에서 멤버의 액세스를 [사용 하 여](../../cpp/using-declaration.md) 키워드) 오래 된 되도록 합니다. 액세스 선언이의 이후 버전에서 지원 되지 않을 수 있습니다 C++입니다.

다음 샘플에서는 C4516 오류가 생성 됩니다.

```
// C4516.cpp
// compile with: /W4
class A
{
public:
   void x(char);
};

class B : protected A
{
public:
   A::x;  // C4516 on access-declaration
   // use the following line instead
   // using A::x; // using-declaration, ok
};

int main()
{
}
```