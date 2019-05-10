---
title: 컴파일러 오류 C2100
ms.date: 11/04/2016
f1_keywords:
- C2100
helpviewer_keywords:
- C2100
ms.assetid: 9ed5ea11-9d55-4ddf-8b1a-162c74f3c390
ms.openlocfilehash: 89273d5ef9c3b011a7b08a160431dcbc17fc065e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350691"
---
# <a name="compiler-error-c2100"></a>컴파일러 오류 C2100

간접 참조가 잘못 되었습니다

간접 참조 연산자 ( `*` ) 포인터가 아닌 값에 적용 됩니다.

다음 샘플에서는 C2100 오류가 생성 됩니다.

```
// C2100.cpp
int main() {
   int r = 0, *s = 0;
   s = &r;
   *r = 200;   // C2100
   *s = 200;   // OK
}
```