---
title: 컴파일러 오류 C3364
ms.date: 11/04/2016
f1_keywords:
- C3364
helpviewer_keywords:
- C3364
ms.assetid: 98654741-60fe-4472-a6af-e580f8c0a6e1
ms.openlocfilehash: e99ab3919edcfb883701c08c52cd7aad60cd4591
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400359"
---
# <a name="compiler-error-c3364"></a>컴파일러 오류 C3364

'delegate': 대리 생성자: 인수 관리 되는 클래스의 멤버 함수 또는 전역 함수에 대 한 포인터 여야 합니다.

대리 생성자의 두 번째 매개 변수는 멤버 함수의 주소 또는 클래스의 정적 멤버 함수의 주소를 사용 합니다. 둘 다 간단한 주소로 취급 됩니다.

다음 샘플에서는 C3364 오류가 생성 됩니다.

```
// C3364_2.cpp
// compile with: /clr

delegate int D( int, int );

ref class C {
public:
   int mf( int, int ) {
      return 1;
   }
};

int main() {
   C^ pC = gcnew C;
   System::Delegate^ pD = gcnew D( pC,pC->mf( 1, 2 ) ); // C3364

   // try the following line instead
   // System::Delegate^ pD = gcnew D(pC, &C::mf);
}
```
