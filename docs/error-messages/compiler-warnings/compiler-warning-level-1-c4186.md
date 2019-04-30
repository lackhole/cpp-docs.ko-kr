---
title: 컴파일러 경고(수준 1) C4186
ms.date: 11/04/2016
f1_keywords:
- C4186
helpviewer_keywords:
- C4186
ms.assetid: caf3f7d8-f305-426b-8d4e-2b96f5c269ea
ms.openlocfilehash: fa5f0c3d3d409384b7cdc3c8a9cbe884732cbf8c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338508"
---
# <a name="compiler-warning-level-1-c4186"></a>컴파일러 경고(수준 1) C4186

\#가져오기 ' attribute '특성에 count 인수가; 필요 무시

`#import` 특성의 인수 개수가 잘못되었습니다.

## <a name="example"></a>예제

```
// C4186.cpp
// compile with: /W1 /c
#import "stdole2.tlb" no_namespace("abc") rename("a","b","c")  // C4186
```

`no_namespace` 특성은 인수를 사용하지 않습니다. **rename** 특성은 두 개의 인수만 사용합니다.