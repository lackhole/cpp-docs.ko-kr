---
title: 컴파일러 오류 C2378
ms.date: 11/04/2016
f1_keywords:
- C2378
helpviewer_keywords:
- C2378
ms.assetid: 507a91c6-ca72-48df-b3a4-2cf931c86806
ms.openlocfilehash: fb6d228826cf1b21904863505c0963069e89d32d
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344870"
---
# <a name="compiler-error-c2378"></a>컴파일러 오류 C2378

'identifier': 재정의. 형식 정의를 사용하여 기호를 오버로드할 수 없습니다.

식별자가 `typedef`로 다시 정의되었습니다.

다음 샘플에서는 C2378을 생성합니다.

```
// C2378.cpp
// compile with: /c
int i;
typedef int i;   // C2378
typedef int b;   // OK
```