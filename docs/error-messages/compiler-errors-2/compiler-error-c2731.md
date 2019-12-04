---
title: 컴파일러 오류 C2731
ms.date: 11/04/2016
f1_keywords:
- C2731
helpviewer_keywords:
- C2731
ms.assetid: 9b563999-febd-4582-9147-f355083c091e
ms.openlocfilehash: 4b73ee4ad205bfc2203423b5f413011ce090852f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755813"
---
# <a name="compiler-error-c2731"></a>컴파일러 오류 C2731

' identifier ': 함수를 오버 로드할 수 없습니다.

`main`, `WinMain`, `DllMain`및 `LibMain` 함수를 오버 로드할 수 없습니다.

다음 샘플에서는 C2731를 생성 합니다.

```cpp
// C2731.cpp
extern "C" void WinMain(int, char *, char *);
void WinMain(int, short, char *, char*);   // C2731
```
