---
title: 컴파일러 경고(수준 1) C4926
ms.date: 11/04/2016
f1_keywords:
- C4926
helpviewer_keywords:
- C4926
ms.assetid: 5717fce0-146f-4ef2-bde0-e9a01c0922d1
ms.openlocfilehash: 839d0b8ffad947e7031ca618b255588f54b82770
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393469"
---
# <a name="compiler-warning-level-1-c4926"></a>컴파일러 경고(수준 1) C4926

'identifier': 기호를 이미 정의했으므로 특성이 무시됩니다.

정방향 선언이 있지만 이름이 같은 특성을 가진 구문이 이미 있습니다. 정방향 선언에 대한 특성은 무시됩니다.

다음 샘플에서는 C4926을 생성합니다.

```
// C4926.cpp
// compile with: /W1
[module(name="MyLib")];

[coclass]
struct a {
};

[coclass]
struct a;   // C4926

int main() {
}
```