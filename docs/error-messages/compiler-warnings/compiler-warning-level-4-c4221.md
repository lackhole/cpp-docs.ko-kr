---
title: 컴파일러 경고(수준 4) C4221
ms.date: 11/04/2016
f1_keywords:
- C4221
helpviewer_keywords:
- C4221
ms.assetid: 8532bd68-54dc-4526-8597-f61dcb0a0129
ms.openlocfilehash: fa87c240472df2926753781f0f14cbd69752de00
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541934"
---
# <a name="compiler-warning-level-4-c4221"></a>컴파일러 경고(수준 4) C4221

비표준 확장이 사용 됨: ' identifier ': 자동 변수의 주소를 사용 하 여 초기화할 수 없습니다.

기본 Microsoft 확장 (/Ze)을 사용 하면 로컬 (자동) 변수의 주소를 사용 하 여 집계 형식 (**array**, `struct`또는 **union**)을 초기화할 수 있습니다.

## <a name="example"></a>예제

```c
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

이러한 초기화는 ANSI 호환성 ([/za](../../build/reference/za-ze-disable-language-extensions.md))에서 유효 하지 않습니다.