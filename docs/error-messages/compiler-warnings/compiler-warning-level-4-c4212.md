---
title: 컴파일러 경고(수준 4) C4212
ms.date: 11/04/2016
f1_keywords:
- C4212
helpviewer_keywords:
- C4212
ms.assetid: df781ea1-182d-4f9f-9a31-55b6ce80c711
ms.openlocfilehash: 99dd99eee3c305a53c5ea03235d23a2520768176
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541822"
---
# <a name="compiler-warning-level-4-c4212"></a>컴파일러 경고(수준 4) C4212

비표준 확장이 사용 됨: 함수 선언에서 줄임표를 사용 했습니다.

함수 프로토타입에는 다양 한 수의 인수가 있습니다. 함수 정의는 그렇지 않습니다.

다음 샘플에서는 C4212를 생성 합니다.

```c
// C4212.c
// compile with: /W4 /Ze /c
void f(int , ...);
void f(int i, int j) {}
```