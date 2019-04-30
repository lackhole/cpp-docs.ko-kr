---
title: 컴파일러 오류 C2238
ms.date: 11/04/2016
f1_keywords:
- C2238
helpviewer_keywords:
- C2238
ms.assetid: 3d53060c-d6b7-4603-b9cf-d7c65eb64cd2
ms.openlocfilehash: dde413c2c38e97fe47a0063953d64b0381d313a9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301424"
---
# <a name="compiler-error-c2238"></a>컴파일러 오류 C2238

'token' 앞에 예기치 않은 토큰이 있습니다.

잘못된 토큰이 있습니다.

다음 샘플에서는 C2238을 생성합니다.

```
// C2238.cpp
// compile with: /c
class v {
virtual: int vvv;   // C2238
};
```