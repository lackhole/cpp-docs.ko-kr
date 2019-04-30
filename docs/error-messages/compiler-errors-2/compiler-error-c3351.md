---
title: 컴파일러 오류 C3351
ms.date: 11/04/2016
f1_keywords:
- C3351
helpviewer_keywords:
- C3351
ms.assetid: c021bbbe-1067-4f51-af4f-940d2b792eb5
ms.openlocfilehash: 3935acc645403efcd579a80340ebb9794bc1052a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402660"
---
# <a name="compiler-error-c3351"></a>컴파일러 오류 C3351

'object': 대리자 생성자: 두 번째 인수는 정적 멤버 함수 또는 전역 함수의 주소여야 합니다.

컴파일러에서 `static`으로 선언된 함수의 주소가 필요합니다.

다음 샘플에서는 C3351을 생성합니다.

```
// C3351a.cpp
// compile with: /clr
delegate int D(int, int);

ref class C {
public:
   int mf(int, int) {
      return 1;
   }

   static int mf2(int, int) {
      return 1;
   }
};

int main() {
   System::Delegate ^pD = gcnew D(nullptr, &C::mf);   // C3351
   System::Delegate ^pD2 = gcnew D(&C::mf2);
}
```
