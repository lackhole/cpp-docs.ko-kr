---
title: 컴파일러 경고(수준 1) C4174
ms.date: 11/04/2016
f1_keywords:
- C4174
helpviewer_keywords:
- C4174
ms.assetid: 63301e51-24bc-43c4-bb11-252f7d513e9e
ms.openlocfilehash: cc55318c8ef54f7d7f69e93d72717f54578ba576
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391688"
---
# <a name="compiler-warning-level-1-c4174"></a>컴파일러 경고(수준 1) C4174

'name': #pragma 구성 요소로 사용할 수 없습니다.

## <a name="example"></a>예제

```
// C4174.cpp
// compile with: /W1
#pragma component(info)  // C4174; unknown
#pragma component(browser, off)  // turn off browse info
int main()
{
}
```