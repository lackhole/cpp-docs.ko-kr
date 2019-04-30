---
title: 컴파일러 오류 C2662
ms.date: 11/04/2016
f1_keywords:
- C2662
helpviewer_keywords:
- C2662
ms.assetid: e172c2a4-f29e-4034-8232-e7dc6f83689f
ms.openlocfilehash: fefd523ca3b9a3406afc307150322f9d431aa730
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360351"
---
# <a name="compiler-error-c2662"></a>컴파일러 오류 C2662

'function': 'type1'에서 'type2'에 'this'이 포인터를 변환할 수 없습니다

컴파일러 변환할 수 없습니다는 `this` 대 한 포인터 `type1` 를 `type2`합니다.

비-를 호출 하 여이 오류를 발생할 수 있습니다`const` 에 대해 멤버 함수는 `const` 개체입니다.  가능한 해결 방법:

- 제거 된 `const` 개체 선언에서.

- 추가 `const` 멤버 함수입니다.

다음 샘플에서는 C2662 오류가 생성 됩니다.

```
// C2662.cpp
class C {
public:
   void func1();
   void func2() const{}
} const c;

int main() {
   c.func1();   // C2662
   c.func2();   // OK
}
```

사용 하 여 컴파일하면 **/clr**에서 함수를 호출할 수 없습니다는 `const` 또는 `volatile` 관리 되는 형식의 정규화 된 합니다. Const 관리 되는 개체에서 메서드를 호출할 수 없습니다 관리 되는 클래스의 const 멤버 함수를 선언할 수 없습니다.

```
// C2662_b.cpp
// compile with: /c /clr
ref struct M {
   property M^ Type {
      M^ get() { return this; }
   }

   void operator=(const M %m) {
      M ^ prop = m.Type;   // C2662
   }
};

ref struct N {
   property N^ Type {
      N^ get() { return this; }
   }

   void operator=(N % n) {
      N ^ prop = n.Type;   // OK
   }
};
```

다음 샘플에서는 C2662 오류가 생성 됩니다.

```
// C2662_c.cpp
// compile with: /c
// C2662 expected
typedef int ISXVD;
typedef unsigned char BYTE;

class LXBASE {
protected:
    BYTE *m_rgb;
};

class LXISXVD:LXBASE {
public:
   // Delete the following line to resolve.
   ISXVD *PMin() { return (ISXVD *)m_rgb; }

   ISXVD *PMin2() const { return (ISXVD *)m_rgb; };   // OK
};

void F(const LXISXVD *plxisxvd, int iDim) {
   ISXVD isxvd;
   // Delete the following line to resolve.
   isxvd = plxisxvd->PMin()[iDim];

   isxvd = plxisxvd->PMin2()[iDim];
}
```