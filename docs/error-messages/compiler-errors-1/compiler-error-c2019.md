---
title: 컴파일러 오류 C2019
ms.date: 11/04/2016
f1_keywords:
- C2019
helpviewer_keywords:
- C2019
ms.assetid: 4f37b1e1-9eca-418f-a4c3-141e8512d7b6
ms.openlocfilehash: 6e9e5bbca5da13fdfd4727d3b19aa3656689ce96
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303712"
---
# <a name="compiler-error-c2019"></a>컴파일러 오류 C2019

전처리기 지시문이 있어야 하는데 'character'가 있습니다.

다음에 오는 문자는 `#` 로그인 하지 않은 전처리기 지시문의 첫 번째 문자입니다.

다음 샘플에서는 C2019를 생성합니다.

```
// C2019.cpp
#!define TRUE 1   // C2019
```

해결 방법:

```
// C2019b.cpp
// compile with: /c
#define TRUE 1
```