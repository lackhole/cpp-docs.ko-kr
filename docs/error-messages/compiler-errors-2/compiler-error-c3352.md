---
title: 컴파일러 오류 C3352
ms.date: 11/04/2016
f1_keywords:
- C3352
helpviewer_keywords:
- C3352
ms.assetid: f233bed7-474e-425f-aad2-7801578169d4
ms.openlocfilehash: b679a89bb768ad7a50d0bbaa7b814c7a72f9f4c5
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740431"
---
# <a name="compiler-error-c3352"></a>컴파일러 오류 C3352

' function ': 지정한 함수가 ' type ' 대리자 형식과 일치 하지 않습니다.

`function`에 대 한 매개 변수 목록이 며 대리자가 일치 하지 않습니다.

자세한 내용은 [delegate (C++ 구성 요소 확장)](../../extensions/delegate-cpp-component-extensions.md)를 참조 하세요.

다음 샘플에서는 C3352를 생성 합니다.

```cpp
// C3352.cpp
// compile with: /clr
delegate int D( int, int );
ref class C {
public:
   int mf( int ) {
      return 1;
   }

   // Uncomment the following line to resolve.
   // int mf(int, int) { return 1; }
};

int main() {
   C^ pC = gcnew C;
   System::Delegate^ pD = gcnew D( pC, &C::mf );   // C3352
}
```
