---
title: 컴파일러 경고(수준 1) C4677
ms.date: 11/04/2016
f1_keywords:
- C4677
helpviewer_keywords:
- C4677
ms.assetid: a8d656a1-e2ff-4f8b-9028-201765131026
ms.openlocfilehash: 66b8d42b63bcbf328703523c4eeda7a047f4643c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374575"
---
# <a name="compiler-warning-level-1-c4677"></a>컴파일러 경고(수준 1) C4677

'function': 전용이 아닌 멤버의 시그니처에 어셈블리 전용 형식 'private_type'

어셈블리 외부에서 개인 액세스 권한이 있는 형식을 사용 하는 어셈블리 외부에 public 액세스 가능성을 가지는 형식입니다. 공용 어셈블리 유형을 참조 하는 구성 요소 어셈블리 전용 형식 참조 하는 멤버 또는 형식 멤버를 사용할 수 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C4677 오류가 발생 합니다.

```
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