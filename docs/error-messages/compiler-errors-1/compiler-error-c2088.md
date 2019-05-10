---
title: 컴파일러 오류 C2088
ms.date: 11/04/2016
f1_keywords:
- C2088
helpviewer_keywords:
- C2088
ms.assetid: b93f7094-185b-423d-8bb9-507cd757dbf5
ms.openlocfilehash: 6d53f2896fc3b964a4d2652b3bfd0dcebb4a7226
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175175"
---
# <a name="compiler-error-c2088"></a>컴파일러 오류 C2088

'operator': ' s-k '에 대해 잘못 되었습니다.

연산자를 구조체 또는 공용 구조체에 대 한 정의 되지 않았습니다. 이 오류 C 코드에 대해서만 유효합니다.

다음 샘플에서는 세 번 C2088를 생성합니다.

```
// C2088.c
struct S {
   int m_i;
} s;

int main() {
   int i = s * 1;   // C2088
   struct S s2 = +s;   // C2088
   s++;   // C2088
}
```