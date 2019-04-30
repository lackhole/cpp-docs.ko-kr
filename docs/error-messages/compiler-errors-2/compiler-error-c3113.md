---
title: 컴파일러 오류 C3113
ms.date: 11/04/2016
f1_keywords:
- C3113
helpviewer_keywords:
- C3113
ms.assetid: 3afdc668-b29e-474e-9ea3-aa027d42db7c
ms.openlocfilehash: b8edd31db87587887d9e96522802ee9091caab91
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404132"
---
# <a name="compiler-error-c3113"></a>컴파일러 오류 C3113

'structure' 템플릿/제네릭 여야 합니다.

클래스 템플릿 또는 클래스에서 인터페이스 또는 enum 제네릭 확인 하려고 했습니다.

다음 샘플에서는 C3113를 생성합니다.

```
// C3113.cpp
// compile with: /c
template <class T>
enum E {};   // C3113
// try the following line instead
// class MyClass{};
```