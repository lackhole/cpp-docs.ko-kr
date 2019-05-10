---
title: 컴파일러 오류 C3290
ms.date: 11/04/2016
f1_keywords:
- C3290
helpviewer_keywords:
- C3290
ms.assetid: 0baf684b-1143-4953-ac99-a2fa267d8017
ms.openlocfilehash: f2a346354d8da7d78c5517b01b4438bfb8af50ad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222709"
---
# <a name="compiler-error-c3290"></a>컴파일러 오류 C3290

'type': trivial 속성은 참조 형식일 수 없습니다.

속성이 잘못 선언되었습니다. trivial 속성을 선언하면 컴파일러가 속성에서 업데이트할 변수를 만들며, 클래스에 추적 참조 변수를 사용할 수 없습니다.

참조 [속성](../../extensions/property-cpp-component-extensions.md) 하 고 [추적 참조 연산자](../../extensions/tracking-reference-operator-cpp-component-extensions.md) 자세한 내용은 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3290을 생성합니다.

```
// C3290.cpp
// compile with: /clr /c
ref struct R {};

ref struct X {
   R^ mr;

   property R % y;   // C3290
   property R ^ x;   // OK

   // OK
   property R% prop {
      R% get() {
         return *mr;
      }

      void set(R%) {}
   }
};

int main() {
   X x;
   R% xp = x.prop;
}
```