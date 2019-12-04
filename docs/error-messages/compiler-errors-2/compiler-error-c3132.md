---
title: 컴파일러 오류 C3132
ms.date: 11/04/2016
f1_keywords:
- C3132
helpviewer_keywords:
- C3132
ms.assetid: d54a3d12-336a-4ed0-ad4e-43cddac33b5e
ms.openlocfilehash: d3ef68e693b77b72c1e4cc2590a404b09b38ab04
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760207"
---
# <a name="compiler-error-c3132"></a>컴파일러 오류 C3132

' function-parameter ': 매개 변수 배열은 ' 단일 차원 관리 되는 배열 ' 형식의 형식 인수에만 적용할 수 있습니다.

단일 차원 배열이 아닌 매개 변수에 <xref:System.ParamArrayAttribute> 특성이 적용 되었습니다.

다음 샘플에서는 C3132를 생성 합니다.

```cpp
// C3132.cpp
// compile with: /clr /c
using namespace System;
void f( [ParamArray] Int32[,] );   // C3132
void g( [ParamArray] Int32[] );   // C3132

void h( [ParamArray] array<Char ^> ^ MyArray );   // OK
```
