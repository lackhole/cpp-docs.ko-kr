---
title: 컴파일러 오류 C3755
ms.date: 11/04/2016
f1_keywords:
- C3755
helpviewer_keywords:
- C3755
ms.assetid: 9317b55e-a52e-4b87-b915-5a208d6eda38
ms.openlocfilehash: 0150693ae84b45dc62c11cfdc59369eb25a819cd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757282"
---
# <a name="compiler-error-c3755"></a>컴파일러 오류 C3755

' delegate ': 대리자를 정의할 수 없습니다.

[대리자 (C++ 구성 요소 확장)](../../extensions/delegate-cpp-component-extensions.md) 를 선언할 수는 있지만 정의할 수는 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3755를 생성 합니다.

```cpp
// C3755.cpp
// compile with: /clr /c
delegate void MyDel() {};   // C3755
```

## <a name="example"></a>예제

C3755는 대리자 템플릿을 만들려고 할 때에도 발생할 수 있습니다. 다음 샘플에서는 C3755를 생성 합니다.

```cpp
// C3755_b.cpp
// compile with: /clr /c
ref struct R {
   template<class T>
   delegate void D(int) {}   // C3755
};
```
