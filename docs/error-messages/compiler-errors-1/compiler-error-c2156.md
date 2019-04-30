---
title: 컴파일러 오류 C2156
ms.date: 11/04/2016
f1_keywords:
- C2156
helpviewer_keywords:
- C2156
ms.assetid: 136f9c67-2c27-4f61-b7e6-ccd202eca697
ms.openlocfilehash: e2637a54249c37f3872d87959f2cf6d7bf73481e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174889"
---
# <a name="compiler-error-c2156"></a>컴파일러 오류 C2156

pragma는 함수 외부에 있어야 합니다.

전역 수준(함수 본문 외부)에서 지정해야 하는 pragma가 함수 내에 있습니다.

다음 샘플에서는 C2156을 생성합니다.

```
// C2156.cpp
#pragma optimize( "l", on )   // OK
int main() {
   #pragma optimize( "l", on )   // C2156
}
```