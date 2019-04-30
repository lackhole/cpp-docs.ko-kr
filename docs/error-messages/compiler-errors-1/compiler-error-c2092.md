---
title: 컴파일러 오류 C2092
ms.date: 11/04/2016
f1_keywords:
- C2092
helpviewer_keywords:
- C2092
ms.assetid: 037e44ae-16c8-489a-a512-dcdf7f7795a6
ms.openlocfilehash: d3d0b0e62fbc5f8ad90b3fee5fe39c6bdaba7c2e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62376011"
---
# <a name="compiler-error-c2092"></a>컴파일러 오류 C2092

'배열 name' 배열 요소 형식은 함수 일 수 없습니다.

함수의 배열은 허용 되지 않습니다. 함수에 대 한 포인터의 배열을 사용 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C2092 오류가 생성 됩니다.

```
// C2092.cpp
typedef void (F) ();
typedef F AT[10];   // C2092
```

## <a name="example"></a>예제

해결 방법:

```
// C2092b.cpp
// compile with: /c
typedef void (F) ();
typedef F * AT[10];
```