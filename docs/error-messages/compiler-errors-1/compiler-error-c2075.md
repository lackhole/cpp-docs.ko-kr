---
title: 컴파일러 오류 C2075
ms.date: 11/04/2016
f1_keywords:
- C2075
helpviewer_keywords:
- C2075
ms.assetid: 8b1865d2-540b-4117-b982-e7a58a0b6cf7
ms.openlocfilehash: 630c5cf2e90ae3373ef28b1388f06cd3fc069425
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302005"
---
# <a name="compiler-error-c2075"></a>컴파일러 오류 C2075

'identifier': 배열 초기화에는 중괄호가 있어야 합니다.

지정된 배열 이니셜라이저 주변에 중괄호가 없습니다.

다음 샘플에서는 C2075를 생성합니다.

```c
// C2075.c
int main() {
   int i[] = 1, 2, 3 };   // C2075
}
```

가능한 해결 방법:

```c
// C2075b.c
int main() {
   int j[] = { 1, 2, 3 };
}
```
