---
title: 컴파일러 경고(수준 3) C4823
ms.date: 11/04/2016
f1_keywords:
- C4823
helpviewer_keywords:
- C4823
ms.assetid: 8a77560d-dcea-4cae-aebb-8ebf1b4cef85
ms.openlocfilehash: 28d490c341c4d14c2e6c03e13007b5a8be423622
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401542"
---
# <a name="compiler-warning-level-3-c4823"></a>컴파일러 경고(수준 3) C4823

'function': 사용 고정 포인터 하지만 해제 의미 체계를 사용할 수 없습니다. /EHa를 사용 하는 것이 좋습니다.

블록 범위에서 선언 하는 고정 포인터에 의해 관리 되는 힙에 있는 개체를 고정 해제, 컴파일러는 고정 포인터에 대 한 포인터를 무효화 하는 소멸자가 "가장" 로컬 클래스의 소멸자의 동작을 시뮬레이션 합니다. 예외를 throw 한 후 소멸자에 대 한 호출을 사용 하려면 기능을 활성화 해야 개체 해제를 사용 하 여 수행할 수 있습니다 [/EHsc](../../build/reference/eh-exception-handling-model.md)합니다.

수동으로 개체를 고정 해제 하 고 경고를 무시할 수 있습니다.

## <a name="example"></a>예제

다음 샘플 C4823를 생성합니다.

```
// C4823.cpp
// compile with: /clr /W3 /EHa-
using namespace System;

ref struct G {
   int m;
};

void f(G ^ pG) {
   try {
      pin_ptr<int> p = &pG->m;
      // manually unpin, ignore warning
      // p = nullptr;
      throw gcnew Exception;
   }
   catch(Exception ^) {}
}   // C4823 warning

int main() {
   f( gcnew G );
}
```
