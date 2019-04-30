---
title: 컴파일러 오류 C2781
ms.date: 11/04/2016
f1_keywords:
- C2781
helpviewer_keywords:
- C2781
ms.assetid: f29b9963-f55b-427c-8db6-50f37713df5a
ms.openlocfilehash: be665d86cf230c364f522fd1ad74cd5a124ac9de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62382972"
---
# <a name="compiler-error-c2781"></a>컴파일러 오류 C2781

'declaration': 적어도 value1 인수-value2 제공

가변 매개 변수 목록 사용 하 여 함수 템플릿 인수가 너무 적습니다.

다음 샘플에서는 C2781 오류가 생성 됩니다.

```
// C2781.cpp
template<typename T>
void f(T, T, ...){}

int main() {
   f(1);   // C2781

   // try the following line instead
   f(1,1);
}
```