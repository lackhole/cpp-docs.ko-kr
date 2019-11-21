---
title: 컴파일러 경고(수준 1) C4174
ms.date: 11/04/2016
f1_keywords:
- C4174
helpviewer_keywords:
- C4174
ms.assetid: 63301e51-24bc-43c4-bb11-252f7d513e9e
ms.openlocfilehash: dfa3c66e31e35cf9dbbd55f29fcd2d511870fdce
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73624814"
---
# <a name="compiler-warning-level-1-c4174"></a>컴파일러 경고(수준 1) C4174

'name': #pragma 구성 요소로 사용할 수 없습니다.

## <a name="example"></a>예제

```cpp
// C4174.cpp
// compile with: /W1
#pragma component(info)  // C4174; unknown
#pragma component(browser, off)  // turn off browse info
int main()
{
}
```