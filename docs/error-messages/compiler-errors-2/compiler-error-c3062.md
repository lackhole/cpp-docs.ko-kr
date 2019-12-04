---
title: 컴파일러 오류 C3062
ms.date: 11/04/2016
f1_keywords:
- C3062
helpviewer_keywords:
- C3062
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
ms.openlocfilehash: 9b1fbc8f4ca2ce3434a30e833f4741bc17015bbb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749531"
---
# <a name="compiler-error-c3062"></a>컴파일러 오류 C3062

' enum ': 내부 형식이 ' t r u e ' 이므로 열거자에 값이 필요 합니다.

열거형의 기본 형식을 지정할 수 있습니다. 그러나 일부 형식에서는 각 열거자에 값을 할당 해야 합니다.

열거형에 대 한 자세한 내용은 [enum 클래스](../../extensions/enum-class-cpp-component-extensions.md)를 참조 하세요.

다음 샘플에서는 C3062를 생성 합니다.

```cpp
// C3062.cpp
// compile with: /clr

enum class MyEnum : bool { a };   // C3062
enum class MyEnum2 : bool { a = true};   // OK
```
