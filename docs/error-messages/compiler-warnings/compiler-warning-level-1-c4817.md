---
title: 컴파일러 경고(수준 1) C4817
ms.date: 11/04/2016
f1_keywords:
- C4817
helpviewer_keywords:
- C4817
ms.assetid: a68f5486-6940-4934-9f93-bfd4d71f92a9
ms.openlocfilehash: d729bdbf0f8379b2ffde80567ae4307d0a8dacd7
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052319"
---
# <a name="compiler-warning-level-1-c4817"></a>컴파일러 경고(수준 1) C4817

'member': 이 멤버에 액세스하기 위해 '.'를 사용할 수 없습니다. 컴파일러는 '->'로 바뀝니다.

잘못된 멤버 액세스 연산자가 사용되었습니다.

## <a name="example"></a>예제

다음 샘플에서는 C4817을 생성합니다.

```cpp
// C4817.cpp
// compile with: /clr /W1
using namespace System;
int main() {
   array<Int32> ^ a = gcnew array<Int32>(100);
   Console::WriteLine( a.Length );   // C4817
   Console::WriteLine( a->Length );   // OK
}
```
