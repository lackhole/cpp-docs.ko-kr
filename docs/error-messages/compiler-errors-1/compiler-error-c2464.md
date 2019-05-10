---
title: 컴파일러 오류 C2464
ms.date: 11/04/2016
f1_keywords:
- C2464
helpviewer_keywords:
- C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
ms.openlocfilehash: a00ac997f73175eeab08a0132128e48e8fc58feb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338898"
---
# <a name="compiler-error-c2464"></a>컴파일러 오류 C2464

'identifier': 참조를 할당 하는 데 'new' 사용할 수 없습니다

참조 식별자를 사용 하 여 할당 된 `new` 연산자입니다. 참조는 하므로 메모리 개체가 아니므로 `new` 에 대 한 포인터를 반환할 수 없습니다. 표준 변수 선언 구문을 사용 하 여 참조를 선언 합니다.

다음 샘플에서는 C2464를 생성합니다.

```
// C2464.cpp
int main() {
   new ( int& ir );   // C2464
}
```