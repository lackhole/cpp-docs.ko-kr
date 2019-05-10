---
title: 컴파일러 경고(수준 1) C4659
ms.date: 11/04/2016
f1_keywords:
- C4659
helpviewer_keywords:
- C4659
ms.assetid: e29ba8db-7917-43f6-8e34-868b752279ae
ms.openlocfilehash: 2aef25e922d8f38ac7103b1b12ccb31c282f0403
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374653"
---
# <a name="compiler-warning-level-1-c4659"></a>컴파일러 경고(수준 1) C4659

\#pragma 'pragma': 사용 하 여 예약 된 세그먼트 '세그먼트' 동작이 정의 되지 않았습니다, #pragma 주석 (linker,...)를 사용 합니다.

.Drectve 옵션을 링커에 옵션 전달 하는 데 사용 되었습니다. Pragma를 사용 하는 대신 [주석](../../preprocessor/comment-c-cpp.md) 링커 옵션을 전달 합니다.

```
// C4659.cpp
// compile with: /W1 /LD
#pragma code_seg(".drectve")   // C4659
```