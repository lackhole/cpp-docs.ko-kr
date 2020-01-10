---
title: 컴파일러 오류 C2088
ms.date: 11/04/2016
f1_keywords:
- C2088
helpviewer_keywords:
- C2088
ms.assetid: b93f7094-185b-423d-8bb9-507cd757dbf5
ms.openlocfilehash: 1f798774a7735a6aceb0bf75b3c6da9ccb1e4a72
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301979"
---
# <a name="compiler-error-c2088"></a>컴파일러 오류 C2088

' operator ': ' 클래스 키 '의 경우 잘못 되었습니다.

구조체 또는 공용 구조체에 대 한 연산자가 정의 되지 않았습니다. 이 오류는 C 코드에 대해서만 유효 합니다.

다음 샘플에서는 C2088를 세 번 생성 합니다.

```c
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
