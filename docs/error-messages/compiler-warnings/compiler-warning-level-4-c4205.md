---
title: 컴파일러 경고(수준 4) C4205
ms.date: 11/04/2016
f1_keywords:
- C4205
helpviewer_keywords:
- C4205
ms.assetid: 39b5108c-7230-41b4-b2fe-2293eb6aae28
ms.openlocfilehash: 1b165d2bdb2fb50df89fdd77c734c054a40b6e95
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401230"
---
# <a name="compiler-warning-level-4-c4205"></a>컴파일러 경고(수준 4) C4205

비표준 확장이 사용 됨: 함수 범위에서 정적 함수 선언

Microsoft 확장명 (/Ze)를 사용 하 여 **정적** 다른 함수 내에서 함수를 선언할 수 있습니다. 함수는 전역 범위가 지정 됩니다.

## <a name="example"></a>예제

```
// C4205.c
// compile with: /W4
void func1()
{
   static int func2();  // C4205
};

int main()
{
}
```

이러한 초기화는 ANSI 호환성 사용할 수 없습니다 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).