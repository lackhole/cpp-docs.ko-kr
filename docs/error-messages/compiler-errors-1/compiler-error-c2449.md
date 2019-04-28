---
title: 컴파일러 오류 C2449
ms.date: 11/04/2016
f1_keywords:
- C2449
helpviewer_keywords:
- C2449
ms.assetid: 544bf0b6-daa0-40e8-9f21-8e583d472a2d
ms.openlocfilehash: f674bbec7cee8c00792848ee7e51b1e46299dd58
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302074"
---
# <a name="compiler-error-c2449"></a>컴파일러 오류 C2449

찾을 ' {0} ' 파일 범위 (함수 헤더가 없습니다.?)

중괄호는 파일 범위에서 발생합니다.

이 오류는 함수 헤더와 함수 정의의 여는 중괄호 사이 세미콜론을 하 여 발생할 수 있습니다.

다음 샘플에서는 C2499 오류가 생성 됩니다.

```
// C2449.c
// compile with: /c
void __stdcall func(void) {}   // OK
void __stdcall func(void);  // extra semicolon on this line
{                         // C2449 detected here
```