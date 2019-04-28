---
title: 컴파일러 경고 (수준 2) C4150
ms.date: 11/04/2016
f1_keywords:
- C4150
helpviewer_keywords:
- C4150
ms.assetid: ff1760ec-0d9f-4d45-b797-94261624becf
ms.openlocfilehash: 4c5c10ee0ea3242e52e6db5391694c9ddf941a78
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349778"
---
# <a name="compiler-warning-level-2-c4150"></a>컴파일러 경고 (수준 2) C4150

불완전 한 형식 'type';에 대 한 포인터 삭제 소멸자가 호출 되지 않은

합니다 **삭제** 컴파일러가 소멸자를 찾을 수 없습니다 있도록 선언 되었지만 정의 되지 않은 형식을 삭제 하려면 연산자를 호출 합니다.

다음 샘플에서는 C4150 오류가 생성 됩니다.

```
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