---
title: 컴파일러 오류 C3350
ms.date: 11/04/2016
f1_keywords:
- C3350
helpviewer_keywords:
- C3350
ms.assetid: cfbbc338-92b5-4f34-999e-aa2d2376bc70
ms.openlocfilehash: a19dbde6409afaae29e9110315c7c68fe9d43d62
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300546"
---
# <a name="compiler-error-c3350"></a>컴파일러 오류 C3350

'delegate': 대리 생성자에 인수가 number개 있어야 합니다.

대리자 인스턴스를 만드는 경우 인수 두 개, 대리자 함수를 포함하는 형식 인스턴스 및 함수를 전달해야 합니다.

다음 샘플에서는 C3350을 생성합니다.

```
// C3350.cpp
// compile with: /clr
delegate void SumDelegate();

public ref class X {
public:
   void F() {}
   static void F2() {}
};

int main() {
   X ^ MyX = gcnew X();
   SumDelegate ^ pSD = gcnew SumDelegate();   // C3350
   SumDelegate ^ pSD1 = gcnew SumDelegate(MyX, &X::F);
   SumDelegate ^ pSD2 = gcnew SumDelegate(&X::F2);
}
```
