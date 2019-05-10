---
title: 심각한 오류 C1103
ms.date: 11/04/2016
f1_keywords:
- C1103
helpviewer_keywords:
- C1103
ms.assetid: 9d276939-9c47-4235-9d20-76b8434f9731
ms.openlocfilehash: b6253af9fcf400321fb58d4d8a6d7aacf461b926
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174202"
---
# <a name="fatal-error-c1103"></a>심각한 오류 C1103

progid를 가져오는 동안 심각한 오류가 발생했습니다. 'message'

컴파일러가 형식 라이브러리를 가져오는 동안 문제를 발견했습니다.  예를 들어 progid를 사용하여 형식 라이브러리를 지정하고 `no_registry`도 지정할 수는 없습니다.

자세한 내용은 [#import 지시문](../../preprocessor/hash-import-directive-cpp.md)합니다.

다음 샘플에서는 C1103을 생성합니다.

```
// C1103.cpp
#import "progid:a.b.id.1.5" no_registry auto_search   // C1103
```