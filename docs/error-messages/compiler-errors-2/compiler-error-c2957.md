---
title: 컴파일러 오류 C2957
ms.date: 11/04/2016
f1_keywords:
- C2957
helpviewer_keywords:
- C2957
ms.assetid: 9cb4526f-4af8-47e9-b786-56192627ca72
ms.openlocfilehash: 51745b60d89c28280c8c48cdbba3762d92529073
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300754"
---
# <a name="compiler-error-c2957"></a>컴파일러 오류 C2957

'delim': 왼쪽 구분 기호가 잘못되었습니다. '<'가 필요합니다.

제네릭 클래스의 형식이 잘못되었습니다.

다음 샘플에서는 C2957을 생성합니다.

```
// C2957.cpp
// compile with: /clr /LD
generic << class T>   // C2957
// try the following line instead
// generic < class T>
gc class C {};
```