---
title: 컴파일러 오류 C2345
ms.date: 11/04/2016
f1_keywords:
- C2345
helpviewer_keywords:
- C2345
ms.assetid: e1cc88b0-0223-4d07-975b-fa99956a82bd
ms.openlocfilehash: ceb2a835ca94399f27640628105afcde986af1b0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188311"
---
# <a name="compiler-error-c2345"></a>컴파일러 오류 C2345

align(value): 맞춤 값이 잘못되었습니다.

[align](../../cpp/align-cpp.md) 키워드에 허용 범위 외부의 값을 전달했습니다.

다음 코드에서는 C2345를 생성합니다.

```
// C2345.cpp
// compile with: /c
__declspec(align(0)) int a;   // C2345
__declspec(align(1)) int a;   // OK
```