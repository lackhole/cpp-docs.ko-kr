---
title: 컴파일러 오류 C3753
ms.date: 11/04/2016
f1_keywords:
- C3753
helpviewer_keywords:
- C3753
ms.assetid: a5b99e28-796c-4107-a673-97c2ae3bb2b9
ms.openlocfilehash: 2970c4851d3e5cbbe9952c12a71c913c5e3ac656
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755332"
---
# <a name="compiler-error-c3753"></a>컴파일러 오류 C3753

제네릭 속성은 사용할 수 없습니다.

제네릭 매개 변수 목록은 관리 되는 클래스, 구조체 또는 함수에만 나타날 수 있습니다.

자세한 내용은 [제네릭](../../extensions/generics-cpp-component-extensions.md) 및 [속성](../../extensions/property-cpp-component-extensions.md)을 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3753를 생성 합니다.

```cpp
// C3753.cpp
// compile with: /clr /c
ref struct A {
   generic <typename T>
   property int i;   // C3753 error
};
```
