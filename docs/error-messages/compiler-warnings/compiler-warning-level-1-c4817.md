---
title: 컴파일러 경고(수준 1) C4817
ms.date: 11/04/2016
f1_keywords:
- C4817
helpviewer_keywords:
- C4817
ms.assetid: a68f5486-6940-4934-9f93-bfd4d71f92a9
ms.openlocfilehash: bb6eb8899efdab3cae39f77079f7eed72344acc1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406420"
---
# <a name="compiler-warning-level-1-c4817"></a>컴파일러 경고(수준 1) C4817

'member': 이 멤버에 액세스하기 위해 '.'를 사용할 수 없습니다. 컴파일러는 '->'로 바뀝니다.

잘못된 멤버 액세스 연산자가 사용되었습니다.

## <a name="example"></a>예제

다음 샘플에서는 C4817을 생성합니다.

```
// C4817.cpp
// compile with: /clr /W1
using namespace System;
int main() {
   array<Int32> ^ a = gcnew array<Int32>(100);
   Console::WriteLine( a.Length );   // C4817
   Console::WriteLine( a->Length );   // OK
}
```
