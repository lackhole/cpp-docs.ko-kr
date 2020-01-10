---
title: 컴파일러 오류 C2449
ms.date: 11/04/2016
f1_keywords:
- C2449
helpviewer_keywords:
- C2449
ms.assetid: 544bf0b6-daa0-40e8-9f21-8e583d472a2d
ms.openlocfilehash: 6fd62813fdf3b50c0e329fc423e100d55a36ae12
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75299025"
---
# <a name="compiler-error-c2449"></a>컴파일러 오류 C2449

파일 범위에 ' {'가 있습니다 (함수 헤더 없음?).

파일 범위에서 여는 중괄호가 발생 합니다.

함수 헤더와 함수 정의의 여는 중괄호 사이에 세미콜론이 있으면이 오류가 발생할 수 있습니다.

다음 샘플에서는 C2499를 생성 합니다.

```c
// C2449.c
// compile with: /c
void __stdcall func(void) {}   // OK
void __stdcall func(void);  // extra semicolon on this line
{                         // C2449 detected here
```
