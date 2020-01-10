---
title: 컴파일러 오류 C2081
ms.date: 11/04/2016
f1_keywords:
- C2081
helpviewer_keywords:
- C2081
ms.assetid: 7db9892d-364d-4178-a49d-f8398ece09a0
ms.openlocfilehash: 2e8e813d8162b9a191b6760366b52783e7c8609f
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301992"
---
# <a name="compiler-error-c2081"></a>컴파일러 오류 C2081

' identifier ': 정식 매개 변수 목록에 있는 이름이 잘못 되었습니다.

식별자로 인해 구문 오류가 발생 했습니다.

이 오류는 정식 매개 변수 목록에 이전 스타일을 사용 하 여 발생할 수 있습니다. 정식 매개 변수 목록에서 형식 매개 변수의 형식을 지정 해야 합니다.

다음 샘플에서는 C2081를 생성 합니다.

```c
// C2081.c
void func( int i, j ) {}  // C2081, no type specified for j
```

가능한 해결 방법:

```c
// C2081b.c
// compile with: /c
void func( int i, int j ) {}
```
