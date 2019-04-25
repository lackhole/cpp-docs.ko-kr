---
title: 컴파일러 오류 C3179
ms.date: 11/04/2016
f1_keywords:
- C3179
helpviewer_keywords:
- C3179
ms.assetid: 60d7e41b-25fd-48ac-8b79-830c062f4dcd
ms.openlocfilehash: a5c92e8a776e318e732448ba31beedef946d9f41
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174070"
---
# <a name="compiler-error-c3179"></a>컴파일러 오류 C3179

명명되지 않은 관리되는 형식 또는 WinRT 형식을 사용할 수 없습니다.

모든 CLR 및 WinRT 클래스와 구조체에는 이름이 있어야 합니다.

다음 샘플에서는 C3179 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```
// C3179a.cpp
// compile with: /clr /c
typedef value struct { // C3179
// try the following line instead
// typedef value struct MyStruct {
   int i;
} V;
```
