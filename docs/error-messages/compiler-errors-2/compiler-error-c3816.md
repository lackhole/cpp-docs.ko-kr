---
title: 컴파일러 오류 C3816
ms.date: 11/04/2016
f1_keywords:
- C3816
helpviewer_keywords:
- C3816
ms.assetid: 2e52cc7f-e31c-41a3-8d6f-9f5fab3648c0
ms.openlocfilehash: d362480b3380fe4576ef56b8ca76dfa10eaa1408
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384285"
---
# <a name="compiler-error-c3816"></a>컴파일러 오류 C3816

'declaration' 이전에 선언 되었거나 다른 관리 되는 또는 WinRTmodifier 정의

정방향 선언 및 실제 선언에서는 특성의 선언에 충돌이나 불일치가 없어야 합니다.

다음 샘플에서는 C3816을 생성하고 해결 방법을 보여 줍니다.

```
// C3816a.cpp
// compile with: /clr /c
class C1;
// try the following line instead
// ref class C1;

ref class C1{  // C3816, forward declaration does not use ref
};
```