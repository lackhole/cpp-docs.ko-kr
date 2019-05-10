---
title: 컴파일러 오류 C2217
ms.date: 11/04/2016
f1_keywords:
- C2217
helpviewer_keywords:
- C2217
ms.assetid: 1ce1e3f5-4171-4376-804d-967f7e612935
ms.openlocfilehash: f178f969afa189910c9d23d70226ecc6c15876a4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353542"
---
# <a name="compiler-error-c2217"></a>컴파일러 오류 C2217

'attribute1' 'attribute2' 필요

첫 번째 함수 특성에는 두 번째 특성에 필요합니다.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면

1. 중단 (`__interrupt`)로 선언 된 함수 `near`합니다. 인터럽트 함수 여야 `far`합니다.

1. 으로 선언 된 함수를 중단할 `__stdcall`, 또는 `__fastcall`합니다. 함수를 중단 해야 사용 C 호출 규칙입니다.

## <a name="example"></a>예제

C2217 가변 개수의 인수를 사용 하는 CLR 함수에 대리자를 바인딩할 경우에 발생할 수 있습니다. 함수에는 또한 e 매개 변수 배열 오버 로드에, 하는 대신 사용 합니다. 다음 샘플 C2217를 생성합니다.

```
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