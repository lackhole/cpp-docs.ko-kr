---
title: 컴파일러 오류 C2563
ms.date: 11/04/2016
f1_keywords:
- C2563
helpviewer_keywords:
- C2563
ms.assetid: 54abba68-6458-4ca5-894d-3babdb7b3552
ms.openlocfilehash: 04a10c82fa6aa39bcf1098d6d4aabfc2f769e7c8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257857"
---
# <a name="compiler-error-c2563"></a>컴파일러 오류 C2563

정식 매개 변수 목록과에서 일치 하지 않습니다.

함수 (또는 함수에 대 한 포인터) 형식 매개 변수 목록에 다른 함수 (또는 멤버 함수에 대 한 포인터)의 일치 하지 않습니다. 결과적으로, 함수 또는 포인터에 할당 될 수 없습니다.

다음 샘플에서는 C2563 오류가 생성 됩니다.

```
// C2563.cpp
void func( int );
void func( int, int );
int main() {
   void *fp();
   fp = func;   // C2563
}
```