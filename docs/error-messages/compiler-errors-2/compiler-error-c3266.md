---
title: 컴파일러 오류 C3266
ms.date: 11/04/2016
f1_keywords:
- C3266
helpviewer_keywords:
- C3266
ms.assetid: 7375c099-acb7-42f6-898d-57cfefa010b8
ms.openlocfilehash: 9122663108cafc8c73564379892e96978a90b26d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754175"
---
# <a name="compiler-error-c3266"></a>컴파일러 오류 C3266

'class': 클래스-생성자에는 'void' 매개 변수 목록이 있어야 합니다.

/clr 프로그래밍을 사용하는 클래스의 클래스-생성자는 매개 변수를 사용할 수 없습니다.

다음 샘플에서는 C3266을 생성합니다.

```cpp
// C3266.cpp
// compile with: /clr

ref class X {
   static X(int i) { // C3266
   // try the following line instead
   // static X() {
   }
};

int main() {
}
```
