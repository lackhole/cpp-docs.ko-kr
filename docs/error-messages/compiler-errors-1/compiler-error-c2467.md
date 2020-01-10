---
title: 컴파일러 오류 C2467
ms.date: 11/04/2016
f1_keywords:
- C2467
helpviewer_keywords:
- C2467
ms.assetid: f9ead270-5d0b-41cc-bdcd-586a647c67a7
ms.openlocfilehash: da17a3f78c8cab8144cb66b9a672dc59190b50f9
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301147"
---
# <a name="compiler-error-c2467"></a>컴파일러 오류 C2467

익명의 ' 사용자 정의 형식 ' 선언이 잘못 되었습니다.

중첩 된 사용자 정의 형식이 선언 되었습니다. 이 오류는[/za](../../build/reference/za-ze-disable-language-extensions.md)(ANSI compatibility option)를 사용 하는 C 소스 코드를 컴파일하는 경우에 발생 합니다.

다음 샘플에서는 C2467를 생성 합니다.

```c
//C2467.c
// compile with: /Za
int main() {
   struct X {
      union { int i; };   // C2467, nested declaration
   };
}
```
