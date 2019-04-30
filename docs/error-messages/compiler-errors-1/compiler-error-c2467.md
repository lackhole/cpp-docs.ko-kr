---
title: 컴파일러 오류 C2467
ms.date: 11/04/2016
f1_keywords:
- C2467
helpviewer_keywords:
- C2467
ms.assetid: f9ead270-5d0b-41cc-bdcd-586a647c67a7
ms.openlocfilehash: aa45cbb19519dea7bd5c8fb96abd2c76ea30a786
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302087"
---
# <a name="compiler-error-c2467"></a>컴파일러 오류 C2467

익명 ' 사용자 정의 형식당 ' 선언은 올바르지 않습니다

중첩 된 사용자 정의 형식 선언 되었습니다. ANSI 호환성 옵션을 사용 하 여 C 소스 코드를 컴파일할 때 오류입니다 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) 사용 하도록 설정 합니다.

다음 샘플에서는 C2467 오류가 생성 됩니다.

```
//C2467.c
// compile with: /Za
int main() {
   struct X {
      union { int i; };   // C2467, nested declaration
   };
}
```