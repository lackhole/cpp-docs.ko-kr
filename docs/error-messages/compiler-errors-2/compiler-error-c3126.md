---
title: 컴파일러 오류 C3126
ms.date: 11/04/2016
f1_keywords:
- C3126
helpviewer_keywords:
- C3126
ms.assetid: e72658a3-5d85-4a31-89a4-dbc3d475973d
ms.openlocfilehash: 2b8901ce9914f35d4cd219f4d51477582fa676a8
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760727"
---
# <a name="compiler-error-c3126"></a>컴파일러 오류 C3126

' type ' 관리 되는 형식 내에서 ' union ' 공용 구조체를 정의할 수 없습니다.

공용 구조체는 관리 되는 형식 내에서 정의할 수 없습니다.

다음 샘플에서는 C3126를 생성 합니다.

```cpp
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
