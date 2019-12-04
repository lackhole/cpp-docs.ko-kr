---
title: 컴파일러 오류 C2147
ms.date: 11/04/2016
f1_keywords:
- C2147
helpviewer_keywords:
- C2147
ms.assetid: d1adb3bf-7ece-4815-922c-ad7492fb6670
ms.openlocfilehash: 0af88d89ff264ca9efd02477a62e5bd7532271bd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756489"
---
# <a name="compiler-error-c2147"></a>컴파일러 오류 C2147

구문 오류: ' identifier '는 새 키워드입니다.

이제 언어의 예약 키워드 인 식별자가 사용 되었습니다.

다음 샘플에서는 C2147를 생성 합니다.

```cpp
// C2147.cpp
// compile with: /clr
int main() {
   int gcnew = 0;   // C2147
   int i = 0;   // OK
}
```
