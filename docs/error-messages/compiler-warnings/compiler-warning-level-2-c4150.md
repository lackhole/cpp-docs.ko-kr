---
title: 컴파일러 경고 (수준 2) C4150
ms.date: 11/04/2016
f1_keywords:
- C4150
helpviewer_keywords:
- C4150
ms.assetid: ff1760ec-0d9f-4d45-b797-94261624becf
ms.openlocfilehash: 5f55347dbe7843e67a3c6ef0ab83b91c8fa9d283
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052151"
---
# <a name="compiler-warning-level-2-c4150"></a>컴파일러 경고 (수준 2) C4150

불완전 한 ' type ' 형식에 대 한 포인터를 삭제 합니다. 소멸자를 호출 하지 않았습니다.

**Delete** 연산자는 선언 되었지만 정의 되지 않은 형식을 삭제 하기 위해 호출 되므로 컴파일러가 소멸자를 찾을 수 없습니다.

다음 샘플에서는 C4150를 생성 합니다.

```cpp
// C4150.cpp
// compile with: /W2
class  IncClass;

void NoDestruct( IncClass* pIncClass )
{
   delete pIncClass;
} // C4150, define class to resolve

int main()
{
}
```