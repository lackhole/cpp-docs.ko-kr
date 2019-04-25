---
title: 컴파일러 오류 C3414
ms.date: 11/04/2016
f1_keywords:
- C3414
helpviewer_keywords:
- C3414
ms.assetid: 715f5432-b509-4f8f-84f5-e1463bac490f
ms.openlocfilehash: 86ed40f31ae17724700e9d2c68950027d0eefb69
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173410"
---
# <a name="compiler-error-c3414"></a>컴파일러 오류 C3414

'member': 가져온된 멤버 함수를 정의할 수 없습니다

멤버는 참조 된 어셈블리에 정의 된 코드에 정의 되었습니다.

다음 샘플에서는 C3414를 생성합니다.

```
// C3414a2.cpp
// compile with: /clr /LD
public ref class MyClass {
public:
   void Test(){}
};
```

그리고

```
// C3414b2.cpp
// compile with: /clr
#using <C3414a2.dll>

void MyClass::Test() {    // C3414
}

System::Object::Object() {    // C3414
}
```
