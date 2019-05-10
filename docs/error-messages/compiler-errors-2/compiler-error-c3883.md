---
title: 컴파일러 오류 C3883
ms.date: 11/04/2016
f1_keywords:
- C3883
helpviewer_keywords:
- C3883
ms.assetid: cdd1c1f4-f268-4469-9c62-d52303114b0c
ms.openlocfilehash: 51ecf5fbc793c02a23e2aa02fb08e37ebe4b0ad0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62347040"
---
# <a name="compiler-error-c3883"></a>컴파일러 오류 C3883

'var': initonly 정적 데이터 멤버를 초기화 해야 합니다

변수 표시 [initonly](../../dotnet/initonly-cpp-cli.md) 올바르게 초기화 되지 않았습니다.

다음 샘플에서는 C3883 오류가 생성 됩니다.

```
// C3883.cpp
// compile with: /clr
ref struct Y1 {
   initonly
   static int staticConst1;   // C3883
};
```

다음 샘플에는 가능한 해결 방법을 보여 줍니다.

```
// C3883b.cpp
// compile with: /clr /c
ref struct Y1 {
   initonly
   static int staticConst2 = 0;
};
```

다음 샘플에는 정적 생성자에서 초기화 하는 방법을 보여 줍니다.

```
// C3883c.cpp
// compile with: /clr /LD
ref struct Y1 {
   initonly
   static int staticConst1;

   static Y1() {
      staticConst1 = 0;
   }
};
```