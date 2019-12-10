---
title: 컴파일러 오류 C3114
ms.date: 11/04/2016
f1_keywords:
- C3114
helpviewer_keywords:
- C3114
ms.assetid: b5d2df4f-87d0-4292-9981-25c6a6013c05
ms.openlocfilehash: 6f548c72a0e95c533ed711fe9f2583a7abd6c500
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760763"
---
# <a name="compiler-error-c3114"></a>컴파일러 오류 C3114

' argument ': 명명 된 특성 인수가 잘못 되었습니다.

특성 클래스 데이터 멤버가 유효한 명명 된 인수가 되도록 하려면 `static`, `const`또는 `literal`으로 표시 되지 않아야 합니다. 속성이 인 경우 속성은 `static` 수 없으며 get 및 set 접근자가 있어야 합니다.

자세한 내용은 [속성](../../extensions/property-cpp-component-extensions.md) 및 [사용자 정의 특성](../../extensions/user-defined-attributes-cpp-component-extensions.md)을 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3114를 생성 합니다.

```cpp
// C3114.cpp
// compile with: /clr /c
public ref class A : System::Attribute {
public:
   static property int StaticProp {
      int get();
   }

   property int Prop2 {
      int get();
      void set(int i);
   }
};

[A(StaticProp=123)]   // C3114
public ref class R {};

[A(Prop2=123)]   // OK
public ref class S {};
```
