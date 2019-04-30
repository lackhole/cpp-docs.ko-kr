---
title: 컴파일러 경고(수준 1) C4052
ms.date: 11/04/2016
f1_keywords:
- C4052
helpviewer_keywords:
- C4052
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
ms.openlocfilehash: c7d2a603b7ec97889b075c7a67e5b8439ad487af
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388646"
---
# <a name="compiler-warning-level-1-c4052"></a>컴파일러 경고(수준 1) C4052

함수 선언이 다릅니다. 한쪽에 가변 인수가 들어 있습니다.

하나의 함수 선언에 변수 인수가 없습니다. 무시됩니다.

다음 샘플에서는 C4052를 생성합니다.

```
// C4052.c
// compile with: /W4 /c
int f();
int f(int i, ...);   // C4052
```