---
title: 컴파일러 경고(수준 1) C4606
ms.date: 11/04/2016
f1_keywords:
- C4606
helpviewer_keywords:
- C4606
ms.assetid: c1b45fb6-672b-42eb-9e1c-c67b3e4150d3
ms.openlocfilehash: e471ca3e478d1166b150e49bf25efa4b9d5803cb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402517"
---
# <a name="compiler-warning-level-1-c4606"></a>컴파일러 경고(수준 1) C4606

\#pragma 경고: 'warning_number'가 무시 됩니다. 코드 분석 경고가 경고 수준과 연결 되어 있지 않습니다.

코드 분석 경고에 `error`, `once`, 및 `default` 지원 되는 [경고](../../preprocessor/warning.md) pragma입니다.

## <a name="example"></a>예제

다음 샘플 C4606을 생성합니다.

```
// C4606.cpp
// compile with: /c /W1
#pragma warning(1: 6001)   // C4606
#pragma warning(once: 6001)   // OK
```