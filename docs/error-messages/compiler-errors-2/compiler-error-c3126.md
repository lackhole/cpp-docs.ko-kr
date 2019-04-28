---
title: 컴파일러 오류 C3126
ms.date: 11/04/2016
f1_keywords:
- C3126
helpviewer_keywords:
- C3126
ms.assetid: e72658a3-5d85-4a31-89a4-dbc3d475973d
ms.openlocfilehash: 92f01bd9a04d6350b348d734281855bb86b350d9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300663"
---
# <a name="compiler-error-c3126"></a>컴파일러 오류 C3126

관리 되는 ' type' 내부 ' union' 공용 구조체를 정의할 수 없습니다.

관리 되는 형식 내에서 공용 구조체를 정의할 수 없습니다.

다음 샘플에서는 C3126 오류가 생성 됩니다.

```
// C3126_2.cpp
// compile with: /clr /c
ref class Test
{
   union x
   {   // C3126
      int a;
      int b;
   };
};
```
