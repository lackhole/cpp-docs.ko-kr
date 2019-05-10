---
title: 컴파일러 오류 C2153
ms.date: 11/04/2016
f1_keywords:
- C2153
helpviewer_keywords:
- C2153
ms.assetid: cfc50cb7-9a0f-4b5b-879a-d419c99f7be1
ms.openlocfilehash: eeb7da509ffb1b8c408763c79d471586eb94f383
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175162"
---
# <a name="compiler-error-c2153"></a>컴파일러 오류 C2153

16 진 상수에는 16 진수가 적어도 하나 있어야 합니다.

16 진수 상수 0 X, x 및 \x 올바르지 않습니다. 16 진수가 적어도 하나를 수행 해야 x 또는 X입니다.

다음 샘플에서는 C2153 오류가 생성 됩니다.

```
// C2153.cpp
int main() {
   int a= 0x;    // C2153
   int b= 0xA;   // OK
}
```