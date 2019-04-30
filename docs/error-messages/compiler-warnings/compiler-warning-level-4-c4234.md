---
title: 컴파일러 경고(수준 4) C4234
ms.date: 11/04/2016
f1_keywords:
- C4234
helpviewer_keywords:
- C4234
ms.assetid: f7fecd5c-8248-4fde-8446-502aedc357ca
ms.openlocfilehash: 314ee068fb2be6148304360b0aaa3bd8029c283b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401074"
---
# <a name="compiler-warning-level-4-c4234"></a>컴파일러 경고(수준 4) C4234

비표준 확장이 사용 됨: 'keyword' 키워드를 사용 하도록 예약

컴파일러는 사용 하는 키워드를 아직 구현 하지 않습니다.

이 경고는 오류를 자동으로 승격 됩니다. 사용 하 여이 동작을 수정 하려는 경우 [#pragma 경고](../../preprocessor/warning.md)합니다. 예를 들어 수준 4 경고 문제가 c4234

```
#pragma warning(2:4234)
```

소스 코드 파일.