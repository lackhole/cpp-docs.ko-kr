---
title: 컴파일러 오류 C2854
ms.date: 11/04/2016
f1_keywords:
- C2854
helpviewer_keywords:
- C2854
ms.assetid: 917fec9c-790a-4149-8dfc-00d17a09199c
ms.openlocfilehash: a1c30e1fa0f70e5e7bb4b1c97421ca06913fc6f4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62281718"
---
# <a name="compiler-error-c2854"></a>컴파일러 오류 C2854

#pragma hdrstop에 구문 오류가 발생 했습니다.

`#pragma hdrstop` 이름이 잘못 되었습니다. Pragma는 괄호 및 따옴표 선택적 파일 이름이 올 수 있습니다.

다음 샘플에서는 C2854를 생성합니다.

```
// C2854.cpp
// compile with: /c
#pragma hdrstop( "\\source\\pchfiles\\myheader.pch" ]   // C2854
// try the following line instead
// #pragma hdrstop( "\\source\\pchfiles\\myheader.pch" )
```