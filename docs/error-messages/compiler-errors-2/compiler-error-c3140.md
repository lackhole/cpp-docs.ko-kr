---
title: 컴파일러 오류 C3140
ms.date: 11/04/2016
f1_keywords:
- C3140
helpviewer_keywords:
- C3140
ms.assetid: 122f8943-fac3-4db8-a3a8-2c5d19233de6
ms.openlocfilehash: dc1e1828583b3ac8342c12a62e6ba4c1694b5824
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760571"
---
# <a name="compiler-error-c3140"></a>컴파일러 오류 C3140

같은 컴파일 단위에 여러 개의 ' module ' 특성을 사용할 수 없습니다.

[Module](../../windows/module-cpp.md) 특성은 프로젝트당 한 번만 정의할 수 있습니다.

다음 샘플에서는 C3140를 생성 합니다.

```cpp
// C3140.cpp
// compile with: /c
[emitidl];
[module(name = "MyLibrary")];
[module(name = "MyLibrary2")];   // C3140
```
