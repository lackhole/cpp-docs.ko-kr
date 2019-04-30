---
title: 컴파일러 오류 C3140
ms.date: 11/04/2016
f1_keywords:
- C3140
helpviewer_keywords:
- C3140
ms.assetid: 122f8943-fac3-4db8-a3a8-2c5d19233de6
ms.openlocfilehash: e7dde3eb27c018502225ea3bc45e4bee7c699379
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374965"
---
# <a name="compiler-error-c3140"></a>컴파일러 오류 C3140

같은 컴파일 단위에 여러 개의 'module' 특성을 가질 수 없습니다.

합니다 [모듈](../../windows/module-cpp.md) 특성만 정의 될 수 한 번 프로젝트별으로 합니다.

다음 샘플에서는 C3140 오류가 생성 됩니다.

```
// C3140.cpp
// compile with: /c
[emitidl];
[module(name = "MyLibrary")];
[module(name = "MyLibrary2")];   // C3140
```