---
title: 컴파일러 오류 C2640
ms.date: 11/04/2016
f1_keywords:
- C2640
helpviewer_keywords:
- C2640
ms.assetid: e4d137ab-ed1d-457c-9eec-b70d97f1b0b4
ms.openlocfilehash: d0dc2dd514186a94811b816c5f3f470a057186f9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182602"
---
# <a name="compiler-error-c2640"></a>컴파일러 오류 C2640

'identifier': __based 한정자를 참조

`__based` 한정자는 포인터에만 사용할 수 있습니다.

다음 샘플에서는 C2640 오류가 생성 됩니다.

```
// C2640.cpp
void f(int i) {
    void *vp;
    int _based(vp) &vr = I;  // C2640
}
```