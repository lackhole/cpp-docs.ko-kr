---
title: 컴파일러 경고(수준 4) C4221
ms.date: 11/04/2016
f1_keywords:
- C4221
helpviewer_keywords:
- C4221
ms.assetid: 8532bd68-54dc-4526-8597-f61dcb0a0129
ms.openlocfilehash: f552a5d76d1a778cdf72cbe079138f609350ffb1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401100"
---
# <a name="compiler-warning-level-4-c4221"></a>컴파일러 경고(수준 4) C4221

비표준 확장이 사용 됨: 'identifier': 자동 변수의 주소를 사용 하 여 초기화할 수 없습니다.

기본 Microsoft 확장 (/Ze)을 사용 하 여 집계 형식을 초기화할 수 있습니다 (**배열**를 `struct`, 또는 **union**) 로컬 (자동) 변수의 주소를 사용 하 여 합니다.

## <a name="example"></a>예제

```
// C4221.c
// compile with: /W4
struct S
{
   int *i;
};

void func()
{
   int j;
   struct S s1 = { &j };   // C4221
}

int main()
{
}
```

이러한 초기화는 ANSI 호환성 사용할 수 없습니다 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).