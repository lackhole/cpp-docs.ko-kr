---
title: 컴파일러 오류 C3353
ms.date: 11/04/2016
f1_keywords:
- C3353
helpviewer_keywords:
- C3353
ms.assetid: 5699c04b-d504-46ce-bf71-c200318fed71
ms.openlocfilehash: c38642d7abd4f2fd50792c548c9a5521b2da10ad
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59777590"
---
# <a name="compiler-error-c3353"></a>컴파일러 오류 C3353

'delegate': 대리자는 전역 함수 또는 관리되는 또는 WinRT 형식의 멤버 함수에서만 만들어질 수 있습니다.

대리자를 사용 하 여 선언 된 [대리자](../../extensions/delegate-cpp-component-extensions.md) 키워드를 전역 범위에서 선언할 수 있습니다.

다음 샘플에서는 C3353을 생성합니다.

```
// C3353.cpp
// compile with: /clr
delegate int f;   // C3353
```