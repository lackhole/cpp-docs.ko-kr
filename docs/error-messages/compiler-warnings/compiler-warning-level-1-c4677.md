---
title: 컴파일러 경고 (수준 1) C4677
ms.date: 11/04/2016
f1_keywords:
- C4677
helpviewer_keywords:
- C4677
ms.assetid: a8d656a1-e2ff-4f8b-9028-201765131026
ms.openlocfilehash: 8567e7392537507a25121977448ac47ec079316b
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051378"
---
# <a name="compiler-warning-level-1-c4677"></a>컴파일러 경고 (수준 1) C4677

' function ': 전용이 아닌 멤버의 시그니처에 어셈블리 전용 형식 ' private_type '이 (가) 있습니다.

어셈블리 외부에서 public 액세스 가능성이 있는 형식은 어셈블리 외부에서 private 액세스 권한이 있는 형식을 사용 합니다. Public 어셈블리 형식을 참조 하는 구성 요소는 어셈블리 전용 형식을 참조 하는 멤버 또는 형식 멤버를 사용할 수 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C4677를 생성 합니다.

```cpp
// C4677.cpp
// compile with: /clr /c /W1
delegate void TestDel();
public delegate void TestDel2();

public ref class MyClass {
public:
   static event TestDel^ MyClass_Event;   // C4677
   static event TestDel2^ MyClass_Event2;   // OK
};
```