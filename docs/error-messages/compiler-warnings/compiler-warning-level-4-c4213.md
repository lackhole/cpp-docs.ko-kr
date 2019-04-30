---
title: 컴파일러 경고(수준 4) C4213
ms.date: 11/04/2016
f1_keywords:
- C4213
helpviewer_keywords:
- C4213
ms.assetid: 59fc3f61-ebd2-499e-99d7-f57bec11eda1
ms.openlocfilehash: 8a3697b3bf63ac2a7a1e4e4bd0bf3a626c6bd631
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401152"
---
# <a name="compiler-warning-level-4-c4213"></a>컴파일러 경고(수준 4) C4213

비표준 확장이 사용 됨: l-value 캐스팅

기본 Microsoft 확장 (/Ze)을 사용 하 여 대입문의 왼쪽에 캐스트를 사용할 수 있습니다.

## <a name="example"></a>예제

```
// C4213.c
// compile with: /W4
void *a;
void f()
{
   int   i[3];
   a = &i;
   *(( int * )a )++ = 3;  // C4213
}

int main()
{
}
```

이러한 캐스트 ANSI 호환성 올바르지 않습니다. ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).