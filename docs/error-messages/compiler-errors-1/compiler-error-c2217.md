---
title: 컴파일러 오류 C2217
ms.date: 11/04/2016
f1_keywords:
- C2217
helpviewer_keywords:
- C2217
ms.assetid: 1ce1e3f5-4171-4376-804d-967f7e612935
ms.openlocfilehash: 7417c651fde6bef781bb6eb2e081cd3ad8ecc3a0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74741302"
---
# <a name="compiler-error-c2217"></a>컴파일러 오류 C2217

' attribute1 '에는 ' attribute2 '가 필요 합니다.

첫 번째 함수 특성에는 두 번째 특성이 필요 합니다.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면

1. 인터럽트 (`__interrupt`) 함수를 `near`으로 선언 했습니다. 인터럽트 함수를 `far`해야 합니다.

1. `__stdcall`또는 `__fastcall`으로 선언 된 인터럽트 함수입니다. 인터럽트 함수는 C 호출 규칙을 사용 해야 합니다.

## <a name="example"></a>예제

C2217는 다양 한 수의 인수를 사용 하는 CLR 함수에 대리자를 바인딩하려는 경우에도 발생할 수 있습니다. 함수에 e 매개 변수 배열 오버 로드도 있으면이를 대신 사용 합니다. 다음 샘플에서는 C2217를 생성 합니다.

```cpp
// C2217.cpp
// compile with: /clr
using namespace System;
delegate void MyDel(String^, Object^, Object^, ...);   // C2217
delegate void MyDel2(String ^, array<Object ^> ^);   // OK

int main() {
   MyDel2^ wl = gcnew MyDel2(Console::WriteLine);
   array<Object ^ > ^ x = gcnew array<Object ^>(2);
   x[0] = safe_cast<Object^>(0);
   x[1] = safe_cast<Object^>(1);

   // wl("{0}, {1}", 0, 1);
   wl("{0}, {1}", x);
}
```
