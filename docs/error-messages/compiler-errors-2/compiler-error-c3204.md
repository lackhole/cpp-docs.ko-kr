---
title: 컴파일러 오류 C3204
ms.date: 11/04/2016
f1_keywords:
- C3204
helpviewer_keywords:
- C3204
ms.assetid: 06e578da-0262-48c8-b2ae-be1cd6d28884
ms.openlocfilehash: 72b9f4fe926b617d7c5b3538fb9d3281e1d95a5f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738702"
---
# <a name="compiler-error-c3204"></a>컴파일러 오류 C3204

'_alloca'는 catch 블록 내부에서 호출할 수 없습니다.

이 오류는 catch 블록 내에서 [_alloca](../../c-runtime-library/reference/alloca.md) 호출을 사용하는 경우에 발생합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3204를 생성합니다.

```cpp
// C3204.cpp
// compile with: /EHsc
#include <malloc.h>

void ShowError(void)
{
   try
   {
   }
   catch(...)
   {
      _alloca(1);   // C3204
   }
}
```
