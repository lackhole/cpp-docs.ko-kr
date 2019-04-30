---
title: 컴파일러 오류 C2008
ms.date: 11/04/2016
f1_keywords:
- C2008
helpviewer_keywords:
- C2008
ms.assetid: e748ccbe-ffd4-4008-aca7-e53c25225209
ms.openlocfilehash: 0bd9193d6e305a4b6c6851ef2524a68ecc056816
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208986"
---
# <a name="compiler-error-c2008"></a>컴파일러 오류 C2008

'character': 매크로 정의에 사용할 수 없습니다.

매크로 이름 바로 뒤에 문자가 표시 됩니다. 오류를 해결 하려면 매크로 이름 뒤에 오는 한 공간 이어야 합니다.

다음 샘플에서는 C2008을 생성합니다.

```
// C2008.cpp
#define TEST1"mytest1"    // C2008
```

해결 방법:

```
// C2008b.cpp
// compile with: /c
#define TEST2 "mytest2"
```