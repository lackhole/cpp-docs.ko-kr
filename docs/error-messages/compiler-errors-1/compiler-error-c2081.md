---
title: 컴파일러 오류 C2081
ms.date: 11/04/2016
f1_keywords:
- C2081
helpviewer_keywords:
- C2081
ms.assetid: 7db9892d-364d-4178-a49d-f8398ece09a0
ms.openlocfilehash: 2bccd15b8c2b6d1c5cd6c4b536bbdaf350eb0181
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408656"
---
# <a name="compiler-error-c2081"></a>컴파일러 오류 C2081

'identifier': 정식 매개 변수 목록이 잘못 되었습니다에서 이름

식별자에 구문 오류가 발생합니다.

이 오류는 정식 매개 변수 목록에 대 한 이전 스타일을 사용 하 여 발생할 수 있습니다. 정식 매개 변수 목록의 형식 매개 변수의 형식을 지정 해야 합니다.

다음 샘플에서는 C2081 오류가 생성 됩니다.

```
// C2081.c
void func( int i, j ) {}  // C2081, no type specified for j
```

해결 방법:

```
// C2081b.c
// compile with: /c
void func( int i, int j ) {}
```