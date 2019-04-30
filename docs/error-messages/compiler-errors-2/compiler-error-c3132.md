---
title: 컴파일러 오류 C3132
ms.date: 11/04/2016
f1_keywords:
- C3132
helpviewer_keywords:
- C3132
ms.assetid: d54a3d12-336a-4ed0-ad4e-43cddac33b5e
ms.openlocfilehash: 1a97e04747cb92909380e66d1f4ea8ca62183054
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349882"
---
# <a name="compiler-error-c3132"></a>컴파일러 오류 C3132

' 함수 매개 변수 ': '관리 되는 1 차원 배열' 형식의 형식 인수에 매개 변수 배열만 적용할 수

<xref:System.ParamArrayAttribute> 없는 1 차원 배열 매개 변수에 특성이 적용 되었습니다.

다음 샘플에서는 C3132 오류가 생성 됩니다.

```
// C3132.cpp
// compile with: /clr /c
using namespace System;
void f( [ParamArray] Int32[,] );   // C3132
void g( [ParamArray] Int32[] );   // C3132

void h( [ParamArray] array<Char ^> ^ MyArray );   // OK
```