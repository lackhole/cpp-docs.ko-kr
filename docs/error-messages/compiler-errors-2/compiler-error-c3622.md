---
title: 컴파일러 오류 C3622
ms.date: 11/04/2016
f1_keywords:
- C3622
helpviewer_keywords:
- C3622
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
ms.openlocfilehash: 2adcee4cb20c39c39b06e0ac2087478cfe2d8937
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740899"
---
# <a name="compiler-error-c3622"></a>컴파일러 오류 C3622

' class ': ' keyword '로 선언 된 클래스를 인스턴스화할 수 없습니다.

[Abstract](../../extensions/abstract-cpp-component-extensions.md)로 표시 된 클래스를 인스턴스화하려고 했습니다. `abstract`로 표시 된 클래스는 기본 클래스가 될 수 있지만 인스턴스화할 수 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3622를 생성 합니다.

```cpp
// C3622.cpp
// compile with: /clr
ref class a abstract {};

int main() {
   a aa;   // C3622
}
```
