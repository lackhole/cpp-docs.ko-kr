---
title: 컴파일러 경고 (수준 1) C4659
ms.date: 11/04/2016
f1_keywords:
- C4659
helpviewer_keywords:
- C4659
ms.assetid: e29ba8db-7917-43f6-8e34-868b752279ae
ms.openlocfilehash: 27023e6886638be63db1e1fb654c0caa70769a56
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052525"
---
# <a name="compiler-warning-level-1-c4659"></a>컴파일러 경고 (수준 1) C4659

\#pragma ' pragma ': ' segment ' 예약 세그먼트를 사용 하 여 정의 되지 않은 동작이 있습니다. #pragma 주석 (링커, ...)을 사용 하십시오.

.Drectve 옵션을 사용 하 여 옵션을 링커에 전달 했습니다. 대신 링커 옵션을 전달 하기 위해 pragma [주석을](../../preprocessor/comment-c-cpp.md) 사용 합니다.

```cpp
// C4659.cpp
// compile with: /W1 /LD
#pragma code_seg(".drectve")   // C4659
```