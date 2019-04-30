---
title: 컴파일러 오류 C2246
ms.date: 11/04/2016
f1_keywords:
- C2246
helpviewer_keywords:
- C2246
ms.assetid: 4f3e4f83-21f3-4256-af96-43e0bb060311
ms.openlocfilehash: c8efb71e0a39c56628fc582421e0f24ceb9b290c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302607"
---
# <a name="compiler-error-c2246"></a>컴파일러 오류 C2246

'identifier': 지역으로 정의된 클래스에 잘못된 정적 데이터 멤버가 있습니다.

로컬 범위를 가진 클래스, 구조체 또는 공용 구조체의 멤버가 `static`으로 선언되었습니다.

다음 샘플에서는 C2246을 생성합니다.

```
// C2246.cpp
// compile with: /c
void func( void ) {
   class A { static int i; };   // C2246  i is local to func
   static int j;   // OK
};
```