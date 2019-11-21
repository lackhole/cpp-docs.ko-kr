---
title: 컴파일러 경고(수준 1) C4186
ms.date: 11/04/2016
f1_keywords:
- C4186
helpviewer_keywords:
- C4186
ms.assetid: caf3f7d8-f305-426b-8d4e-2b96f5c269ea
ms.openlocfilehash: 3dd339d7535d0a6ef077a562dd82b6c70d17bfb5
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73624950"
---
# <a name="compiler-warning-level-1-c4186"></a>컴파일러 경고(수준 1) C4186

' attribute ' 특성을 가져오는 \#count 인수가 필요 합니다. 무시

`#import` 특성의 인수 개수가 잘못되었습니다.

## <a name="example"></a>예제

```cpp
// C4186.cpp
// compile with: /W1 /c
#import "stdole2.tlb" no_namespace("abc") rename("a","b","c")  // C4186
```

`no_namespace` 특성은 인수를 사용하지 않습니다. **rename** 특성은 두 개의 인수만 사용합니다.