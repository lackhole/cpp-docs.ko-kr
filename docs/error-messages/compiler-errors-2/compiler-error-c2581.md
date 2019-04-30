---
title: 컴파일러 오류 C2581
ms.date: 11/04/2016
f1_keywords:
- C2581
helpviewer_keywords:
- C2581
ms.assetid: 24a4e4c1-24d3-4e42-b760-7dcaf9740b16
ms.openlocfilehash: edfab092c82f9dc1d4b9dfe5d21daa2b2ab98d08
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385864"
---
# <a name="compiler-error-c2581"></a>컴파일러 오류 C2581

'type': 정적 ' operator =' 함수에 유효 하지 않은

할당 (`=`) 연산자를 잘못 선언 되었습니다 `static`합니다. 할당 연산자 일 수 없습니다 `static`합니다. 자세한 내용은 [사용자 정의 연산자 (C++/CLI)](../../dotnet/user-defined-operators-cpp-cli.md)합니다.

## <a name="example"></a>예제

다음 샘플 C2581를 생성합니다.

```
// C2581.cpp
// compile with: /clr /c
ref struct Y {
   static Y ^ operator = (Y^ me, int i);   // C2581
   Y^ operator =(int i);   // OK
};
```