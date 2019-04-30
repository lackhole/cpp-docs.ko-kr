---
title: 컴파일러 오류 C3114
ms.date: 11/04/2016
f1_keywords:
- C3114
helpviewer_keywords:
- C3114
ms.assetid: b5d2df4f-87d0-4292-9981-25c6a6013c05
ms.openlocfilehash: c5a4feae5c8805a27c020b532fd58e0562e46b6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404119"
---
# <a name="compiler-error-c3114"></a>컴파일러 오류 C3114

'argument': 잘못 명명 된 특성 인수입니다.

명명 된 인수가 유효한 특성 클래스 데이터 멤버의 순서 대로 해당 표시 되 면 안 `static`, `const`, 또는 `literal`합니다. 속성이 아니어야 하는 경우 속성 `static` 해야 get 및 set 접근자입니다.

자세한 내용은 [속성](../../extensions/property-cpp-component-extensions.md) 하 고 [사용자 정의 특성](../../extensions/user-defined-attributes-cpp-component-extensions.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3114 오류가 발생 합니다.

```
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