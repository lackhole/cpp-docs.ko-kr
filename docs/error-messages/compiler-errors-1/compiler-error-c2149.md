---
title: 컴파일러 오류 C2149
ms.date: 11/04/2016
f1_keywords:
- C2149
helpviewer_keywords:
- C2149
ms.assetid: 7a106dab-d79f-41b9-85be-f36e86e4d2ab
ms.openlocfilehash: 62eca9730b28f83cea39d5c6606d4bb94ce885dd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175209"
---
# <a name="compiler-error-c2149"></a>컴파일러 오류 C2149

'identifier': 명명된 비트 필드의 너비가 0일 수 없습니다.

비트 필드는 명명되지 않은 경우에만 너비가 0일 수 있습니다.

다음 샘플에서는 C2149를 생성합니다.

```
// C2149.cpp
// compile with: /c
struct C {
   int i : 0;   // C2149
   int j : 2;   // OK
};
```