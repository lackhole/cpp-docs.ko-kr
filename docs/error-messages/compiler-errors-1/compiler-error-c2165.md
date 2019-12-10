---
title: 컴파일러 오류 C2165
ms.date: 11/04/2016
f1_keywords:
- C2165
helpviewer_keywords:
- C2165
ms.assetid: b108313b-b8cb-4dce-b2ec-f2b31c9cdc87
ms.openlocfilehash: 3bfaa07fa4524e5883b2744d5686e90fc9683016
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755683"
---
# <a name="compiler-error-c2165"></a>컴파일러 오류 C2165

'keyword': 데이터에 대한 포인터를 수정할 수 없습니다.

`__stdcall`, `__cdecl`또는 `__fastcall` 키워드가 데이터에 대한 포인터를 수정하려고 시도합니다.

다음 샘플에서는 C2165를 생성합니다.

```cpp
// C2165.cpp
// compile with: /c
char __cdecl *p;   // C2165
char *p;   // OK
```
