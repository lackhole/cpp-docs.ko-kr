---
title: 컴파일러 경고(수준 1) C4230
ms.date: 11/04/2016
f1_keywords:
- C4230
helpviewer_keywords:
- C4230
ms.assetid: a4be8729-74b6-44df-a5ea-e3f45aad0f8f
ms.openlocfilehash: c8d223a286b8d42ca404fbfe7cbc51b67b3dd497
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207489"
---
# <a name="compiler-warning-level-1-c4230"></a>컴파일러 경고(수준 1) C4230

된 구문을 사용 했습니다: 오래; 한정자를 무시

와 같은 Microsoft 한정자 전에 한정자를 사용 하 여 `__cdecl` 쿼리로 됩니다.

## <a name="example"></a>예제

```
// C4230.cpp
// compile with: /W1 /LD
int __cdecl const function1();   // C4230 const ignored
```