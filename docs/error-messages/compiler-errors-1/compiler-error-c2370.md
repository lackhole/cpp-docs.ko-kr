---
title: 컴파일러 오류 C2370
ms.date: 11/04/2016
f1_keywords:
- C2370
helpviewer_keywords:
- C2370
ms.assetid: 03403e8f-f393-47c4-bd25-5c1c7ea7d5cd
ms.openlocfilehash: ab7b19799925f9aa02f67ffdbec181628391e495
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745657"
---
# <a name="compiler-error-c2370"></a>컴파일러 오류 C2370

'identifier': 재정의. 스토리지 클래스가 다릅니다.

식별자를 다른 스토리지 클래스로 이미 선언했습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2370을 생성합니다.

```cpp
// C2370.cpp
// compile with: /Za /c
extern int i;
static int i;   // C2370
int i;   // OK
```

## <a name="example"></a>예제

다음 샘플에서는 C2370을 생성합니다.

```cpp
// C2370b.cpp
#define Thread __declspec( thread )
extern int tls_i;
int Thread tls_i;   // C2370 declaration and the definition differ
int tls_i;   // OK
```
