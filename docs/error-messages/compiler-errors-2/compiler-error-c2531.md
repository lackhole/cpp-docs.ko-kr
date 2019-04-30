---
title: 컴파일러 오류 C2531
ms.date: 11/04/2016
f1_keywords:
- C2531
helpviewer_keywords:
- C2531
ms.assetid: c49afe15-55f8-4dc8-ac01-bf653622a7db
ms.openlocfilehash: 03e055e9830b8168fb19885a04c8d40d24713d23
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378969"
---
# <a name="compiler-error-c2531"></a>컴파일러 오류 C2531

'identifier': 비트 필드 잘못 된에 대 한 참조

비트 필드에 대 한 참조는 허용 되지 않습니다.

다음 샘플에서는 C2531 오류가 생성 됩니다.

```
// C2531.cpp
// compile with: /c
class P {
   int &b1 : 10;   // C2531
   int b2 : 10;   // OK
};
```