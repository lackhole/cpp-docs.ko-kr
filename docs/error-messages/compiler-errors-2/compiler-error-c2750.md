---
title: 컴파일러 오류 C2750
ms.date: 11/04/2016
f1_keywords:
- C2750
helpviewer_keywords:
- C2750
ms.assetid: 30450034-feb5-448c-9655-b8c5f3639695
ms.openlocfilehash: 34d19e8e9f51c90c48ec0d429f98bb82e3d829d4
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59777200"
---
# <a name="compiler-error-c2750"></a>컴파일러 오류 C2750

'type': 참조 형식에 'new' 사용할 수 없습니다 'gcnew'를 대신 사용

그러면 인스턴스가 가비지 수집 힙에 배치 될 CLR 형식의 인스턴스를 만드는 사용 해야 합니다 [gcnew](../../extensions/ref-new-gcnew-cpp-component-extensions.md)합니다.

다음 샘플에서는 C2750를 생성합니다.

```
// C2750.cpp
// compile with: /clr
ref struct Y1 {};

int main() {
   Y1 ^ x = new Y1;   // C2750

   // try the following line instead
   Y1 ^ x2 = gcnew Y1;
}
```