---
title: 컴파일러 오류 C2854
ms.date: 11/04/2016
f1_keywords:
- C2854
helpviewer_keywords:
- C2854
ms.assetid: 917fec9c-790a-4149-8dfc-00d17a09199c
ms.openlocfilehash: 70b763afa4d511823a62d4d3770fc030ab9fb2ec
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745891"
---
# <a name="compiler-error-c2854"></a>컴파일러 오류 C2854

#pragma hdrstop에서 구문 오류가 발생 했습니다.

`#pragma hdrstop`에서 잘못 된 파일 이름을 제공 합니다. Pragma는 괄호와 따옴표의 선택적인 파일 이름 뒤에 올 수 있습니다.

다음 샘플에서는 C2854를 생성 합니다.

```cpp
// C2854.cpp
// compile with: /c
#pragma hdrstop( "\\source\\pchfiles\\myheader.pch" ]   // C2854
// try the following line instead
// #pragma hdrstop( "\\source\\pchfiles\\myheader.pch" )
```
