---
title: 컴파일러 오류 C3898
ms.date: 11/04/2016
f1_keywords:
- C3898
helpviewer_keywords:
- C3898
ms.assetid: d9a90df6-87e4-4fe7-ab01-c226ee86bf10
ms.openlocfilehash: 02c649fb906b0c5f09afe25952a8670c1a0e7f3d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749206"
---
# <a name="compiler-error-c3898"></a>컴파일러 오류 C3898

' var ': 형식 데이터 멤버는 관리 되는 형식의 멤버일 수만 있습니다.

네이티브 클래스에서 [initonly](../../dotnet/initonly-cpp-cli.md) 데이터 멤버가 선언 되었습니다.  `initonly` 데이터 멤버는 CLR 클래스 에서만 선언할 수 있습니다.

다음 샘플에서는 C3898를 생성 합니다.

```cpp
// C3898.cpp
// compile with: /clr
struct Y1 {
   initonly
   static int data_var = 9;   // C3898
};
```

가능한 해결 방법:

```cpp
// C3898b.cpp
// compile with: /clr /c
ref struct Y1 {
   initonly
   static int data_var = 9;
};
```
