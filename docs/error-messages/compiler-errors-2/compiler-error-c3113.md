---
title: 컴파일러 오류 C3113
ms.date: 11/04/2016
f1_keywords:
- C3113
helpviewer_keywords:
- C3113
ms.assetid: 3afdc668-b29e-474e-9ea3-aa027d42db7c
ms.openlocfilehash: 067e8b14a0123691ee6368dccaa3ca3f5c763413
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760789"
---
# <a name="compiler-error-c3113"></a>컴파일러 오류 C3113

' structure '는 template/generic 일 수 없습니다.

클래스 템플릿 또는 클래스를 인터페이스 또는 열거형에서 제네릭으로 만들려고 했습니다.

다음 샘플에서는 C3113를 생성 합니다.

```cpp
// C3113.cpp
// compile with: /c
template <class T>
enum E {};   // C3113
// try the following line instead
// class MyClass{};
```
