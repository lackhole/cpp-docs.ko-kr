---
title: 컴파일러 오류 C2021
ms.date: 11/04/2016
f1_keywords:
- C2021
helpviewer_keywords:
- C2021
ms.assetid: 064f32e2-3794-48d5-9767-991003dcb36a
ms.openlocfilehash: 6492dfffbb5a2f80ea543d4248c0f77759c0a521
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303608"
---
# <a name="compiler-error-c2021"></a>컴파일러 오류 C2021

'character'가 아니라 지수 값이 필요합니다.

부동 소수점 상수의 지 수로 사용 되는 문자를 유효한 숫자가 아닙니다. 범위에 있는 지 수를 사용 해야 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C2021 오류가 생성 됩니다.

```
// C2021.cpp
float test1=1.175494351E;   // C2021
```

## <a name="example"></a>예제

해결 방법:

```
// C2021b.cpp
// compile with: /c
float test2=1.175494351E8;
```