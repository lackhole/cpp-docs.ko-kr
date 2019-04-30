---
title: 컴파일러 오류 C2380
ms.date: 11/04/2016
f1_keywords:
- C2380
helpviewer_keywords:
- C2380
ms.assetid: 717b1e6e-ddfe-4bac-a5f3-7f9a4dcb1572
ms.openlocfilehash: c0494d4ba405a084e7b455139016c98af7d95191
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344811"
---
# <a name="compiler-error-c2380"></a>컴파일러 오류 C2380

형식 앞에 'identifier' (반환 형식 또는 클래스 이름에 현재 잘못 된 재정의 사용 하 여 생성자?)

생성자 값을 반환 하거나 클래스 이름을 재정의 합니다.

다음 샘플에서는 C2326을 생성합니다.

```
// C2380.cpp
// compile with: /c
class C {
public:
   int C();   // C2380, specifies an int return
   int C;   // C2380, redefinition of i
   C();   // OK
};
```