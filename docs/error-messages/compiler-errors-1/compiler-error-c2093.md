---
title: 컴파일러 오류 C2093
ms.date: 11/04/2016
f1_keywords:
- C2093
helpviewer_keywords:
- C2093
ms.assetid: 17529a70-9169-46b5-9fc6-57a5ce224e6a
ms.openlocfilehash: 52fcd69e631f1ca24664cde06478ae33ca2a37f2
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301953"
---
# <a name="compiler-error-c2093"></a>컴파일러 오류 C2093

' variable1 ': ' variable2 ' 자동 변수의 주소를 사용 하 여 초기화할 수 없습니다.

[/Za](../../build/reference/za-ze-disable-language-extensions.md)를 사용 하 여 컴파일하는 경우 프로그램에서 자동 변수의 주소를 이니셜라이저로 사용 하려고 시도 했습니다.

다음 샘플에서는 C2093를 생성 합니다.

```c
// C2093.c
// compile with: /Za /c
void func() {
   int li;   // an implicit auto variable
   int * s[]= { &li };   // C2093 address is not a constant

   // OK
   static int li2;
   int * s2[]= { &li2 };
}
```
