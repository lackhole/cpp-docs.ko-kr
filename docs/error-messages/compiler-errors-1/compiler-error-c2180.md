---
title: 컴파일러 오류 C2180
ms.date: 11/04/2016
f1_keywords:
- C2180
helpviewer_keywords:
- C2180
ms.assetid: ea71b39e-b977-48a7-b7bd-af68ef5e263b
ms.openlocfilehash: 5e9444356e536a8369dbcf62cac3c7538d9da5dd
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301901"
---
# <a name="compiler-error-c2180"></a>컴파일러 오류 C2180

제어 식이 'type' 형식입니다.

`if`, `while`, `for` 또는 `do` 문의 제어 식은 `void`로 캐스팅되는 식입니다. 이 문제를 해결하려면 `bool` 또는 `bool`로 변환할 수 있는 형식을 생성하는 식으로 제어 식을 변경합니다.

다음 샘플에서는 C2180 오류가 발생하는 경우를 보여 줍니다.

```c
// C2180.c

int main() {
   while ((void)1)   // C2180
      return 1;
   while (1)         // OK
      return 0;
}
```
