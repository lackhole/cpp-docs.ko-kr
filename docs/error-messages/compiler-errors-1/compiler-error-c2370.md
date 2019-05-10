---
title: 컴파일러 오류 C2370
ms.date: 11/04/2016
f1_keywords:
- C2370
helpviewer_keywords:
- C2370
ms.assetid: 03403e8f-f393-47c4-bd25-5c1c7ea7d5cd
ms.openlocfilehash: 28c337a5cadfaeced39ee6ed73601338941029fc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188041"
---
# <a name="compiler-error-c2370"></a>컴파일러 오류 C2370

'identifier': 재정의. 스토리지 클래스가 다릅니다.

식별자를 다른 스토리지 클래스로 이미 선언했습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2370을 생성합니다.

```
// C2370.cpp
// compile with: /Za /c
extern int i;
static int i;   // C2370
int i;   // OK
```

## <a name="example"></a>예제

다음 샘플에서는 C2370을 생성합니다.

```
// C2370b.cpp
#define Thread __declspec( thread )
extern int tls_i;
int Thread tls_i;   // C2370 declaration and the definition differ
int tls_i;   // OK
```