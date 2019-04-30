---
title: 컴파일러 오류 C3798
ms.date: 11/04/2016
f1_keywords:
- C3798
helpviewer_keywords:
- C3798
ms.assetid: b2f8b1d8-8812-49b8-a346-28e48f02ba5c
ms.openlocfilehash: a11c88f536e3282e887e32ef437077e61f4424cc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400151"
---
# <a name="compiler-error-c3798"></a>컴파일러 오류 C3798

'specifier': 속성 선언 (get/set 메서드 대신 속성에 배치 해야) 재정의 지정자를 사용할 수 없습니다

속성이 잘못 선언되었습니다. 자세한 내용은 다음 항목을 참조하세요.

- [속성](../../extensions/property-cpp-component-extensions.md)

- [abstract](../../extensions/abstract-cpp-component-extensions.md)

- [sealed](../../extensions/sealed-cpp-component-extensions.md)

## <a name="example"></a>예제

다음 샘플에서는 C3798

```
// C3798.cpp
// compile with: /clr /c
ref struct A {
   property int Prop_1 abstract;   // C3798
   property int Prop_2 sealed;   // C3798

   // OK
   property int Prop_3 {
      virtual int get() abstract;
      virtual void set(int i) abstract;
   }

   property int Prop_4 {
      virtual int get() sealed;
      virtual void set(int i) sealed;
   }
};
```