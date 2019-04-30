---
title: 컴파일러 경고(수준 4) C4210
ms.date: 11/04/2016
f1_keywords:
- C4210
helpviewer_keywords:
- C4210
ms.assetid: f8600adf-dfe2-4022-a37a-3d4997641dfd
ms.openlocfilehash: 3435e18f60568cad390dcb0ef7900658a21ea959
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401191"
---
# <a name="compiler-warning-level-4-c4210"></a>컴파일러 경고(수준 4) C4210

비표준 확장이 사용 됨: 파일 범위를 제공 하는 함수

기본 Microsoft 확장 ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)), 함수 선언에는 파일 범위가 있습니다.

```
// C4210.c
// compile with: /W4 /c
void func1()
{
   extern int func2( double );   // C4210 expected
}

int main()
{
   func2( 4 );   //  /Ze passes 4 as type double
}                //  /Za passes 4 as type int
```

이 확장은 다른 컴파일러로 이식 되 코드를 방지할 수 있습니다.